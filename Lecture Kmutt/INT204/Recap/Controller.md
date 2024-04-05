
```java
package com.example.demo2.controllers;  
  
import com.example.demo2.dtos.SimpleEmployeeDTO;  
import com.example.demo2.entities.Employee;  
  
import com.example.demo2.services.EmployeeService;  
import org.modelmapper.ModelMapper;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.data.domain.Sort;  
import org.springframework.web.bind.annotation.*;  
  
import java.util.List;  
import java.util.Optional;  
import java.util.stream.Collectors;  
  
@RestController  
@RequestMapping("/employee")  
public class EmployeeController {  
    @Autowired  
    EmployeeService service;  
    @Autowired  
    ModelMapper modelMapper;  
    @GetMapping("/{id}")  
    public SimpleEmployeeDTO getCustomerById(@PathVariable Integer id){  
        Employee employee = service.findById(id);  
        return modelMapper.map(employee,SimpleEmployeeDTO.class);  
    }  
    @GetMapping("/all")  
    public List <SimpleEmployeeDTO> getAll(@RequestParam(defaultValue = "firstName") String sortby,@RequestParam(defaultValue = "ASC") String direction,@RequestParam(defaultValue = "0") Integer page ,@RequestParam(defaultValue = "5") Integer size){  
        System.out.println(direction);  
  
        List<Employee> emp = service.findAll(sortby,direction,page,size);  
        List<SimpleEmployeeDTO> dtos = emp.stream().map(employee -> modelMapper.map(employee, SimpleEmployeeDTO.class)).collect(Collectors.toList());  
        return  dtos ;  
  
    }  
}
```
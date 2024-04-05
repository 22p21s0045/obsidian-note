
### Install
```xml
<dependency>  
    <groupId>org.modelmapper</groupId>  
    <artifactId>modelmapper</artifactId>  
    <version>3.2.0</version>  
</dependency>
```



### Config
```java
  
import org.modelmapper.ModelMapper;  
import org.springframework.context.annotation.Bean;  
import org.springframework.context.annotation.Configuration;  
  
@Configuration  
public class ApplicationConfig {  
    @Bean  
    public ModelMapper modelMapper(){  
        return  new ModelMapper();  
    }  
}
```


```java
public SimpleEmployeeDTO getCustomerById(@PathVariable Integer id){  
    Employee employee = service.findById(id);  
    return modelMapper.map(employee,SimpleEmployeeDTO.class);  
}
```



```java
public List <SimpleEmployeeDTO> getAll(@RequestParam(defaultValue = "firstName") String sortby,@RequestParam(defaultValue = "ASC") String direction,@RequestParam(defaultValue = "0") Integer page ,@RequestParam(defaultValue = "5") Integer size){  
    System.out.println(direction);  
  
    List<Employee> emp = service.findAll(sortby,direction,page,size);  
    List<SimpleEmployeeDTO> dtos = emp.stream().map(employee -> modelMapper.map(employee, SimpleEmployeeDTO.class)).collect(Collectors.toList());  
    return  dtos ;  
  
}
```
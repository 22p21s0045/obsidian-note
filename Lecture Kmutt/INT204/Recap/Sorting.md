### Service
```java
public List<Employee> findAll(String sortby,String direction,Integer page,Integer size){  
    
    Sort sort = Sort.by(sortby);  
    if("DES".equalsIgnoreCase(direction)){  
        return repository.findAll(sort.descending());  
    }  
    else {  
  
        return repository.findAll(sort.ascending());  
    }  
  
  
  
  
}
```
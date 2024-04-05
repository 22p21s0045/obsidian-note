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


final
```java
public List<Employee> findAll(String sortby,String direction,Integer page,Integer size){  
    Sort.Order order = new Sort.Order((direction.equalsIgnoreCase("asc")?Sort.Direction.ASC : Sort.Direction.DESC),sortby);  
  
    System.out.println(sortby);  
  
    
  
  
    if("DES".equalsIgnoreCase(direction)){  
        PageRequest pageRequest = PageRequest.of(page,size,Sort.by(sortby).descending());  
        return repository.findAll(pageRequest).getContent();  
    }  
    else {  
        PageRequest pageRequest = PageRequest.of(page,size,Sort.by(sortby).ascending());  
  
        return repository.findAll(pageRequest).getContent();  
    }  
  
  
  
  
}
```
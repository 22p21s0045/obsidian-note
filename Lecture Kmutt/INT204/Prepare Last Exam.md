```bash
spring.datasource.driver-class-name = com.mysql.jdbc.Driver  
spring.datasource.password= 123456  
spring.datasource.username= root  
spring.datasource.url= jdbc:mysql://localhost:3306/classicmodels  
spring.jpa.hibernate.ddl-auto =none  
spring.jpa.hibernate.naming.physical-strategy = org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
```


# JPA Query method
| Keyword                | Sample                                                        | JPQL snippet                                                       |
| ---------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------ |
| `Distinct`             | `findDistinctByLastnameAndFirstname`                          | `select distinct …​ where x.lastname = ?1 and x.firstname = ?2`    |
| `And`                  | `findByLastnameAndFirstname`                                  | `… where x.lastname = ?1 and x.firstname = ?2`                     |
| `Or`                   | `findByLastnameOrFirstname`                                   | `… where x.lastname = ?1 or x.firstname = ?2`                      |
| `Is`, `Equals`         | `findByFirstname`,`findByFirstnameIs`,`findByFirstnameEquals` | `… where x.firstname = ?1`                                         |
| `Between`              | `findByStartDateBetween`                                      | `… where x.startDate between ?1 and ?2`                            |
| `LessThan`             | `findByAgeLessThan`                                           | `… where x.age < ?1`                                               |
| `LessThanEqual`        | `findByAgeLessThanEqual`                                      | `… where x.age <= ?1`                                              |
| `GreaterThan`          | `findByAgeGreaterThan`                                        | `… where x.age > ?1`                                               |
| `GreaterThanEqual`     | `findByAgeGreaterThanEqual`                                   | `… where x.age >= ?1`                                              |
| `After`                | `findByStartDateAfter`                                        | `… where x.startDate > ?1`                                         |
| `Before`               | `findByStartDateBefore`                                       | `… where x.startDate < ?1`                                         |
| `IsNull`, `Null`       | `findByAge(Is)Null`                                           | `… where x.age is null`                                            |
| `IsNotNull`, `NotNull` | `findByAge(Is)NotNull`                                        | `… where x.age not null`                                           |
| `Like`                 | `findByFirstnameLike`                                         | `… where x.firstname like ?1`                                      |
| `NotLike`              | `findByFirstnameNotLike`                                      | `… where x.firstname not like ?1`                                  |
| `StartingWith`         | `findByFirstnameStartingWith`                                 | `… where x.firstname like ?1` (parameter bound with appended `%`)  |
| `EndingWith`           | `findByFirstnameEndingWith`                                   | `… where x.firstname like ?1` (parameter bound with prepended `%`) |
| `Containing`           | `findByFirstnameContaining`                                   | `… where x.firstname like ?1` (parameter bound wrapped in `%`)     |
| `OrderBy`              | `findByAgeOrderByLastnameDesc`                                | `… where x.age = ?1 order by x.lastname desc`                      |
| `Not`                  | `findByLastnameNot`                                           | `… where x.lastname <> ?1`                                         |
| `In`                   | `findByAgeIn(Collection<Age> ages)`                           | `… where x.age in ?1`                                              |
| `NotIn`                | `findByAgeNotIn(Collection<Age> ages)`                        | `… where x.age not in ?1`                                          |
| `True`                 | `findByActiveTrue()`                                          | `… where x.active = true`                                          |
| `False`                | `findByActiveFalse()`                                         | `… where x.active = false`                                         |
| `IgnoreCase`           | `findByFirstnameIgnoreCase`                                   | `… where UPPER(x.firstname) = UPPER(?1)`                           |



# Sorting and Pagination

```java
@Service  
public class OrderService {  
    @Autowired  
    OrderRepository repository;  
    public Page<Order> findAll(int pageNumber,int pageSize,String sortField, String sortDestination){  
        Sort sort = Sort.by(sortField);  
        if(sortDestination.equalsIgnoreCase("desc")){  
            sort.descending();  
        }  
        else {  
            sort.ascending();  
        }  
        Pageable pageable = PageRequest.of(pageNumber,pageSize,sort);  
        return repository.findAll(pageable);  
    }  
}
```


# Error Exception handle
```java
@ControllerAdvice  
public class ExceptionAdvice {  
    @ExceptionHandler(MethodArgumentTypeMismatchException.class)  
    @ResponseStatus(HttpStatus.BAD_REQUEST)  
    @ResponseBody  
    public ResponseEntity handleTypeMisMatchException(MethodArgumentTypeMismatchException e, WebRequest request){  
        ErrorResponse er = new ErrorResponse(HttpStatus.BAD_REQUEST.value(), "Invalid Parameter " + e.getName() + " must positive number",request.getDescription(false));  
        return ResponseEntity.badRequest().body(er);  
  
  
    }  
  
}
```


# Error Response object
```java

@Getter  
@Setter  
@RequiredArgsConstructor  
@JsonInclude(JsonInclude.Include.NON_NULL)  
public class ErrorResponse {  
    private final int status;  
    private final String message;  
    private final String instance;  
    private String stackTrace;  
    private List<ValidationError> errors;  
  
    @Getter  
    @Setter    @RequiredArgsConstructor    private static class ValidationError {  
        private final String field;  
        private final String message;  
    }  
  
    public void addValidationError(String field, String message) {  
        if (Objects.isNull(errors)) {  
            errors = new ArrayList<>();  
        }  
        errors.add(new ValidationError(field, message));  
    }  
}
```

# Page With DTO

```java
@GetMapping  
    public Page<OrderDto> findAllOrder(@RequestParam(defaultValue = "10") Integer pageNumber, @RequestParam(defaultValue = "10") Integer pageSize, @RequestParam(defaultValue = "id") String sortField, @RequestParam(defaultValue = "asc") String sortDestination) {  
  
  
        if (pageNumber <= 0 || pageSize <= 0) {  
            throw new InvalidParameter("Page Number and Page Size must be positive number");  
        }  
  
  
        Page<Order> orderPage = service.findAll(pageNumber, pageSize, sortField, sortDestination);  
  
        return (Page<OrderDto>) orderPage.map((element) -> mapper.map(element, OrderDto.class));  
  
    }  
}
```


# Install Spring Validation
```xml
<dependency> <groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-validation</artifactId> </dependency>
```
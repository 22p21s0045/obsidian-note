3/12/2024
[Spring Boot @ControllerAdvice & @ExceptionHandler example - BezKoder](https://www.bezkoder.com/spring-boot-controlleradvice-exceptionhandler/)

[Efficient Data Transfer in REST APIs | Stackademic](https://blog.stackademic.com/efficient-data-transfer-in-rest-apis-a-deep-dive-into-the-dto-pattern-with-spring-boot-and-mysql-df2bdf1ece74)


## @NotNull
-  to say that a field must not be null.
## @NotEmpty
-  to say that a list field must not empty.
## @NotBlank
-  to say that a string field must not be the empty string (i.e. it must have at least one character).
## @Min and @Max
- to say that a numerical field is only valid when it's value is above or below a certain value.
## @Pattern
-  to say that a string field is only valid when it matches a certain regular expression.
## @Email
-  to say that a string field must be a valid email address.

## Validate in Service
```java
@Service public class OfficeService {
@Autowired private Validator validator; 
public Office createNewOffice(Office office) {
Errors errors = validator.validateObject(office); 
if (errors.hasErrors()) { 
throw new RuntimeException(errors.toString()); 
} 
return repository.save(office); 

}
```
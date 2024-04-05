```java
import lombok.Getter;  
import org.springframework.http.HttpStatus;  
import org.springframework.web.bind.annotation.ResponseStatus;  
@Getter  
@ResponseStatus(HttpStatus.NOT_FOUND)  
public class ItemNotFoundException extends RuntimeException{  
    private HttpStatus status;  
    private String message;  
    public ItemNotFoundException(String message,HttpStatus status){  
        super(message);  
        this.status = status;  
        this.message = message;  
    }  
  
}
```

### Global exception

```java
@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(UserNotFoundException.class)
    @ResponseStatus(HttpStatus.NOT_FOUND)
    public ResponseEntity<String> handleUserNotFoundException(UserNotFoundException ex) {
        return ResponseEntity.status(HttpStatus.NOT_FOUND).body(ex.getMessage());
    }

    @ExceptionHandler(Exception.class)
    @ResponseStatus(HttpStatus.INTERNAL_SERVER_ERROR)
    public ResponseEntity<String> handleGenericException(Exception ex) {
        return ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR).body("An error occurred");
    }
}

```
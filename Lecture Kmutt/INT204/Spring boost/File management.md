## Config prefix
```java
import org.springframework.boot.context.properties.ConfigurationProperties;  
import org.springframework.context.annotation.Configuration;  
  
@ConfigurationProperties(prefix = "file")  
public class FileStorageProperties {  
    private String uploadDir;  
}
```
- `@ConfigurationProperties(prefix = "file")`: This annotation indicates that this class should be used to bind properties with the prefix `"file"`. In other words, it will look for properties that start with `"file"` in the properties files.
    
- `@Configuration`: This annotation marks the class as a Spring configuration class. It is used to define beans and configurations in a Spring application context.
    
- `private String uploadDir;`: This is a private field `uploadDir` of type `String` that represents the directory where uploaded files will be stored. This field will be populated with the value of the property `file.upload-dir` defined in the properties files.

### Add config in the main
```java
package com.example.imageupload;  
  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  
import org.springframework.boot.context.properties.EnableConfigurationProperties;  
  
@SpringBootApplication  
@EnableConfigurationProperties({  
        FileStorageProperties.class  
})  
public class ImageUploadApplication {  
  
    public static void main(String[] args) {  
        SpringApplication.run(ImageUploadApplication.class, args);  
    }  
  
}
```
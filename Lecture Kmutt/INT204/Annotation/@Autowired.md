@Autowired is an annotation used in Spring Boot to enable <mark style="background: #FFF3A3A6;">automatic dependency </mark>injection. It allows the Spring container to provide an instance of a required dependency when a bean is created. This annotation can be used on fields, constructors, and methods to have Spring provide the dependencies automatically. Dependency injection is a design pattern in which objects are passed their dependencies rather than creating them internally. In Spring Boot, **`@Autowired`** is used to inject objects into other objects. This allows for loose coupling between components and helps to keep code more maintainable.


# @RestController
สำหรับการทำงานกับ JSON ควรใช้ @RESTController แทน @Controller เพื่อทำให้แน่ใจว่า เราจะ return Java Object หรือว่า JSON ไม่ใช่ HTML template
โดยปกติแล้วถ้าเราใช้ @Controller ที่ controller จะทำการไป map และ return HTML template ใน src/main/resources folder และถ้าเราจะให้ return เป็น Java Object หรือว่า JSON ต้องทำการใช้ @Controller ร่วมกับ @ResponseBody เพื่อบอกให้ controller ทำการ return เป็น JSON

#JPA #annotation 
# JPA
## @ Table
 annotation allows you to specify the details of the table that will be used to persist the entity in the database. The @Table annotation provides four attributes, allowing you to override the name of the table, its catalog, and its schema, and enforce unique constraints on columns in the table. For now, we are using just the table name which is EMPLOYEE.

#   @Entity 
Let’s start with the @Entity annotation. This annotation, part of the javax.persistence package, is used at the class level and marks the class as a persistent entity. It signals to the JPA provider that the class should be treated as a table in the database.

# **@Column 
annotation is used for Adding the column the name in the table of a particular MySQL database.**
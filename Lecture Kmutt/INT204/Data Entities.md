This is data JPA mapping entity

#  Customer

```java
@Entity  
@Data  
@Table(name = "customers")  
public class Customer {  
    @Id  
    private Integer customerNumber;  
    private String customerName;  
    private String contactLastName;  
    private String contactFirstName;  
    private String phone;  
    private String addressLine1;  
    private String addressLine2;  
    private String city;  
    private String state;  
    private String postalCode;  
    private String country;  
//    private Integer salesRepEmployeeNumber;  
    @JsonIgnore  
    @ManyToOne  
    @JoinColumn(name = "salesRepEmployeeNumber")  
    private Employee salesRepEmployee;  
  
    private Double creditLimit;  
    @OneToMany(mappedBy = "customerNumber")  
    private List<Order> orderList;  
}
```

# Employee
```java
@Getter  
@Setter  
@Entity  
@Table(name = "employees")  
public class Employee {  
    @Id  
    @Column(name = "employeeNumber", nullable = false)  
    private Integer id;  
  
    @JsonIgnore  
    @ManyToOne  
    @JoinColumn(name = "officeCode")  
    private Office office;  
  
    @Column(name = "lastName", nullable = false, length = 50)  
    private String lastName;  
    @Column(name = "firstName", nullable = false, length = 50)  
    private String firstName;  
    @Column(name = "extension", nullable = false, length = 10)  
    private String extension;  
    @Column(name = "email", nullable = false, length = 100)  
    private String email;  
  
    @JsonIgnore  
    @ManyToOne  
    @JoinColumn(name = "reportsTo")  
    private Employee employees;  
  
    @Column(name = "jobTitle", nullable = false, length = 50)  
    private String jobTitle;  
}
```

# Office
``` java
@Getter  
@Setter  
@Entity  
@Table(name = "offices")  
public class Office {  
    @Id  
    @Column(name = "officeCode", nullable = false, length = 10)  
    private String officeCode;  
    @Column(name = "city", nullable = false, length = 50)  
    private String city;  
    @Column(name = "phone", nullable = false, length = 50)  
    private String phone;  
    @Column(name = "addressLine1", nullable = false, length = 50)  
    private String addressLine1;  
    @Column(name = "addressLine2", length = 50)  
    private String addressLine2;  
    @Column(name = "state", length = 50)  
    private String state;  
    @Column(name = "country", nullable = false, length = 50)  
    private String country;  
    @Column(name = "postalCode", nullable = false, length = 15)  
    private String postalCode;  
    @Column(name = "territory", nullable = false, length = 10)  
    private String territory;  
    @JsonIgnore  
    @OneToMany(mappedBy = "office")  
    private Set<Employee> employees = new LinkedHashSet<>();  
}
```


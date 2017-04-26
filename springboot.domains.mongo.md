# Domains

```bash

package sample.domains;

import org.springframework.data.annotation.Id;


@Document
public class Person {

    @Id
    public String id;
    @NotBlank
    @NotNull(message = "can't be null")
    @Size(max=250)
    @Indexed(unique=true)
    @Length(max = 80)
    private String name;
    private int age;
    
    @DBRef(db="address")
    private List<Address> addresses = new ArrayList<>();
    // getter + setter + toString
  
}


@Document
public class Address {

    @Id
    public String id;
    private String address;
    private String city;
    private String state;
    private long zipcode;
    
  
    // getter + setter + toString
  
}

```
# Domains

```bash

package sample.domains;

import org.springframework.data.annotation.Id;


public class Customer {

    @Id
    public String id;
    public String firstName;
    public String lastName;
    
    // getter + setter + toString
  
}

```
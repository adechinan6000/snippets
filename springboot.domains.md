# Domains

```java

package sample.domains;

import org.springframework.data.annotation.Id;

@Data // for lombock
public class Customer {

    @Id
    public String id;
    public String firstName;
    public String lastName;
  
}

```
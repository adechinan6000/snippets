# Repositories


```java

package sample.repositories;
import java.util.List;
import org.springframework.data.mongodb.repository.MongoRepository;
import org.springframework.data.repository.query.Param;

public interface CustomerRepository extends MongoRepository<Customer, String> {

	public Customer findByFirstName(String firstName);
	public List<Customer> findByLastName(@Param("lastName") String lastName);

}

```
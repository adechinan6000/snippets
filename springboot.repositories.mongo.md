# Repositories


```bash

package sample.repositories;
import java.util.List;
import org.springframework.data.mongodb.repository.MongoRepository;
import org.springframework.data.repository.query.Param;

public interface CustomerRepository extends MongoRepository<Customer, String> {

    // by default this repository have allready crud + natives methods implemented, don't redifined
    // you must just add custom queries
    /*how to use it: in a service or controller call this:
        @Autowired
        private CustomerRepository customerRepository;
        in a method:
        customerRepository.save(...)
        see: springboot.services.md snippets
    */

    /* custom queries add only what you want, not all */
	Customer findByFirstName(String firstName);
	List<Customer> findByLastName(@Param("lastName") String lastName);
	Optional<Customer> findOne(String id);
	List<Person> findByEmailAddressAndLastname(EmailAddress emailAddress, String lastname);
	
    // Enables the distinct flag for the query
    List<Person> findDistinctPeopleByLastnameOrFirstname(String lastname, String firstname);
    List<Person> findPeopleDistinctByLastnameOrFirstname(String lastname, String firstname);
    
    // Enabling ignoring case for an individual property
    List<Person> findByLastnameIgnoreCase(String lastname);
    // Enabling ignoring case for all suitable properties
    List<Person> findByLastnameAndFirstnameAllIgnoreCase(String lastname, String firstname);
    
    // Enabling static ORDER BY for a query
    List<Person> findByLastnameOrderByFirstnameAsc(String lastname);
    List<Person> findByLastnameOrderByFirstnameDesc(String lastname);
    
    // Relationship
    List<Person> findByAddressZipCode(ZipCode zipCode);
    
    // Limiting
    Page<User> queryFirst10ByLastname(String lastname, Pageable pageable);
    Slice<User> findTop3ByLastname(String lastname, Pageable pageable);
    List<User> findFirst10ByLastname(String lastname, Sort sort);
    List<User> findTop10ByLastname(String lastname, Pageable pageable);
    
    // Customise query
    @Query("{ 'firstname' : ?0 }")
    List<Person> findByThePersonsFirstname(String firstname);
    @Query(value="{ 'firstname' : ?0 }", fields="{ 'firstname' : 1, 'lastname' : 1}") 
    List<Person> findByThePersonsFirstname(String firstname);



}

```
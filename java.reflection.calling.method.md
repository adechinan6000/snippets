# Calling methods on object

```java
try {
    Class<Person> personClass = Person.class;
    // person class has setName method with take a string as param so:
    Method setName = personClass.getMethod("setName", String.class);
    Person p = personClass.newInstance();
    setName.invoke(p, "Ann");
    System.out.println(p);
} catch (Exception e) {
    e.printStackTrace();
}
```
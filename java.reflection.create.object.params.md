# Create object with parameters

```bash
try {
    Class cli = Class.forName("Person");
    // constructor of person class take a string and and integer as param so:
    Constructor<Person> cons = cli.getConstructor(String.class, int.class);
    Person chris = cons.newInstance("Chris", 15);
    System.out.println(chris);
}
catch (Exception e) {
}
```
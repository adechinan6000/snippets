# Create object simple

```bash
try {
Class cli = Class.forName("Person"); 
Object o = cli.newInstance();
System.out.println(o);
}
catch (Exception e) {
}
```
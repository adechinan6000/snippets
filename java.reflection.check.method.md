## Checking existance of method

```java
Class a = Class.forName("yourClassName");
Method[] m = a.getMethods();
List<Method> data = Arrays.asList(m);
try {
   System.out.println(data.contains(Woman.class.getMethod("bonna")));
} catch (Exception e) {
   e.printStackTrace();
}
```
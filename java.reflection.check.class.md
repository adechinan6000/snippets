# Checking existance of class

```java
try {
     Class cls = Class.forName("yourClassName"); // or "package1.Test"
} catch (Exception e) {
     e.printStackTrace();
}
```
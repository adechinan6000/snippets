# Checking existance of class

```bash
try {
     Class cls = Class.forName("yourClassName"); // or "package1.Test"
} catch (Exception e) {
     e.printStackTrace();
}
```
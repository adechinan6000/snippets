# Junit

* Create the class under test

```bash
public class MyUnit {

    public String concatenate(String one, String two){
        return one + two;
    }
}
```

* Create a test

```bash
import org.junit.Test;
import static org.junit.Assert.*;

public class MyUnitTest {

    @Test
    public void testConcatenate() {
        MyUnit myUnit = new MyUnit();

        String result = myUnit.concatenate("one", "two");

        assertEquals("onetwo", result);

    }
}
```
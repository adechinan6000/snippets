## Enum


```bash
enum CustomerType {
	INDIVIDUAL, ORGANIZATION
}

public class MyClass {

	public CustomerType customerType = CustomerType.INDIVIDUAL;

	public void test() {
		if (this.customerType == CustomerType.INDIVIDUAL) {
				System.out.println("true");
		}
	}
}
```
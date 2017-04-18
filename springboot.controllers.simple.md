# Simple Controller

```java

@RequestMapping(value = "/", method = RequestMethod.GET)
public String show() {
	return "greeting";
}

```
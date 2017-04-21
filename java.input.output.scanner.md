# Input - output

```bash
Scanner scanner = new Scanner(System.in);
String userInput = scanner.next();
try {
	int i = Integer.valueOf(userInput);
	System.out.println("The number entered: " + i);
	} catch (NumberFormatException e) {
	System.out.println("Invalid user input");
}
```

		
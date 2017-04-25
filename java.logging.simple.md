## loging

```bash
Path debugFile = Paths.get("debug.txt");
OutputStream outputStream = Files.newOutputStream(debugFile, StandardOpenOption.CREATE, StandardOpenOption.APPEND);
PrintStream printStream = new PrintStream(outputStream, true);
System.setOut(printStream);
System.out.println("To file");
try {
	int impo = 1 / 0;
} catch (Exception e) {
	System.setOut(printStream);
	System.out.println(e.getMessage());
}
```
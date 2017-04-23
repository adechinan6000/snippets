# Java write and read file

* making folder and content.txt

```bash
Path newdir = Paths.get("data");
if (!Files.exists(newdir))
Files.createDirectories(newdir);
Path content = Paths.get("data/content.txt");
```

* writing into content.txt

```bash
try (BufferedWriter bufferedWriter = Files.newBufferedWriter(content, StandardCharsets.UTF_8,
				StandardOpenOption.CREATE, StandardOpenOption.APPEND);
				PrintWriter printWriter = new PrintWriter(bufferedWriter)) {
			printWriter.println("PrintWriter is easy to use.");
			printWriter.println(1234);
		}
```

* reading from content.txt

```bash
try (BufferedReader reader = Files.newBufferedReader(Paths.get("data/content.txt"))) {
			reader.lines().map(String::toLowerCase).forEach(System.out::println);
		}
```
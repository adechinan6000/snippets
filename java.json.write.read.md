# Read and write json

* dependencies

```bash
compile group: 'com.googlecode.json-simple', name: 'json-simple', version: '1.1.1'
```

* folder + file

```bash
Path newdir = Paths.get("data");
if (!Files.exists(newdir))
Files.createDirectories(newdir);
Path jsonfile = Paths.get("data/info.json");
```

* create json data

```bash
JSONObject obj = new JSONObject();
obj.put("Name", "crunchify.com");
obj.put("Author", "App Shah");
JSONArray company = new JSONArray();
company.add("Compnay: eBay");
company.add("Compnay: Paypal");
company.add("Compnay: Google");
obj.put("Company List", company);
```

* insert json data

```bash
try (OutputStream outputStream = Files.newOutputStream(jsonfile, StandardOpenOption.CREATE);
				OutputStreamWriter writer = new OutputStreamWriter(outputStream, StandardCharsets.UTF_8)) {
			writer.write(obj.toString());
		}
```

* read json data

```bash
JSONParser parser = new JSONParser();
Object obj2 = parser.parse(new FileReader("data/info.json"));
JSONObject jsonObject = (JSONObject) obj;
String name = (String) jsonObject.get("Name");
String author = (String) jsonObject.get("Author");
JSONArray companyList = (JSONArray) jsonObject.get("Company List");
System.out.println("Name: " + name);
System.out.println("Author: " + author);
System.out.println("\nCompany List:");
Iterator<String> iterator = companyList.iterator();
while (iterator.hasNext()) {
	System.out.println(iterator.next());
}
```
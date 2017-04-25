## Random


 * random number

```bash
Random random = new Random();
System.out.println(random.nextInt(100));
```


 * random string

```bash
byte[] array = new byte[7]; // length is bounded by 7
new Random().nextBytes(array);
String generatedString = new String(array, Charset.forName("UTF-8"));
System.out.println(generatedString);
```


 
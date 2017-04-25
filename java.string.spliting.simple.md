# Java string split


```bash
String text = "Good morning. Have a good class. " +
                 "Have a good visit. Have fun!";
String[] words = text.split("[ \n\t\r.,;:!?(){]");
List<String> list = Arrays.asList(words);
list.stream().forEach(System.out::println);
```
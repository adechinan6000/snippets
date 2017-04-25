## jsoup load url

## dependencies
```bash
compile 'org.jsoup:jsoup:1.10.2'
```


## load url

```bash
Document doc = Jsoup.connect("https://jsoup.org/cookbook/").get();
String title = doc.title();
System.out.println(title);
```
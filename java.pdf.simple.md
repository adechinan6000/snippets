# Pdf

* dependencies

```bash
compile group: 'com.itextpdf', name: 'itextpdf', version: '5.0.6'
```

* usage

```bash
Document document = new Document();
PdfWriter writer = PdfWriter.getInstance(document, new FileOutputStream("HelloWorld.pdf"));
document.open();
document.add(new Paragraph("A Hello World PDF document."));
document.close();
writer.close();
```


* more info

```bash
http://howtodoinjava.com/apache-commons/create-pdf-files-in-java-itext-tutorial/
http://www.vogella.com/tutorials/JavaPDF/article.html
https://www.javacodegeeks.com/2015/06/java-programming-tips-best-practices-beginners.html
```
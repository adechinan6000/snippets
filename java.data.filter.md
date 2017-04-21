# Filter data

* create data
* get stream for data
* handle it

> Filter accepts a predicate to filter all elements of the stream

```bash

// create data
List<String> stringCollection = new ArrayList<>();
stringCollection.add("ddd2");
stringCollection.add("aaa2");

// filter
stringCollection
      .stream() // always stream before anything
      .filter((s) -> s.startsWith("a"))
      .forEach(System.out::println);


```
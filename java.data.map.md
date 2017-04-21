# Map data

> map converts each element into another object via the given function

```bash

        // create data
        List<String> stringCollection = new ArrayList<>();
        stringCollection.add("ddd2");
        stringCollection.add("aaa2");

        // map
        stringCollection
                .stream()
                .map(String::toUpperCase) 
                .forEach(System.out::println);


```
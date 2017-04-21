# Sorted data

> Sorted is an intermediate operation which returns a sorted view of the stream

```bash
// create data
        List<String> stringCollection = new ArrayList<>();
        stringCollection.add("ddd2");
        stringCollection.add("aaa2");

        // sort
        stringCollection
                .stream()
                .map(String::toUpperCase)
                .sorted((a, b) -> b.compareTo(a)) // sorted
                .forEach(System.out::println);

```
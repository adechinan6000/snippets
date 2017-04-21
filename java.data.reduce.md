# Reduce

> This terminal operation performs a reduction on the elements of the stream with the given function

```bash

        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
        
        // reduce 
        int sum = numbers.stream()
                .reduce(0, Integer::sum); // sum all mumbers 
        System.out.println(sum);

```
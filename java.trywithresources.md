## Try with ressources


```bash
try (InputStream is = new FileInputStream("en-token.zip")){
            TokenizerModel model = new TokenizerModel(is);
            TokenizerME tokenizer = new TokenizerME(model);
            String tokens[] = tokenizer.tokenize("Hi. How are you? This is Mike.");
            List<String> list = Arrays.asList(tokens);
            list.stream().forEach(System.out::println);
        } catch (Exception ex) {
            ex.printStackTrace();
        }
```
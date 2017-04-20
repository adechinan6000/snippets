# Read loop data

## Update html tag

```html
<html xmlns:th="http://www.thymeleaf.org">
```

## Display data

```html
<p th:each="post : ${posts}">
	<h4>ID:</h4>
	<div th:text="${post.id}"></div>
	<h4>Title:</h4>
	<div th:text="${post.title}"></div>
	<h4>Content:</h4>
	<div th:text="${post.content}"></div>
	<div>---------------------------------------------------------</div>
</p>
```

## More

*java.thymeleaft.create.loop*
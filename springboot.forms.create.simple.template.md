# template (index)
```html
<form action="#" th:action="@{/}" th:object="${post}" method="post">
	<table>
		<tr>
			<td>Title:</td>
			<td><input type="text" th:field="*{title}" /></td>
			<td th:if="${#fields.hasErrors('title')}" th:errors="*{title}">Title error message</td>
		</tr>
		<tr>
			<td>Content:</td>
			<td><input type="text" th:field="*{content}" /></td>
			<td th:if="${#fields.hasErrors('content')}" th:errors="*{content}">Content error message</td>
		</tr>
		<tr>
			<td><button type="submit">Submit post</button></td>
		</tr>
	</table>
</form>
```

# template (result)
```html
<h4>Title:</h4>
<p th:text="${title}" />
<h4>Content:</h4>
<p th:text="${content}" />
```
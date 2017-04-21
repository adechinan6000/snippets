# Controller

```bash
@RequestMapping(value="/", method=RequestMethod.GET)
public String index(Post post) {
	return "index";
}

@RequestMapping(value = "/", method = RequestMethod.POST)
public String addNewPost(@Valid Post post, BindingResult bindingResult, Model model) {
	if (bindingResult.hasErrors()) {
		return "index";
	}
	model.addAttribute("title", post.getTitle());
	model.addAttribute("content", post.getContent());
	return "result";
}
```
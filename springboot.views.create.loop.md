# Create loop data

```bash
@RequestMapping(value = "/result", method = RequestMethod.GET)
public String showAllPosts(Model model) {
	model.addAttribute("posts", postRepository.findAll());
	return "result";
}
```
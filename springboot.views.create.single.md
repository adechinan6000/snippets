# Create single data

```bash
@RequestMapping("/")
public String hello(Model model) {
    model.addAttribute("message", "Hello from the controller");
    return "greeting"; //resources/templates/greeting.html
}
```


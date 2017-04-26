# Simple Controller

```bash
@Controller
public class User {
@RequestMapping(value = "/", method = RequestMethod.GET)
public String show() {
	return "greeting";
}
}
```
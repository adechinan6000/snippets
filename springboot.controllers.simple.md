# Simple Controller

```bash

@RequestMapping(value = "/", method = RequestMethod.GET)
public String show() {
	return "greeting";
}

```
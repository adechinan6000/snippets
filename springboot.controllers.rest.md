# Controller

```java
@RestController
public class DepartmentController {

	@Autowired
	private DepartmentService departmentService;
	
	@RequestMapping(value="/departments", method=RequestMethod.GET)
	public Iterable<Department> getAll() {
		return this.departmentService.getAll();
	}
	
    @RequestMapping(value="/departments/{id}", method=RequestMethod.GET)
    public Clas get(@PathVariable int id) {
	    return this.departmentService.get(id);
    }
	
	@RequestMapping(value="/departments", method=RequestMethod.POST)
	public void add(@RequestBody Department department) {
		this.departmentService.add(department);	
	}
	
	@RequestMapping(value="/departments{id}", method=RequestMethod.PUT)
	public void edit(@PathVariable int id, @RequestBody Department department) {
		this.departmentService.edit(id, department);
		
	}
	
	@RequestMapping(value="/departments{id}", method=RequestMethod.DELETE)
	public void delete(@PathVariable int id) {
		this.departmentService.delete(id);
	}
	
    @RequestMapping(value = "/path/{id}", , method=RequestMethod.GET)
    public String getResource(@PathVariable Optional<String> id) {
      if (id.isPresent()) {
        return service.processResource(id.get());
      } else {
        return service.processResource();
      }
    }

}

```
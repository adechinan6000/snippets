## Spring boot services


```bash
@Service
public class DepartmentService {


	@Autowired
	private DepartmentRepository departmentRepository;

	public Iterable<Department> getAll() {
		return this.departmentRepository.findAll();
	}

	public Department get(int id) {
		return this.departmentRepository.findOne(id);
	}

	public void add(Department department) {
		this.departmentRepository.save(department);
	}

	public void edit(int id, Department department) {
		this.departmentRepository.save(department);

	}

	public void delete(int id) {
		this.departmentRepository.delete(id);
	}
	
	
}

```
# Uploading


```bash
@Controller
public class UploadingController {
	public static final String uploadingdir = "uploads"; // same level as src folder

	@RequestMapping("/")
	public String uploading(Model model) {
		File file = new File(uploadingdir);
		model.addAttribute("files", file.listFiles());
		return "uploading";
	}

	@RequestMapping(value = "/", method = RequestMethod.POST)
	public String uploadingPost(@RequestParam("uploadingFiles") MultipartFile[] uploadingFiles) throws IOException {
		for (MultipartFile uploadedFile : uploadingFiles) {
			File file = new File(uploadingdir + uploadedFile.getOriginalFilename());
			uploadedFile.transferTo(file);
		}

		return "redirect:/";
	}
}
```
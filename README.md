# 419.-Passando-Par-metros-para-Web-Service
Consulta ID de usuário direto na URL ex. http://localhost:8080/clientes?id=123
_______________________________________
INICIO
import com.example.exerciciossb.models.Cliente;

@RestController
@RequestMapping(path = "/clientes")
public class ClienteController {
	
	@GetMapping(path = "/clientes/qualquer")
	public Cliente obterCliente() {
		return new Cliente(28, "Pedro", "123.456.789-00");
	}
	
	@GetMapping("/{id}")
	public Cliente obterClientePorId1(@PathVariable int id) {
		return new Cliente(id, "Maria", "987.654.321-00");
	}
	
	@GetMapping // esse é o exemplo que deve ser usado
	public Cliente obterClientePorId2(@RequestParam(name = "id") int id) {
		return new Cliente(id, "Joao Augusto", "111.222.333-44");
	}
}
![image](https://user-images.githubusercontent.com/95525963/154379623-f41c5f3f-ef1f-4ccb-b105-fcd39564a199.png)

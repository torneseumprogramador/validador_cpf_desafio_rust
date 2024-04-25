# Validador CPF
### Este componente para validar cpf foi criado no desafio de rust na comunidade do https://www.torneseumprogramador.com.br na aula 32, para rever o conteúdo, acesse o link abaixo:

Todas as aulas:
- https://www.torneseumprogramador.com.br/cursos/desafio_rust/aulas

Como utilizar ? <br>
No arquivo ( Cargo.toml ) <br>
Adicionar o codigo abaixo

```
[dependencies]
validar_cpf = "1.0.2"
```

Como utilizar em seu código Rust
```rust
use validar_cpf as validador;
use std::io;

fn main() {
    println!("Digite um CPF");

    let mut cpf = String::new();

    match io::stdin().read_line(&mut cpf) {
        Ok(_) => {
            println!("Você digitou: {}", cpf.trim());
        },
        Err(e) => {
            println!("Erro ao ler entrada: {}", e);
        }
    }

    let validado: bool = validador::validar_cpf::cpf(cpf.as_str());

    if validado {
        println!("O CPF é valido")
    } else {
        println!("O CPF é inválido")
    }
}
```

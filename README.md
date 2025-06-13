# Web Go

Este repositório contém um exemplo simples de aplicação web escrita em Go (Golang).
O projeto segue o padrão MVC (Models, Views e Controllers) e utiliza
PostgreSQL para persistência dos dados.

## Estrutura

- **controllers/** &ndash; lógica das requisições HTTP.
- **models/** &ndash; manipulação e acesso a dados.
- **routes/** &ndash; define as rotas e associações aos controllers.
- **db/** &ndash; conexão com o banco PostgreSQL.
- **templates/** &ndash; arquivos HTML utilizados nas páginas.

## Configuração

1. Ajuste as credenciais do banco em `db/db.go` de acordo com a sua
   instalação do PostgreSQL.
2. Certifique‑se de que o banco possua uma tabela `produtos` com os campos
   `id`, `nome`, `descricao`, `preco` e `quantidade`.
3. Instale as dependências do projeto (por exemplo o driver
   `github.com/lib/pq`).

## Execução

Crie um arquivo `main.go` para iniciar o servidor HTTP. Um exemplo simples:

```go
package main

import (
    "net/http"

    "github.com/PedroAndriola/web-go/routes"
)

func main() {
    routes.CarregaRotas()
    http.ListenAndServe(":8000", nil)
}
```

Depois de criar o arquivo, execute:

```bash
$ go run main.go
```

A aplicação ficará disponível em `http://localhost:8000`.

## Licença

Distribuído sob a licença MIT. Veja o arquivo `LICENSE` para mais informações.


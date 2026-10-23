## Processo Unificado (UP)

O Processo Unificado (UP) adota o desenvolvimento de software baseado em componentes. O sistema é construído pela composição de componentes conectados por interfaces bem definidas.

O UP também utiliza desenvolvimento iterativo e incremental. Para identificar as funções do sistema, aplica uma abordagem baseada em cenários: o modelo de casos de uso.

## RUP

O Rational Unified Process (RUP) é uma instanciação mais específica do UP. Entre as práticas associadas ao processo estão:

- Desenvolvimento iterativo.
- Gerenciamento de requisitos.
- Uso de arquitetura e componentes.
- Integração contínua do trabalho da equipe.

### Anotação de aula

Na atividade sobre conflito e refatoração, foi indicado o nível de capacidade 2.

## UML

A UML (Unified Modeling Language) é uma linguagem visual usada para representar e modelar sistemas, especialmente sistemas orientados a objetos. Seus diagramas ajudam a visualizar diferentes aspectos do software.

A UML não define as fases de um processo de desenvolvimento nem determina quando cada diagrama deve ser usado. Ela fornece notações gráficas para representar o sistema.

## Exemplo: sistema de empréstimo de livros

O sistema permite que leitores pesquisem o acervo, consultem a disponibilidade e solicitem empréstimos. O bibliotecário administra os livros e registra empréstimos e devoluções. O sistema controla os prazos, atualiza a disponibilidade e permite consultar atrasos.

### Visão geral

```mermaid
flowchart LR
	leitor[Leitor]
	bibliotecario[Bibliotecario]

	subgraph Sistema de emprestimo de livros
		portal[Portal da biblioteca]
		acervo[Consulta e gestao do acervo]
		emprestimos[Gestao de emprestimos e devolucoes]
	end

	dados[(Livros, leitores e emprestimos)]

	leitor -->|Pesquisa e solicita emprestimos| portal
	bibliotecario -->|Administra livros e operacoes| portal
	portal --> acervo
	portal --> emprestimos
	acervo <--> dados
	emprestimos <--> dados
```

### Diagrama de casos de uso

```mermaid
flowchart LR
	leitor[Leitor]
	bibliotecario[Bibliotecario]
	sistema((Sistema de emprestimo de livros))

	leitor -->|Pesquisar livros| sistema
	leitor -->|Solicitar emprestimo| sistema
	leitor -->|Consultar emprestimos| sistema
	leitor -->|Solicitar devolucao| sistema
	bibliotecario -->|Cadastrar e atualizar livros| sistema
	bibliotecario -->|Registrar emprestimo e devolucao| sistema
	bibliotecario -->|Consultar atrasos| sistema
```

### Diagrama de sequência: solicitação de empréstimo

```mermaid
sequenceDiagram
	actor Leitor
	participant Sistema
	participant Catalogo
	participant Bibliotecario

	Leitor->>Sistema: Pesquisa um livro
	Sistema->>Catalogo: Consulta disponibilidade
	Catalogo-->>Sistema: Informa disponibilidade
	Sistema-->>Leitor: Exibe resultado da pesquisa
	Leitor->>Sistema: Solicita emprestimo
	Sistema->>Catalogo: Verifica disponibilidade
	Catalogo-->>Sistema: Livro disponivel
	Sistema->>Bibliotecario: Envia solicitacao para registro
	Bibliotecario->>Sistema: Confirma emprestimo e prazo
	Sistema->>Catalogo: Atualiza situacao do livro
	Sistema-->>Leitor: Informa confirmacao e prazo de devolucao
```

## Diagrama de componentes: loja online

Neste exemplo, a loja online é dividida em componentes com responsabilidades distintas. A interface recebe as ações do cliente e utiliza os serviços de catálogo, carrinho e pedidos. A gestão de pedidos coordena o pagamento, a atualização do estoque, o envio e as notificações. O provedor de pagamento e o serviço de entrega são sistemas externos integrados à loja.

```mermaid
flowchart LR
	cliente[Cliente]

	subgraph Loja online
		interface[[Componente: Interface web ou aplicativo]]
		catalogo[[Componente: Catalogo de produtos]]
		carrinho[[Componente: Carrinho de compras]]
		pedidos[[Componente: Gestao de pedidos]]
		estoque[[Componente: Controle de estoque]]
		notificacoes[[Componente: Notificacoes]]
		dados[(Banco de dados)]
	end

	pagamento[[Provedor externo de pagamento]]
	entrega[[Servico externo de entrega]]

	cliente --> interface
	interface --> catalogo
	interface --> carrinho
	interface --> pedidos
	catalogo --> dados
	carrinho --> dados
	pedidos --> dados
	pedidos -.->|Solicita autorizacao| pagamento
	pagamento -.->|Resultado do pagamento| pedidos
	pedidos --> estoque
	estoque --> dados
	pedidos -.->|Solicita envio| entrega
	entrega -.->|Codigo de rastreio| pedidos
	pedidos --> notificacoes
	notificacoes -->|Confirmacao e atualizacoes| cliente
```

As linhas contínuas representam as conexões entre partes internas da loja. As linhas pontilhadas destacam as integrações com os serviços externos de pagamento e entrega. O estilo da linha não indica se uma conexão é obrigatória ou opcional: isso depende das regras e dos requisitos do sistema.

**Fluxo principal:** o cliente escolhe os produtos, monta o carrinho e confirma o pedido. A loja solicita o pagamento e, após a aprovação, registra o pedido, atualiza o estoque, solicita a entrega e envia uma confirmação ao cliente.

## Diagrama de classes: sistema de empréstimo

O diagrama abaixo apresenta classes e alguns de seus atributos e métodos. As relações mostram que um leitor pode realizar empréstimos, e cada empréstimo se refere a um livro e é registrado por um bibliotecário.

```mermaid
classDiagram
  class Leitor {
    +nome: String
    +rgm: String
    +email: String
    +solicitarEmprestimo(livro: Livro): void
    +consultarEmprestimos(): List<Emprestimo>
  }

  class Bibliotecario {
    +nome: String
    +matricula: String
    +email: String
    +cadastrarLivro(livro: Livro): void
    +registrarEmprestimo(emprestimo: Emprestimo): void
  }

  class Livro {
    +titulo: String
    +autor: String
    +isbn: String
  }

  class Emprestimo {
    +dataEmprestimo: Date
    +dataDevolucao: Date
    +status: String
  }

	Leitor "1" --> "0..*" Emprestimo : realiza
	Emprestimo "0..*" --> "1" Livro : inclui
	Bibliotecario "1" --> "0..*" Emprestimo : registra
```

## Diagrama de atividade: solicitação de empréstimo

O fluxo começa com a pesquisa do livro. Se houver exemplar disponível e o leitor estiver apto a emprestar, o bibliotecário registra a operação, o sistema atualiza o acervo e informa o prazo de devolução. Caso contrário, o leitor recebe uma mensagem explicando que o empréstimo não pode ser concluído.

```mermaid
flowchart TD
		inicio([Início]) --> pesquisar[Leitor pesquisa um livro]
		pesquisar --> consultar[Sistema consulta a disponibilidade do acervo]
		consultar --> disponivel{Há exemplar disponível?}
		disponivel -->|Nao| indisponivel[Informar que o livro nao esta disponivel]
		indisponivel --> fim([Fim])
		disponivel -->|Sim| validar[Bibliotecario valida o cadastro do leitor]
		validar --> apto{Leitor esta apto a emprestar?}
		apto -->|Nao| recusado[Informar o motivo da recusa]
		recusado --> fim
		apto -->|Sim| registrar[Registrar o emprestimo e o prazo de devolucao]
		registrar --> atualizar[Atualizar a disponibilidade do livro]
		atualizar --> confirmar[Confirmar o emprestimo ao leitor]
		confirmar --> fim
```

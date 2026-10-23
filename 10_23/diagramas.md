o processo unificado UP adota o desenvolvimento de software baseado em componentes, ou seja, preve que o sistema de software pode ser construído
através da composição de componentes de softwares interconectados através de interfaces bem definidas. seg pressman seguindo a UML o processo unificado define os componentes
de software qye serão usados para construir o sistema e as interfaces.
maneira mais facil de visualizar o software inteiro em formato grafico.
o UP adota desenvolvimento iterativo e incremental e define as funções do sistema aplicando uma abordagem baseada em cenários denominada modelo de casos de uso.

---

RUP é uma instancia mais especifica do UP e as melhores paticas de processos de software incorporadas nestes processos de software incorporadas neste processo são Pressman e sommervile
desenvolvimento iterativo;
gerencia de requisitos;
utilização de arquitetura e componentes;
exemplo de rup

---

qual nivel de capacidade da mais confilto, refatoração 2

---

UML define a representação gráfica que deve ser utilizada pra modelar sistemas orientados a objeto, através de grafos. Ela não define fases ou como a linguagem deve ser utilizada ao logno das fases
do processo n e metodologia, so apresenta maneiras de mostrar o seu sistema de maneiras mais intuitiva.
grafos-parte matematica + parte visual.

---

exemplo de UML:
visao geral do sistema de emprestimo de livros

O sistema permite que leitores pesquisem o acervo, consultem a disponibilidade e solicitem emprestimos. O bibliotecario administra os livros e confirma emprestimos e devolucoes. O sistema registra os prazos, atualiza a disponibilidade e permite consultar emprestimos em atraso.

### Visao geral do sistema

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

### Diagrama de sequencia: solicitacao de emprestimo

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

### Diagrama de componentes: compras online

Neste exemplo, a loja online e dividida em componentes com responsabilidades distintas. A interface recebe as acoes do cliente e utiliza os servicos de catalogo, carrinho e pedidos. O componente de pedidos coordena o pagamento, a baixa de estoque, o envio e as notificacoes. O provedor de pagamento e o servico de entrega sao sistemas externos integrados a loja.

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
	pedidos -->|Solicita autorizacao| pagamento
	pagamento -->|Resultado do pagamento| pedidos
	pedidos --> estoque
	estoque --> dados
	pedidos -->|Solicita envio| entrega
	entrega -->|Codigo de rastreio| pedidos
	pedidos --> notificacoes
	notificacoes -->|Confirmacao e atualizacoes| cliente
```

Fluxo principal: o cliente escolhe produtos, monta o carrinho e confirma o pedido. A loja solicita o pagamento; se aprovado, registra o pedido, atualiza o estoque, solicita a entrega e envia a confirmacao ao cliente.
quando a linha é solida, significa que o componente faz parte da loja online e interage com outros componentes internos.
quando a linha é pontilhada, significa que o componente é externo e nao faz parte da loja online, mas interage com ela. Ou seja,
a pontilhada é opcional, mas a solida é obrigatoria.

diagrama de objetos: solicitacao de emprestimo

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

```

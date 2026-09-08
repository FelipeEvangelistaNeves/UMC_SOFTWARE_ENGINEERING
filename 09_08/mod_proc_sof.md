# Modelo de Processo de Software

Um modelo de processo de software é uma representação simplificada do conjunto
de atividades, regras, responsabilidades e recursos usados para desenvolver um
software.

Ele estabelece:

- quem faz: pessoas com habilidades, treinamento, experiência e motivação;
- o que e quando: procedimentos e métodos, definindo as tarefas, a ordem das
  atividades e os relacionamentos entre elas;
- como: ferramentas, equipamentos, técnicas e tecnologias utilizadas no
  desenvolvimento.

Em outras palavras, o modelo de processo orienta como a equipe organiza o
trabalho para transformar uma ideia em um produto de software funcionando,
com qualidade, dentro do prazo e do custo previstos.

## Importância do modelo de processo

O modelo de processo ajuda a:

- definir papéis e responsabilidades;
- organizar as etapas do desenvolvimento;
- controlar prazos e entregas;
- reduzir erros e retrabalho;
- facilitar a comunicação entre a equipe;
- melhorar a qualidade do produto final.

## Principais modelos

### Modelo em cascata

Esse modelo segue uma sequência linear e rígida. As etapas são executadas uma
depois da outra, e normalmente cada fase precisa ser concluída antes que a
próxima comece.

As etapas principais são:

1. Levantamento de requisitos: a equipe identifica o que o sistema precisa fazer.
2. Análise: os requisitos são estudados para entender melhor o problema.
3. Projeto: define-se a arquitetura, a estrutura do sistema e as regras de desenvolvimento.
4. Implementação: os programadores codificam o sistema.
5. Testes: verificam-se erros, falhas e inconsistências.
6. Implantação: o sistema é entregue para uso.
7. Manutenção: ajustes, correções e melhorias são realizadas após a entrega.

Esse modelo é adequado para projetos com requisitos bem definidos e pouco
susceptíveis a mudanças, como sistemas mais estáveis ou regulamentados.

Exemplo visual:

```text
REQUISITOS -> ANALISE -> PROJETO -> IMPLEMENTAÇÃO -> TESTES -> IMPLANTAÇÃO -> MANUTENÇÃO
```

### Modelo incremental

No modelo incremental, o sistema é desenvolvido por partes. Em vez de entregar
tudo de uma vez, a equipe cria versões que vão sendo ampliadas e melhoradas ao
longo do tempo.

Etapas típicas:

1. Definição dos requisitos gerais do sistema.
2. Criação do primeiro incremento, com um conjunto inicial de funcionalidades.
3. Entrega do incremento para avaliação.
4. Ajustes com base no feedback e novas necessidades.
5. Desenvolvimento de novos incrementos com mais recursos e melhorias.
6. Repetição do processo até que o sistema esteja completo.

Esse modelo permite entregar valor mais cedo e reduzir riscos, porque o cliente
passa a usar partes do sistema antes da conclusão total.

Exemplo visual:

```text
Versão 1 -> Versão 2 -> Versão 3 -> Versão 4
   |            |            |            |
Func. A     Func. B     Func. C     Func. D
```

### Modelo iterativo

O modelo iterativo repete ciclos de trabalho. A cada iteração, a equipe revisa,
ajusta e refinamento o sistema, aprendendo mais sobre o problema e sobre a
solução ao longo do tempo.

Etapas comuns:

1. Planejamento inicial do que será abordado na iteração.
2. Análise do problema e dos requisitos da etapa.
3. Desenvolvimento da solução parcial.
4. Testes e avaliação do que foi criado.
5. Ajustes com base nos resultados.
6. Nova iteração com melhorias e refinamentos.

Esse modelo é útil quando o problema é complexo e exige aprendizado contínuo.

Exemplo visual:

```text
      +--------------------+
      |    Iteração 1      |
      | análise + build    |
      +---------+----------+
                |
                v
      +--------------------+
      |    Iteração 2      |
      | revisão + ajuste    |
      +---------+----------+
                |
                v
      +--------------------+
      |    Iteração 3      |
      | melhoria + teste    |
      +--------------------+
```

### Modelo ágil

O modelo ágil trabalha com entregas curtas e frequentes. O foco é colaborar
com o cliente, responder rapidamente às mudanças e entregar valor em pequenas
partes.

Etapas típicas do modelo ágil:

1. Planejamento da próxima entrega.
2. Revisão dos requisitos prioritários.
3. Desenvolvimento em ciclos curtos chamados sprints.
4. Testes contínuos e acompanhamento do progresso.
5. Reunião com o cliente para validar o resultado.
6. Ajustes e refinamentos para a próxima iteração.
7. Nova entrega com mais valor ao cliente.

Esse modelo é muito usado em projetos dinâmicos, com mudanças frequentes e
necessidade de rapidez.

Exemplo visual:

```text
Sprint 1   Sprint 2   Sprint 3   Sprint 4
   |          |          |          |
   v          v          v          v
Planejar -> Desenvolver -> Testar -> Entregar
```

## Escolha do modelo

A escolha depende da estabilidade dos requisitos, do nível de risco, do grau
de inovação, das exigências de qualidade e da participação disponível dos
usuários. Projetos diferentes podem combinar práticas de mais de um modelo.

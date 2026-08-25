# Requisitos de Software

Requisitos são necessidades, capacidades ou condições que um sistema deve
atender. Eles orientam o desenvolvimento e servem como base para verificar se
o produto foi construído corretamente.

## Requisitos funcionais

Requisitos funcionais descrevem **o que o sistema deve fazer**. Eles definem
as funções, serviços e comportamentos esperados do software.

Exemplos:

- o sistema deve permitir cadastrar usuários;
- o usuário deve poder fazer login e sair da conta;
- o sistema deve permitir incluir produtos em um carrinho;
- o sistema deve calcular o valor total de uma compra;
- o sistema deve enviar um aviso após a confirmação do pedido;
- o administrador deve poder gerar relatórios de vendas.

Um requisito funcional deve ser específico e poder ser verificado por meio de
testes. Em vez de escrever apenas “o sistema deve funcionar”, é melhor indicar
qual ação será realizada, por quem e qual resultado deve ser produzido.

## Requisitos não funcionais

Requisitos não funcionais descrevem **como o sistema deve funcionar**. Eles
definem características de qualidade, restrições e padrões que o sistema deve
respeitar, mesmo quando não representam uma funcionalidade específica.

### Segurança

O sistema deve proteger dados e impedir acessos indevidos. Exemplos:

- exigir autenticação para acessar informações privadas;
- permitir diferentes níveis de acesso;
- armazenar senhas de forma segura;
- registrar tentativas de acesso e alterações importantes.

### Desempenho e velocidade

O sistema deve responder dentro de um tempo aceitável e suportar a quantidade
esperada de usuários. Por exemplo: “a tela de consulta deve ser carregada em
até dois segundos para até 500 usuários simultâneos”.

### Usabilidade e aparência

O sistema deve ser fácil de aprender e utilizar, com telas organizadas,
linguagem clara, boa legibilidade e navegação consistente. A aparência deve
ser traduzida em critérios objetivos, como contraste adequado, adaptação a
celulares e mensagens de erro compreensíveis.

### Confiabilidade e disponibilidade

O sistema deve operar corretamente, evitar perda de dados e continuar
disponível pelo período esperado. Também deve possuir mecanismos de recuperação
em caso de falha.

### Manutenibilidade

O software deve ser organizado de modo que correções e melhorias possam ser
realizadas com segurança e esforço controlado.

## Diferença entre os tipos

| Requisitos funcionais                     | Requisitos não funcionais                        |
| ----------------------------------------- | ------------------------------------------------ |
| Definem o que o sistema faz               | Definem como o sistema deve operar               |
| Descrevem ações e comportamentos          | Descrevem qualidade e restrições                 |
| São verificados por resultados funcionais | São verificados por métricas, inspeções e testes |
| Exemplo: cadastrar um cliente             | Exemplo: proteger os dados do cliente            |

Os dois tipos são complementares. Um sistema pode possuir todas as funções
esperadas, mas ainda ser inadequado se for lento, inseguro ou difícil de usar.

## Boas características de um requisito

Um requisito deve ser:

- claro e sem ambiguidades;
- necessário para o negócio ou para o usuário;
- possível de implementar com os recursos disponíveis;
- testável e mensurável;
- rastreável até sua origem;
- priorizado conforme seu valor e sua urgência.

Durante o projeto, os requisitos podem ser revisados com os interessados. Toda
alteração deve ser analisada porque pode afetar o escopo, o prazo, o custo e a
qualidade do produto.

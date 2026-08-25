# Processo de Software

Um processo de software é um conjunto organizado de atividades utilizadas para
planejar, desenvolver, entregar e manter um sistema. O processo pode variar
conforme o tipo de produto, o tamanho da equipe e os riscos do projeto.

## 1. Especificação

Consiste em entender e documentar as necessidades do cliente, dos usuários e
das demais partes interessadas. Nessa etapa ocorre a **elicitação de
requisitos**, que reúne técnicas para descobrir e coletar informações de forma
detalhada.

Algumas técnicas de elicitação são:

- entrevistas;
- questionários;
- observação do trabalho dos usuários;
- análise de documentos e sistemas existentes;
- reuniões e workshops;
- protótipos e validações com usuários.

Depois da coleta, os requisitos são analisados, organizados, priorizados e
documentados. Também devem ser identificadas ambiguidades, conflitos,
dependências e restrições.

## Analogia do restaurante

A especificação pode ser comparada ao atendimento em um restaurante. O cliente
explica o que deseja, o atendente faz perguntas para esclarecer detalhes e o
pedido é registrado antes de ser preparado.

- **Cliente:** representa o usuário ou a organização que possui uma necessidade.
- **Atendente:** representa a pessoa que realiza a elicitação e esclarece o pedido.
- **Pedido:** representa os requisitos documentados.
- **Cozinha:** representa a equipe que projeta e desenvolve o software.
- **Prato entregue:** representa o produto ou incremento disponibilizado.
- **Degustação e avaliação:** representam os testes e a validação com o cliente.

Se o pedido for apenas “quero uma refeição”, haverá grande chance de erro. Da
mesma forma, um requisito vago, como “o sistema deve ser bom”, precisa ser
detalhado em funções e critérios de qualidade verificáveis.

## 2. Projeto e Implementação

### Projeto

No projeto, os requisitos são transformados em uma solução técnica. A equipe
define como o sistema será estruturado e como seus componentes irão trabalhar
juntos.

As principais atividades são:

- definir a arquitetura do sistema;
- escolher linguagens, ferramentas e tecnologias;
- modelar o banco de dados;
- definir interfaces e integrações;
- elaborar fluxos, telas e protótipos;
- estabelecer padrões de segurança e qualidade.

O resultado dessa etapa é uma descrição suficientemente detalhada para orientar
a construção do software.

### Implementação

Na implementação, os Desenvolvedores transformam o projeto em código e outros
artefatos executáveis. Eles criam as funcionalidades, configuram ambientes,
integram componentes e realizam testes durante o desenvolvimento.

Boas práticas nessa etapa incluem controle de versão, revisão de código,
integração frequente e documentação das decisões importantes.

## 3. Testes e validação

Os testes verificam se o software foi construído corretamente e se atende às
necessidades definidas nos requisitos. A validação também confirma se a solução
é útil e adequada para os usuários.

Podem ser realizados:

- testes unitários, que verificam pequenas partes do código;
- testes de integração, que verificam a comunicação entre componentes;
- testes de sistema, que avaliam o software completo;
- testes de desempenho, segurança e usabilidade;
- testes de aceitação com o cliente ou usuários.

Quando uma falha é encontrada, ela deve ser registrada, analisada, corrigida e
testada novamente. A etapa termina quando os critérios de aceitação são
atendidos e o produto possui qualidade suficiente para ser disponibilizado.

## 4. Implantação

Implantação é a disponibilização do software no ambiente em que será utilizado.
Essa etapa pode envolver:

- preparação de servidores, dispositivos e redes;
- configuração de banco de dados e serviços;
- instalação e publicação da aplicação;
- migração ou conversão de dados;
- treinamento dos usuários;
- elaboração de manuais e procedimentos de suporte;
- acompanhamento inicial após a liberação.

Em alguns casos, a implantação é feita gradualmente ou por meio de um projeto
piloto. Assim, a equipe consegue observar os resultados e reduzir os riscos
antes de disponibilizar o sistema para todos.

## 5. Operação

Na operação, o software é utilizado no dia a dia para apoiar as atividades da
organização. A equipe acompanha seu funcionamento, disponibilidade, desempenho,
segurança e capacidade.

Também são monitorados incidentes, erros, uso dos recursos e opiniões dos
usuários. Essas informações ajudam a identificar necessidades de correção e
melhoria.

## 6. Manutenção e evolução

A manutenção acontece depois da implantação e mantém o software útil e
confiável ao longo do tempo. Ela pode ser:

- **corretiva:** corrige falhas encontradas em produção;
- **adaptativa:** adapta o software a novas leis, plataformas ou ambientes;
- **evolutiva:** acrescenta funcionalidades e melhorias;
- **preventiva:** reduz a chance de falhas futuras e facilita a manutenção.

Cada alteração deve ser analisada, priorizada, desenvolvida, testada e
implantada de forma controlada. A manutenção pode gerar novas versões e novos
ciclos de requisitos, projeto, implementação e testes.

## 7. Descontinuação

A descontinuação ocorre quando o software deixa de ser utilizado ou é
substituído. Essa decisão pode acontecer porque o sistema ficou obsoleto,
deixou de atender ao negócio, tornou-se caro de manter ou foi substituído por
uma solução melhor.

O encerramento deve ser planejado para:

- comunicar a mudança aos usuários;
- migrar ou preservar os dados necessários;
- manter registros e cumprir obrigações legais;
- retirar o sistema dos ambientes de produção;
- cancelar serviços e contratos relacionados;
- oferecer suporte durante a transição.

## Atividades contínuas

Algumas atividades acompanham todo o processo de software, como gerenciamento
de riscos, controle de qualidade, gestão de configuração, documentação,
segurança, acompanhamento de custos e comunicação com as partes interessadas.

## Processo incremental

As etapas não precisam ocorrer apenas uma vez nem sempre em uma sequência
rigidamente linear. Em modelos iterativos e ágeis, a equipe repete partes do
processo em ciclos curtos: entende uma necessidade, projeta, implementa, testa,
entrega e obtém feedback. Esse retorno pode alterar os requisitos e orientar o
próximo ciclo.

## Análise da analogia do restaurante

A analogia do restaurante ajuda a entender que desenvolver software não é
apenas escrever código. Existe um processo completo para compreender a
necessidade, preparar uma solução, conferir sua qualidade e atender às
expectativas do usuário.

| Etapa do software | Exemplo no restaurante                                               | Objetivo                         |
| ----------------- | -------------------------------------------------------------------- | -------------------------------- |
| Especificação     | O cliente explica o que deseja e informa restrições, como alergias   | Entender a necessidade           |
| Projeto           | O cozinheiro escolhe a receita, os ingredientes e a forma de preparo | Planejar a solução               |
| Implementação     | A equipe prepara o prato                                             | Construir o produto              |
| Testes            | O cozinheiro confere sabor, aparência e temperatura                  | Verificar a qualidade            |
| Validação         | O cliente experimenta e confirma se o pedido foi atendido            | Confirmar a satisfação           |
| Implantação       | O prato é servido à mesa                                             | Disponibilizar o resultado       |
| Operação          | O cliente consome a refeição                                         | Utilizar o produto               |
| Manutenção        | O restaurante corrige um pedido ou adapta a receita                  | Corrigir e melhorar              |
| Descontinuação    | O prato sai do cardápio                                              | Encerrar ou substituir a solução |

### O que a analogia demonstra

Se o cliente não explicar adequadamente o pedido, o restaurante pode preparar
algo diferente do esperado. Da mesma forma, requisitos incompletos ou ambíguos
podem levar a equipe de software a desenvolver uma solução inadequada.

Também é possível perceber que qualidade não depende apenas do resultado final.
No restaurante, são importantes os ingredientes, o preparo, a higiene, o
tempo de atendimento e a apresentação. No software, além das funcionalidades,
também são importantes segurança, desempenho, usabilidade, confiabilidade e
manutenibilidade.

### Feedback e adaptação

Em um processo tradicional, o pedido pode ser preparado e entregue de uma vez.
Em um processo ágil, o atendimento é mais colaborativo: o cliente pode provar
uma parte do prato, informar o que precisa ser ajustado e receber uma nova
versão. Cada ciclo de feedback melhora o resultado final.

### Limite da analogia

A comparação facilita a compreensão, mas não representa todas as situações de
um projeto de software. Um sistema pode possuir integrações, regras de negócio,
usuários simultâneos, riscos de segurança e manutenção por muitos anos. Por
isso, a analogia deve ser usada como uma forma inicial de visualizar o processo,
complementada por técnicas de engenharia de software.

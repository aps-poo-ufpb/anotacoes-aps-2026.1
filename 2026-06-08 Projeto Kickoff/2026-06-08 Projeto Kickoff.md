---
feature: projetos/UFPB.2026.1/APS2026.1/anotacoes-aps-2026.1/2026-06-08 Projeto Kickoff/attachments/2026-06-08 Projeto Kickoff 2026-06-08 08.24.34.excalidraw.svg
---
![](attachments/2026-06-08%20Projeto%20Kickoff%202026-06-08%2008.24.34.excalidraw.svg)
%%[🖋 Edit in Excalidraw](attachments/2026-06-08%20Projeto%20Kickoff%202026-06-08%2008.24.34.excalidraw.md)%%

# Fichamento — APS 2026.1 — Aula de 08/06/2026

# 1. Orientações específicas do projeto: requisitos, prazos e pesos

## 1.1. Tecnologias obrigatórias

O projeto da disciplina deverá utilizar obrigatoriamente:

- **Docker**
- **Frontend:** Thymeleaf
- **Bootstrap**
- **Backend:** Javalin
- **Banco de dados:** PostgreSQL

A escolha dessas tecnologias tem o objetivo de manter uma base comum para todos os projetos da turma.

O foco da disciplina não é a escolha livre de tecnologias, mas o estudo de conceitos de projeto de software, como:

- modularidade;
- reuso;
- padrões de projeto;
- baixo acoplamento;
- alta coesão;
- organização arquitetural;
- testes;
- logs;
- deploy;
- autenticação;
- autorização.

## 1.2. Estrutura esperada do projeto

O projeto deverá ser desenvolvido como uma aplicação web com:

- interface usando Thymeleaf e Bootstrap;
- backend em Java com Javalin;
- persistência em PostgreSQL;
- execução com Docker;
- publicação em servidor de produção;
- uso de logs;
- testes automatizados;
- autenticação;
- autorização;
- organização modular do código.

## 1.3. Uso obrigatório de GitHub, issues, branches e pull requests

As equipes deverão organizar o desenvolvimento usando GitHub.

Orientações principais:

- criar issues para as funcionalidades a serem implementadas;
- criar uma branch para cada funcionalidade;
- evitar programar diretamente na branch `main`;
- fazer commits e pushs frequentes;
- abrir pull requests para integrar código;
- revisar o código de outra pessoa da equipe antes do merge;
- usar a branch `main` como branch que dispara o deploy no fluxo simplificado da disciplina.

No contexto da disciplina, a branch `main` será tratada como a branch que dispara o deploy para produção.

Em projetos reais, é comum haver branches intermediárias, como:

- `dev`;
- `test`;
- `homolog`;
- `staging`.

Essas branches podem ser usadas antes de o código chegar à `main`.

Na disciplina, o fluxo será simplificado para que as equipes também tenham contato com problemas reais de produção.

## 1.4. Projeto no ar

Até **22 de junho de 2026**, todos os projetos deverão estar publicados no servidor.

Essa entrega funciona como pré-requisito para a continuidade do projeto na disciplina.

A aplicação pode ser simples nesse primeiro momento, por exemplo:

- uma página inicial;
- um “Olá, mundo”;
- um cadastro simples.

O ponto principal é que o projeto esteja funcionando em produção.

## 1.5. Aula prática de deploy

Foi combinada uma aula prática online para demonstrar o processo de colocar o sistema no ar.

- **Data:** 11 de junho de 2026
- **Horário:** 19h
- **Formato:** online, com gravação

O objetivo da aula prática será demonstrar o uso do ambiente, do pipeline e do deploy da aplicação.

## 1.6. Entrega de 06 de julho de 2026

A entrega de **06 de julho de 2026** terá **peso 1**.

Itens esperados:

- CRUDs;
- autenticação;
- autorização;
- uso de banco de dados;
- logs;
- testes automatizados;
- validações rigorosas de formulário;
- pelo menos uma aplicação do padrão Strategy;
- estratégias de quebra de acoplamento;
- organização do código em componentes, módulos ou estruturas semelhantes.

Os CRUDs devem incluir as operações de:

- cadastrar;
- listar;
- editar;
- remover.

As validações devem considerar, por exemplo:

- campos obrigatórios;
- tamanho mínimo e máximo de campos;
- CPF válido, quando aplicável;
- datas válidas;
- endereço, quando aplicável;
- limites de valores;
- dados inconsistentes;
- mensagens de erro adequadas.

Os testes automatizados devem contemplar:

- casos felizes;
- casos de exceção;
- entradas inválidas;
- operações não autorizadas;
- situações de erro relevantes.

## 1.7. Entrega de 20 de julho de 2026

A entrega de **20 de julho de 2026** terá **peso 3**.

Itens previstos:

- evolução das funcionalidades do projeto;
- implementação do padrão Observer;
- aprofundamento das estratégias de modularidade;
- melhoria das estratégias de quebra de acoplamento;
- continuidade da organização em componentes e módulos;
- manutenção dos testes, logs, autenticação e autorização.

## 1.8. Entrega final

A entrega final terá **peso 6**.

Ela deverá consolidar o projeto desenvolvido ao longo da disciplina, considerando:

- funcionalidades implementadas;
- qualidade do código;
- modularidade;
- baixo acoplamento;
- alta coesão;
- uso adequado de padrões de projeto;
- testes;
- logs;
- autenticação;
- autorização;
- funcionamento em produção.

## 1.9. Pipeline de qualidade, segurança, build e deploy

O projeto deverá usar um pipeline automatizado com GitHub Actions.

O pipeline deverá executar etapas como:

1. verificação de qualidade;
2. execução dos testes;
3. verificação de cobertura de testes;
4. análise de segurança;
5. build da aplicação;
6. geração da imagem Docker;
7. deploy no servidor.

Foi indicado que a cobertura mínima de testes deverá ficar em torno de 80%.

A cobertura de testes é importante, mas não garante sozinha a qualidade dos testes.

É possível ter alta cobertura com testes fracos. Por isso, além da cobertura, é necessário criar bons casos de teste, incluindo:

- casos felizes;
- casos de exceção;
- entradas inválidas;
- operações não autorizadas;
- situações de erro relevantes.

As ferramentas automatizadas de segurança ajudam a identificar vulnerabilidades conhecidas ou problemas comuns, mas não garantem que o sistema esteja totalmente seguro. Elas são uma camada de apoio dentro do processo de qualidade.

## 1.10. Uso de IA no desenvolvimento

O uso de IA é permitido e esperado, mas deve ser feito de forma guiada.

A equipe deve evitar pedir que a IA implemente uma funcionalidade inteira sem controle.

Forma inadequada:

```text
Implemente todo o CRUD de produto.
```

Forma mais adequada:

```text
Implemente o controller de produto seguindo a estrutura atual do projeto.
```

```text
Implemente o service de produto com as regras de validação.
```

```text
Implemente testes para os casos felizes e casos de exceção do cadastro de produto.
```

A responsabilidade pelo código é da equipe, mesmo quando o código for gerado com apoio de IA.

A equipe deve:

- revisar o código;
- entender o que foi gerado;
- testar;
- refatorar;
- corrigir;
- garantir que o projeto atende aos requisitos.

## 1.11. Avaliação com apoio de IA

A correção dos projetos poderá contar com apoio de IA, conduzida pelo professor.

A IA poderá ajudar a verificar aspectos como:

- existência de padrões de projeto;
- modularidade;
- acoplamento;
- coesão;
- testes;
- autenticação;
- autorização;
- logs;
- organização geral do código.

Os alunos também podem usar IA para revisar seus próprios projetos antes da entrega.

---

# 2. Tema geral da aula

A aula apresentou a organização técnica e processual do projeto da disciplina, incluindo:

- uso de Git, branches, issues e pull requests;
- conflitos de merge;
- fluxo de deploy automatizado com GitHub Actions;
- uso de Docker e servidor de produção;
- logs em produção;
- autenticação e autorização;
- modularidade, coesão e acoplamento;
- uso de interfaces para quebra de acoplamento;
- uso do padrão DAO para persistência;
- uso de IA no desenvolvimento de software;
- importância de componentes reutilizáveis e memória de projeto para agentes de IA;
- checagens automatizadas de qualidade, testes e segurança.

---

# 3. Tecnologias obrigatórias do projeto

## 3.1. Stack definida para a disciplina

Os projetos da disciplina deverão utilizar:

- Docker;
- Thymeleaf;
- Bootstrap;
- Javalin;
- PostgreSQL.

A estrutura geral será:

- frontend com Thymeleaf e Bootstrap;
- backend com Javalin;
- banco de dados PostgreSQL;
- aplicação empacotada e executada com Docker.

## 3.2. Bootstrap

Bootstrap foi apresentado como uma biblioteca de componentes HTML e CSS.

Ele ajuda a definir um padrão visual para a interface, oferecendo componentes prontos e estilos reutilizáveis.

Exemplos de uso do Bootstrap:

- botões;
- formulários;
- tabelas;
- menus;
- cards;
- grid de layout;
- mensagens de alerta.

## 3.3. Por que não usar outras tecnologias?

Foi reforçado que o objetivo da disciplina não é a escolha da tecnologia em si.

A tecnologia será usada como base comum para estudar conceitos como:

- modularidade;
- reuso;
- padrões de projeto;
- organização arquitetural;
- baixo acoplamento;
- alta coesão;
- deploy;
- testes;
- logs;
- autenticação;
- autorização.

---

# 4. Trabalho em equipe com Git

## 4.1. Conflitos de merge

Um dos problemas comuns em projetos em equipe é o conflito de merge.

Um conflito de merge ocorre quando duas ou mais pessoas alteram os mesmos arquivos ou os mesmos trechos de código.

Exemplo:

1. Uma pessoa altera um arquivo.
2. Essa pessoa faz commit e push.
3. Outra pessoa, que estava com uma versão anterior do projeto, também altera o mesmo arquivo.
4. Ao tentar enviar ou integrar suas mudanças, o Git detecta que já existe uma versão mais nova no servidor.
5. Quando a pessoa atualiza seu projeto local, as alterações entram em conflito.

O conflito precisa ser resolvido manualmente, analisando:

- o que uma pessoa alterou;
- o que a outra pessoa alterou;
- qual versão deve ser mantida;
- se as duas alterações precisam ser combinadas;
- se o código continua funcionando depois da resolução.

## 4.2. Como reduzir conflitos

A principal recomendação foi a comunicação entre os membros da equipe.

Exemplos de acordos importantes:

- avisar quais arquivos serão alterados;
- avisar qual módulo está sendo desenvolvido;
- evitar que duas pessoas trabalhem simultaneamente na mesma funcionalidade;
- dividir tarefas por módulos;
- combinar previamente quem mexe em cada parte do sistema.

Exemplo de comunicação interna:

```text
Estou mexendo nos arquivos A, B e C.
```

Ou:

```text
Estou implementando o módulo X. Não mexam nesse módulo agora; trabalhem no módulo Y.
```

## 4.3. Arquivos naturalmente compartilhados

Alguns arquivos são naturalmente comuns e podem gerar conflitos com mais frequência.

Um exemplo citado foi a classe ou arquivo responsável pelas rotas da aplicação.

Como várias funcionalidades precisam registrar rotas ou endpoints, é comum que diferentes pessoas alterem esse mesmo arquivo.

Conflitos em arquivos de rotas costumam ser simples, mas ainda assim precisam ser revisados com atenção para garantir que nenhuma rota foi:

- removida indevidamente;
- duplicada;
- quebrada;
- associada ao controller errado;
- deixada sem proteção de autenticação ou autorização quando necessário.

---

# 5. Branches por funcionalidade

## 5.1. Branch principal

No GitHub, a branch principal geralmente é chamada de `main`.

Na disciplina, a branch `main` será associada ao código que dispara o deploy para produção.

Isso significa que, quando o código for integrado à `main`, o pipeline poderá publicar a aplicação no servidor.

## 5.2. O que significa ir para produção?

Ir para produção significa publicar o sistema em um servidor, de modo que ele fique disponível para uso.

No contexto da disciplina:

- o código será enviado para o GitHub;
- o GitHub Actions executará o pipeline;
- a imagem Docker será gerada;
- o sistema será publicado no servidor da disciplina;
- cada equipe terá um endereço próprio.

## 5.3. Fluxo simplificado da disciplina e fluxo real

Na disciplina, a branch `main` será tratada como branch de produção.

Essa é uma simplificação didática.

Em projetos reais, é comum que o código passe por branches intermediárias antes da produção.

Exemplo de fluxo mais comum em empresas:

1. Criar branch de funcionalidade.
2. Integrar na branch `dev`.
3. Testar.
4. Integrar em `staging` ou homologação.
5. Validar.
6. Integrar na `main`.
7. Publicar em produção.

Na disciplina, o fluxo será mais direto para permitir que as equipes vivenciem também problemas reais de integração e produção.

## 5.4. Não programar diretamente na branch `main`

Foi orientado que os alunos não devem programar diretamente na branch `main`.

Motivos:

- commits incompletos poderiam ir para produção;
- funcionalidades inacabadas poderiam quebrar o sistema;
- o código principal ficaria instável;
- seria mais difícil revisar alterações;
- aumentaria o risco de conflitos.

## 5.5. Commits frequentes

Foi destacado que não se deve fazer commit e push apenas quando a funcionalidade estiver totalmente pronta.

Commits frequentes são importantes porque:

- registram a evolução do trabalho;
- facilitam colaboração;
- reduzem perda de código;
- permitem compartilhar o andamento com a equipe;
- facilitam a recuperação de versões anteriores.

O push para o GitHub também ajuda a preservar o trabalho remotamente, mas o objetivo principal do Git é controle de versão e colaboração, não apenas backup.

---

# 6. Issues no GitHub

## 6.1. O que são issues?

Issues são tarefas, demandas ou funcionalidades a serem implementadas no projeto.

Elas podem representar, por exemplo:

- implementar CRUD de produto;
- criar tela de login;
- validar CPF;
- implementar autorização;
- configurar banco de dados;
- criar testes automatizados;
- implementar padrão Strategy.

## 6.2. Uso obrigatório de issues na disciplina

Não será exigido um planejamento completo de todas as atividades do projeto.

Entretanto, será exigido que, antes de programar uma funcionalidade, a equipe crie uma issue correspondente.

Exemplo:

- Issue: `CRUD de produto`
- Responsável: pessoa que vai implementar essa funcionalidade

O objetivo é permitir acompanhar quais funcionalidades estão sendo implementadas em cada projeto.

## 6.3. Atribuição de responsáveis

Ao criar uma issue, a tarefa pode ser atribuída a uma pessoa da equipe.

Isso ajuda a organizar:

- quem está responsável por cada funcionalidade;
- quais tarefas estão em andamento;
- quais tarefas foram concluídas;
- quais partes do sistema ainda precisam ser feitas.

---

# 7. Tutorial: criando branch, pull request e merge na main

Durante a aula, foi solicitado que a anotação incluísse um tutorial sobre como criar uma branch, fazer pull request e fazer merge na `main`.

## 7.1. Fluxo geral

O fluxo recomendado é:

1. Criar uma issue para a tarefa.
2. Criar uma branch a partir da issue.
3. Fazer checkout da branch.
4. Implementar a funcionalidade.
5. Fazer commits e push da branch.
6. Abrir um pull request.
7. Pedir revisão de outra pessoa da equipe.
8. Fazer o merge na branch `main` quando estiver tudo correto.

## 7.2. Criando uma issue no GitHub

No repositório do projeto:

1. Acesse a aba **Issues**.
2. Clique em **New issue**.
3. Dê um título para a tarefa.

Exemplo:

```text
CRUD de produto
```

4. Descreva o que precisa ser feito.

Exemplo:

```text
Implementar cadastro, listagem, edição e remoção de produtos.
Adicionar validações de campos obrigatórios, tamanho dos campos e preço.
Criar testes automatizados para casos válidos e inválidos.
```

5. Atribua a issue a uma pessoa da equipe.
6. Crie a issue.

## 7.3. Criando uma branch a partir da issue

Dentro da própria issue, o GitHub pode oferecer a opção:

```text
Create a branch for this issue
```

Ao clicar nessa opção, o GitHub sugere um nome de branch.

Exemplo:

```text
1-crud-de-produto
```

Pode-se manter o nome sugerido pelo GitHub.

## 7.4. Fazendo checkout da branch localmente

Depois de criar a branch no GitHub, é necessário trazê-la para o computador.

Exemplo de comandos:

```bash
git fetch origin
git checkout 1-crud-de-produto
```

Também é possível criar a branch localmente:

```bash
git checkout -b 1-crud-de-produto
```

E depois enviá-la para o GitHub:

```bash
git push -u origin 1-crud-de-produto
```

## 7.5. Trabalhando na branch

Depois de entrar na branch, implemente a funcionalidade.

Durante o desenvolvimento, faça commits frequentes.

Exemplo:

```bash
git status
git add .
git commit -m "Implementa cadastro de produto"
git push
```

Depois de novas alterações:

```bash
git add .
git commit -m "Adiciona validações no formulário de produto"
git push
```

## 7.6. Abrindo um pull request

Quando a funcionalidade estiver pronta:

1. Acesse o repositório no GitHub.
2. Vá até a aba **Pull requests**.
3. Clique em **New pull request**.
4. Escolha a branch da funcionalidade.
5. Compare com a branch `main`.
6. Escreva um título e uma descrição.
7. Crie o pull request.

Exemplo de título:

```text
Implementa CRUD de produto
```

Exemplo de descrição:

```text
Este pull request implementa o CRUD de produto, incluindo cadastro, listagem, edição, remoção, validações de formulário e testes automatizados.
```

## 7.7. Revisando o pull request

A recomendação é que uma pessoa da equipe revise o código da outra.

Durante a revisão, observar:

- se o código funciona;
- se os testes passam;
- se há duplicação de código;
- se a funcionalidade está bem modularizada;
- se há baixo acoplamento;
- se há alta coesão;
- se as validações foram implementadas;
- se o código segue o padrão do projeto;
- se não há dados sensíveis expostos;
- se o código não quebra funcionalidades existentes.

## 7.8. Fazendo merge na `main`

Se o pull request estiver correto, ele pode ser integrado à branch `main`.

Esse processo é o merge.

No GitHub:

1. Abra o pull request.
2. Verifique se não há conflitos.
3. Verifique se as checagens passaram.
4. Clique em **Merge pull request**.
5. Confirme o merge.

Depois disso, a branch `main` receberá o código da funcionalidade.

Na disciplina, quando houver push ou merge na `main`, o pipeline poderá publicar a aplicação em produção.

## 7.9. Atualizando o projeto local depois do merge

Depois que o merge for feito, todos da equipe devem atualizar suas cópias locais.

Exemplo:

```bash
git checkout main
git pull origin main
```

Depois disso, uma nova branch pode ser criada para outra funcionalidade.

---

# 8. Pull request

## 8.1. O que é um pull request?

Pull request é uma solicitação para integrar o código de uma branch em outra.

No contexto da aula, normalmente será uma solicitação para integrar uma branch de funcionalidade na branch `main`.

Exemplo:

- branch de origem: `1-crud-de-produto`;
- branch de destino: `main`.

## 8.2. Finalidade do pull request

O pull request permite:

- revisar código antes da integração;
- executar checagens automáticas;
- discutir alterações;
- detectar erros antes de ir para produção;
- evitar que código instável entre na branch principal.

## 8.3. Revisão de código

Em projetos reais, é comum que outra pessoa revise o código antes do merge.

Também é comum que o repositório tenha regras que impeçam o merge sem aprovação.

Exemplo:

- exigir uma revisão aprovada;
- exigir duas revisões aprovadas;
- exigir que todos os testes passem;
- exigir que a cobertura mínima de testes seja atingida;
- exigir que a análise de segurança não encontre problemas graves.

---

# 9. Compartilhamento de código com branches

Quando uma pessoa está com problema em sua branch, ela pode fazer push dessa branch para o GitHub.

Outra pessoa da equipe pode baixar a branch e ajudar a investigar.

Exemplo:

```bash
git fetch origin
git checkout nome-da-branch
```

Isso evita práticas inadequadas, como enviar código por arquivo `.zip`.

Vantagens:

- mantém o histórico de alterações;
- permite colaboração;
- facilita revisão;
- evita perda de código;
- mantém o projeto organizado.

---

# 10. GitHub Actions e deploy automatizado

## 10.1. O que é GitHub Actions?

GitHub Actions é um recurso do GitHub que permite executar scripts automaticamente.

Na disciplina, ele será usado para automatizar o fluxo de publicação da aplicação.

## 10.2. Quando o pipeline será executado?

O pipeline será executado quando houver push ou merge na branch `main`.

## 10.3. O que o pipeline fará?

O pipeline deverá:

1. Executar checagens de qualidade.
2. Executar testes.
3. Verificar cobertura de testes.
4. Executar verificações de segurança.
5. Fazer o build da aplicação.
6. Gerar uma imagem Docker.
7. Acessar o servidor via SSH.
8. Enviar ou atualizar a imagem Docker.
9. Subir o container no servidor.
10. Publicar a aplicação no endereço da equipe.

## 10.4. Exemplo conceitual do fluxo

```text
Código da equipe
      |
      v
Commit e push
      |
      v
Pull request
      |
      v
Merge na main
      |
      v
GitHub Actions
      |
      v
Build da aplicação
      |
      v
Imagem Docker
      |
      v
Acesso SSH ao servidor
      |
      v
Deploy do container
      |
      v
Aplicação em produção
```

---

# 11. Docker

## 11.1. Uso do Docker na disciplina

Todos os projetos precisarão usar Docker.

O Docker será usado para empacotar a aplicação em uma imagem e executar essa imagem como container no servidor.

## 11.2. Imagem Docker

Uma imagem Docker é como um pacote contendo:

- aplicação;
- dependências;
- configurações necessárias;
- instruções de execução.

## 11.3. Container Docker

Um container é uma instância em execução de uma imagem Docker.

No contexto da disciplina, cada equipe terá sua aplicação executando como container no servidor.

---

# 12. SSH e secrets

## 12.1. O que é SSH?

SSH é uma conexão segura que permite acessar um computador remotamente por meio de um terminal.

Na disciplina, o GitHub Actions usará SSH para acessar o servidor e executar comandos de deploy.

## 12.2. Chave SSH

Para acessar o servidor, será necessário usar uma chave.

Essa chave não deve ser colocada diretamente no código.

Ela deverá ser configurada como um secret no GitHub.

## 12.3. Secrets no GitHub

Secrets são variáveis sensíveis armazenadas de forma protegida no GitHub.

Exemplos de secrets citados ou relacionados ao processo:

- chave de deploy SSH;
- host SSH;
- usuário SSH;
- outras informações de acesso necessárias ao pipeline.

Exemplo conceitual:

```text
SSH_HOST=servidor-da-disciplina
SSH_USERNAME=nome-da-equipe
SSH_DEPLOY_KEY=chave-privada-de-deploy
```

Esses valores não devem ser expostos no repositório.

---

# 13. Servidor e endereço dos projetos

Cada equipe terá um endereço próprio para acessar o sistema publicado.

A estrutura apresentada na aula foi a de cada equipe ter sua aplicação publicada em um subdomínio próprio do servidor da disciplina.

Exemplo genérico:

```text
equipe01.servidor-da-disciplina
equipe02.servidor-da-disciplina
equipe03.servidor-da-disciplina
```

O endereço real será informado pela disciplina.

---

# 14. Logs em produção

## 14.1. O que são logs?

Logs são registros gerados pelo sistema durante sua execução.

Eles ajudam a entender o que aconteceu em determinado momento.

Um log pode registrar, por exemplo:

- início da aplicação;
- erro ao conectar ao banco;
- exceção lançada;
- tentativa de login;
- falha de autorização;
- requisição recebida;
- operação realizada;
- falha no deploy.

## 14.2. Por que logs são importantes?

Logs são essenciais para depurar problemas em produção.

Quando a aplicação não funciona no servidor, os logs ajudam a responder perguntas como:

- a aplicação subiu corretamente?
- houve erro de configuração?
- o banco conectou?
- alguma exceção foi lançada?
- qual rota gerou erro?
- qual operação falhou?
- o erro ocorreu no backend?
- o erro ocorreu no banco?
- o erro ocorreu no deploy?

## 14.3. Acesso aos logs

Foi informado que os alunos terão acesso aos logs dos projetos em produção.

Isso permitirá acompanhar o comportamento da aplicação no servidor.

## 14.4. Logs como parte da experiência de aprendizagem

A aula destacou que lidar com erros em produção é uma experiência importante.

Problemas esperados:

- aplicação não subir;
- erro de configuração;
- falha de conexão;
- erro de banco;
- exceção em tempo de execução;
- falha no pipeline;
- problema de integração entre códigos de diferentes pessoas.

Esses problemas fazem parte do processo de aprendizagem.

---

# 15. CRUDs

## 15.1. O que é CRUD?

CRUD é o conjunto básico de operações de manipulação de dados.

A sigla representa:

- **Create:** cadastrar;
- **Read:** listar ou consultar;
- **Update:** editar;
- **Delete:** remover.

Exemplo:

Em um CRUD de produto, o sistema deve permitir:

- cadastrar produto;
- listar produtos;
- editar produto;
- remover produto.

## 15.2. CRUD com validações

Os CRUDs devem ter validações rigorosas.

Exemplos de validações esperadas:

- campos obrigatórios;
- tamanho mínimo de campo;
- tamanho máximo de campo;
- formato de CPF;
- formato de datas;
- endereço;
- limites de valores;
- consistência entre campos;
- mensagens de erro adequadas.

## 15.3. Testes para CRUDs

Os CRUDs devem ter testes automatizados.

Os testes devem cobrir:

- casos felizes;
- casos de erro;
- campos inválidos;
- campos ausentes;
- valores fora do limite;
- tentativas de operação sem autorização;
- dados inconsistentes.

---

# 16. Validações de formulário

## 16.1. Rigor nas validações

Foi reforçado que os formulários devem ser tratados com rigor.

O sistema não deve assumir que o usuário preencherá tudo corretamente.

Possíveis problemas:

- campo obrigatório vazio;
- CPF inválido;
- data inválida;
- texto maior que o limite permitido;
- número negativo em campo que não permite valor negativo;
- e-mail em formato inválido;
- endereço incompleto;
- preço inválido;
- tentativa de cadastrar dados duplicados.

## 16.2. Exemplos de validações

Exemplo de regras de validação para produto:

```text
Nome:
- obrigatório
- mínimo de 3 caracteres
- máximo de 100 caracteres

Descrição:
- opcional
- máximo de 500 caracteres

Preço:
- obrigatório
- maior que zero

Data de cadastro:
- obrigatória
- deve ser uma data válida
```

Exemplo de regras para pessoa:

```text
Nome:
- obrigatório
- mínimo de 3 caracteres

CPF:
- obrigatório
- deve ter formato válido
- deve passar na validação dos dígitos verificadores

Data de nascimento:
- obrigatória
- deve ser uma data válida

Endereço:
- obrigatório
- deve conter informações mínimas necessárias
```

---

# 17. Testes automatizados

## 17.1. Importância dos testes

Os testes automatizados são obrigatórios no projeto.

Eles servem para verificar se o sistema continua funcionando corretamente após alterações.

## 17.2. Casos felizes

Casos felizes são cenários em que tudo ocorre como esperado.

Exemplo:

- cadastrar produto com dados válidos;
- fazer login com usuário e senha corretos;
- editar um registro existente;
- remover um item permitido;
- listar registros cadastrados.

## 17.3. Casos de exceção

Casos de exceção são cenários em que algo dá errado ou em que o sistema precisa rejeitar uma operação.

Exemplo:

- cadastrar produto sem nome;
- cadastrar CPF inválido;
- tentar editar item inexistente;
- tentar remover item sem permissão;
- fazer login com senha incorreta;
- acessar uma página sem estar autenticado;
- executar ação sem autorização.

## 17.4. Uso da IA para sugerir testes

Foi recomendado usar IA para ajudar a identificar casos de teste.

Exemplo de solicitação para IA:

```text
Para esta funcionalidade de cadastro de produto, quais são os casos felizes e os casos de exceção que eu deveria testar?
```

A IA pode sugerir casos, mas a equipe deve revisar e complementar.

A responsabilidade pelo código continua sendo da equipe.

---

# 18. Autenticação

## 18.1. O que é autenticação?

Autenticação é o processo de verificar se a pessoa é quem afirma ser.

Exemplos de autenticação:

- login e senha;
- link de acesso;
- código enviado por e-mail;
- autenticação por provedor externo;
- autenticação por token.

## 18.2. Exigência da disciplina

Todos os projetos precisam ter alguma forma de autenticação.

O sistema deve conseguir identificar o usuário logado.

## 18.3. Exemplos de autenticação

Exemplo com login e senha:

1. Usuário informa e-mail e senha.
2. Sistema verifica se os dados estão corretos.
3. Se estiverem corretos, cria uma sessão ou token.
4. Usuário passa a ser reconhecido como autenticado.

Exemplo com link ou código:

1. Usuário informa e-mail.
2. Sistema envia um código ou link.
3. Usuário confirma o código.
4. Sistema reconhece o usuário como autenticado.

---

# 19. Autorização

## 19.1. O que é autorização?

Autorização é o processo de verificar se um usuário autenticado tem permissão para executar determinada ação.

Exemplo:

- um administrador pode cadastrar usuários;
- um professor pode lançar notas;
- um aluno pode consultar suas próprias informações;
- um comprador pode aprovar uma compra;
- um usuário comum não pode acessar área administrativa.

## 19.2. Diferença entre autenticação e autorização

Autenticação responde:

> Quem é você?

Autorização responde:

> Você pode fazer isso?

Um usuário pode estar autenticado e, ainda assim, não ter autorização para executar determinada ação.

## 19.3. Exigência da disciplina

Todos os projetos precisam ter alguma forma de autorização.

Não pode ser um sistema em que o usuário faz login e pode acessar tudo.

Deve existir alguma segmentação de funcionalidades por:

- papel;
- perfil;
- permissão;
- tipo de usuário;
- regra de negócio.

## 19.4. Problema de espalhar autorização pelo sistema

Uma má solução seria espalhar regras de autorização diretamente por várias partes do sistema.

Exemplo ruim:

```java
if (usuario.getPapel().equals("ADMIN")) {
    // faz alguma coisa
}
```

Se essa lógica for repetida em muitos lugares, qualquer mudança de regra exigirá alteração em várias partes do sistema.

Isso gera:

- duplicação de código;
- alto acoplamento;
- dificuldade de manutenção;
- maior risco de erro;
- regras inconsistentes.

## 19.5. Solução recomendada

A lógica de autorização deve ficar concentrada em um módulo, serviço, classe ou componente específico.

Exemplo conceitual:

```java
if (autorizador.podeCadastrarProduto(usuario)) {
    produtoService.cadastrar(produto);
}
```

Assim, a regra fica centralizada.

Se a regra mudar, a alteração acontece em um lugar mais controlado.

---

# 20. Modularidade, coesão e acoplamento

## 20.1. Conceito central

Um conceito fundamental da aula foi:

> Juntar coisas que têm alta coesão e separar coisas que têm baixa coesão.

Esse princípio é importante independentemente da linguagem de programação usada.

## 20.2. Acoplamento

Acoplamento é o grau de dependência entre partes do sistema.

Quando uma classe depende diretamente de outra, existe acoplamento.

Exemplo:

- `Disciplina` relacionada a `Professor`;
- `Turma` relacionada a `Aluno`;
- `Aluno` relacionado a `Empréstimo` em um módulo de biblioteca.

O acoplamento nem sempre é ruim.

Existe acoplamento necessário quando os conceitos realmente fazem sentido juntos no domínio do problema.

## 20.3. Baixo acoplamento

Baixo acoplamento significa reduzir dependências desnecessárias entre partes do sistema.

Benefícios:

- facilita manutenção;
- facilita testes;
- facilita reuso;
- reduz efeitos colaterais;
- permite trocar implementações;
- melhora a organização do código;
- ajuda no desenvolvimento com IA.

## 20.4. Coesão

Coesão é o grau de relação conceitual entre os elementos de uma mesma classe, módulo ou componente.

Uma classe tem alta coesão quando seus métodos e atributos pertencem ao mesmo conceito ou responsabilidade.

## 20.5. Alta coesão

Alta coesão significa agrupar no mesmo lugar coisas que pertencem ao mesmo conceito ou à mesma responsabilidade.

Exemplo:

Em um sistema acadêmico, os seguintes conceitos pertencem ao mesmo domínio:

- aluno;
- turma;
- disciplina;
- professor.

Esses conceitos podem estar relacionados dentro do domínio acadêmico.

Em um sistema de biblioteca, também pode existir uma relação coesa entre:

- aluno;
- livro;
- empréstimo.

Nesse caso, aluno também aparece no domínio de biblioteca, pois pode estar relacionado ao empréstimo de livros.

## 20.6. Baixa coesão

Baixa coesão ocorre quando conceitos sem relação são misturados.

Exemplo:

- relacionar diretamente uma disciplina acadêmica com uma entidade de domínio bancário.

Esse tipo de mistura gera confusão conceitual e prejudica a manutenção.

## 20.7. Relações conceituais e dependências no código

Mesmo quando dois conceitos se relacionam no domínio, isso não significa que toda relação precise virar uma dependência direta forte no código.

Por exemplo, o relacionamento entre `Disciplina` e `Professor` pode fazer sentido em um sistema acadêmico.

Ainda assim, a implementação deve ser feita com critério.

Em alguns casos, pode ser adequado usar:

- referência direta;
- identificadores;
- serviços;
- repositórios;
- interfaces;
- objetos intermediários.

A decisão depende do desenho do sistema e do nível de acoplamento desejado.

---

# 21. Separação por camadas

## 21.1. Controller, service, repository, model e DAO

A aula citou a separação da arquitetura em partes como:

- controller;
- service;
- repository;
- model.

Além disso, foi incorporado o conceito de **DAO — Data Access Object**, corrigindo a referência feita em aula a “JDO”.

No contexto discutido, o padrão adequado é DAO.

## 21.2. Controller

O controller lida com a entrada da requisição.

Responsabilidades comuns:

- receber dados da requisição;
- chamar serviços;
- escolher resposta;
- redirecionar usuário;
- renderizar tela.

## 21.3. Service

O service concentra regras de negócio.

Responsabilidades comuns:

- validar regras;
- coordenar operações;
- chamar objetos de acesso a dados;
- aplicar lógica do domínio;
- organizar operações da aplicação.

## 21.4. Repository

O repository é uma abstração usada para lidar com persistência e recuperação de objetos ou agregados do domínio.

Responsabilidades comuns:

- salvar entidades;
- buscar entidades;
- atualizar registros;
- remover registros;
- esconder detalhes de persistência do restante da aplicação.

## 21.5. DAO — Data Access Object

DAO significa **Data Access Object**.

É um padrão usado para isolar o acesso ao banco de dados.

A ideia do DAO é criar uma classe específica para realizar operações de persistência, evitando que controllers ou services manipulem SQL diretamente.

Exemplo conceitual:

```java
public class ProdutoDAO {
    public void salvar(Produto produto) {
        // código SQL para inserir produto no banco
    }

    public Produto buscarPorId(int id) {
        // código SQL para buscar produto no banco
    }

    public List<Produto> listarTodos() {
        // código SQL para listar produtos
    }

    public void atualizar(Produto produto) {
        // código SQL para atualizar produto
    }

    public void remover(int id) {
        // código SQL para remover produto
    }
}
```

Com DAO, o controller não precisa conhecer SQL.

O service também pode se concentrar melhor nas regras de negócio.

Exemplo de uso:

```java
public class ProdutoService {
    private ProdutoDAO produtoDAO;

    public ProdutoService(ProdutoDAO produtoDAO) {
        this.produtoDAO = produtoDAO;
    }

    public void cadastrar(Produto produto) {
        // valida regras de negócio
        produtoDAO.salvar(produto);
    }
}
```

## 21.6. Model

O model representa entidades ou conceitos do domínio.

Exemplos:

- Produto;
- Usuário;
- Pedido;
- Aluno;
- Turma;
- Disciplina.

## 21.7. Por que separar?

Separar essas partes evita código macarrônico.

Também facilita:

- testes;
- manutenção;
- reuso;
- leitura;
- evolução;
- localização de erros.

---

# 22. Persistência com DAO

## 22.1. O problema da persistência

Persistência é o processo de guardar objetos em algum meio durável, como um banco de dados.

No projeto, será necessário:

- pegar um objeto em memória;
- salvar no banco;
- buscar dados no banco;
- reconstruir objetos a partir dos dados;
- atualizar dados;
- remover dados.

## 22.2. Frameworks de persistência

Em projetos com Spring Boot, é comum usar Spring Data JPA.

JPA é uma especificação para persistência objeto-relacional.

Hibernate é uma implementação bastante usada dessa especificação.

Essas ferramentas fazem o mapeamento entre objetos e tabelas do banco.

## 22.3. O objetivo na disciplina

Na disciplina, a proposta não é usar uma solução pronta como Spring Security ou um framework completo de persistência.

O objetivo é entender e implementar os módulos necessários.

Assim, os alunos precisarão pensar em como organizar a persistência.

## 22.4. DAO como padrão para acesso a dados

O DAO será útil para separar o acesso ao banco de dados do restante da aplicação.

Sem DAO, é comum que o SQL fique espalhado em controllers ou services.

Isso gera problemas como:

- duplicação de código SQL;
- dificuldade de manutenção;
- alto acoplamento com o banco;
- dificuldade para testar regras de negócio;
- mistura de responsabilidades.

Com DAO, a aplicação fica mais organizada.

Exemplo de separação:

```text
Controller
   |
   v
Service
   |
   v
DAO
   |
   v
Banco de dados
```

## 22.5. Exemplo de responsabilidades

O controller deve lidar com a requisição.

O service deve lidar com a regra de negócio.

O DAO deve lidar com o banco de dados.

Exemplo conceitual:

```java
public class ProdutoController {
    private ProdutoService produtoService;

    public void cadastrar(Context ctx) {
        Produto produto = // obter dados do formulário
        produtoService.cadastrar(produto);
        ctx.redirect("/produtos");
    }
}
```

```java
public class ProdutoService {
    private ProdutoDAO produtoDAO;

    public void cadastrar(Produto produto) {
        // validar dados
        // aplicar regras de negócio
        produtoDAO.salvar(produto);
    }
}
```

```java
public class ProdutoDAO {
    public void salvar(Produto produto) {
        // executar INSERT no banco
    }
}
```

---

# 23. Exemplo de quebra de acoplamento com restaurante

## 23.1. Cenário

A aula apresentou um exemplo com dois tipos de negócio:

- pizzaria;
- hamburgueria.

Um cliente quer se alimentar, mas não deveria ficar fortemente acoplado a uma implementação específica.

Se o cliente depender diretamente de `Pizzaria` e `Hamburgueria`, ele fica acoplado a essas classes concretas.

## 23.2. Problema

Sem abstração, o cliente precisaria conhecer métodos específicos de cada classe.

Exemplo conceitual:

```java
pizzaria.listarPizzas();
pizzaria.pedirPizza(idPizza);

hamburgueria.listarHamburgueres();
hamburgueria.pedirHamburguer(idHamburguer);
```

O problema é que cada classe tem sua própria interface.

A pizzaria trabalha com pizza.

A hamburgueria trabalha com hambúrguer.

O cliente fica dependente das diferenças internas de cada tipo de estabelecimento.

## 23.3. Solução com abstração

Para reduzir o acoplamento, cria-se uma abstração comum.

Exemplo:

- `Restaurante`;
- `Produto`;
- `ItemDoMenu`.

A ideia é que o cliente interaja com a interface `Restaurante`, e não diretamente com `Pizzaria` ou `Hamburgueria`.

## 23.4. Interface como contrato

Uma interface define um contrato entre partes do sistema.

Ela especifica quais operações uma classe deve oferecer, permitindo que outras partes do sistema dependam da abstração, e não da implementação concreta.

Exemplo conceitual:

```java
public interface Restaurante {
    List<Produto> getMenu();
    Produto fazerPedido(int idProduto);
}
```

A interface não precisa saber como cada restaurante implementa esses métodos.

Ela apenas define o que deve existir.

## 23.5. Implementações concretas

A pizzaria pode implementar a interface `Restaurante`.

```java
public class Pizzaria implements Restaurante {
    @Override
    public List<Produto> getMenu() {
        // retorna produtos da pizzaria
    }

    @Override
    public Produto fazerPedido(int idProduto) {
        // faz pedido de pizza
    }
}
```

A hamburgueria também pode implementar a interface.

```java
public class Hamburgueria implements Restaurante {
    @Override
    public List<Produto> getMenu() {
        // retorna produtos da hamburgueria
    }

    @Override
    public Produto fazerPedido(int idProduto) {
        // faz pedido de hambúrguer
    }
}
```

## 23.6. Cliente usando a abstração

O cliente passa a depender da interface.

```java
public class Cliente {
    private Restaurante restaurante;

    public Cliente(Restaurante restaurante) {
        this.restaurante = restaurante;
    }

    public void comprar(int idProduto) {
        Produto produto = restaurante.fazerPedido(idProduto);
    }
}
```

Agora, o cliente não precisa saber se o restaurante é uma pizzaria ou uma hamburgueria.

Isso reduz o acoplamento.

## 23.7. Observação sobre adaptação

Quando uma classe concreta já possui métodos próprios incompatíveis com a interface esperada pelo cliente, pode ser necessário adaptar essa classe.

Por exemplo, se a pizzaria já possui:

```java
listarPizzas()
pedirPizza(idPizza)
```

E a interface comum exige:

```java
getMenu()
fazerPedido(idProduto)
```

Será necessário fazer uma tradução entre essas operações.

Essa adaptação pode ser feita:

- diretamente na própria classe, se ela puder ser modificada;
- por meio de uma classe intermediária, caso seja necessário adaptar uma interface já existente.

Esse tipo de situação prepara o terreno para discutir padrões que lidam com adaptação entre interfaces diferentes.

---

# 24. Interfaces e quebra de acoplamento

## 24.1. Interface não é a única forma de quebrar acoplamento

A aula destacou que interface é uma forma importante de quebrar acoplamento, mas não é a única.

Outras formas incluem:

- criar módulos;
- criar subsistemas;
- separar pacotes;
- evitar dependências diretas entre domínios diferentes;
- isolar responsabilidades;
- criar serviços específicos;
- criar componentes reutilizáveis;
- separar regras de negócio de detalhes de infraestrutura.

## 24.2. Pacotes e módulos

Ao criar pacotes e colocar classes relacionadas juntas, o projeto fica mais organizado.

Exemplo:

```text
br.edu.projeto.usuario
br.edu.projeto.produto
br.edu.projeto.autenticacao
br.edu.projeto.autorizacao
br.edu.projeto.pedido
br.edu.projeto.persistencia
```

Cada pacote deve reunir conceitos coesos.

## 24.3. Evitar dependências indevidas

Classes de um módulo não devem depender desnecessariamente de classes internas de outro módulo.

Quando a comunicação for necessária, deve-se preferir abstrações, serviços ou contratos bem definidos.

---

# 25. Exemplo: módulo de impressão de cupons

A aula apresentou a ideia de que funcionalidades específicas devem ficar em módulos próprios.

Exemplo:

Se o sistema precisa imprimir cupons, essa responsabilidade não deve ficar espalhada em controllers.

Em vez disso, deve existir um módulo específico para impressão de cupons.

Exemplo conceitual:

```java
cupomService.imprimirCupom(pedido);
```

Ou:

```java
impressoraDeCupom.imprimir(pedido);
```

Assim, se houver problema com impressão de cupom, a equipe sabe onde procurar.

Benefícios:

- organização;
- reuso;
- manutenção;
- testes mais focados;
- menor duplicação;
- menor acoplamento.

---

# 26. Strategy

## 26.1. Exigência da primeira entrega avaliativa

Até a entrega de 06 de julho de 2026, cada projeto deve ter pelo menos uma implementação do padrão Strategy.

## 26.2. Ideia geral do Strategy

Strategy é um padrão de projeto que permite variar um algoritmo ou comportamento sem espalhar condicionais pelo código.

A ideia é criar uma interface comum para diferentes estratégias.

Depois, o sistema escolhe qual estratégia usar.

## 26.3. Exemplo conceitual

Imagine um sistema que calcula desconto.

Há diferentes formas de desconto:

- desconto para cliente comum;
- desconto para cliente premium;
- desconto promocional;
- desconto por cupom.

Uma solução ruim seria espalhar vários `if` pelo sistema.

Exemplo ruim:

```java
if (tipoCliente.equals("PREMIUM")) {
    desconto = valor * 0.15;
} else if (tipoCliente.equals("COMUM")) {
    desconto = valor * 0.05;
} else {
    desconto = 0;
}
```

Uma solução com Strategy poderia criar uma interface:

```java
public interface EstrategiaDesconto {
    BigDecimal calcular(BigDecimal valor);
}
```

E várias implementações:

```java
public class DescontoClienteComum implements EstrategiaDesconto {
    public BigDecimal calcular(BigDecimal valor) {
        return valor.multiply(new BigDecimal("0.05"));
    }
}
```

```java
public class DescontoClientePremium implements EstrategiaDesconto {
    public BigDecimal calcular(BigDecimal valor) {
        return valor.multiply(new BigDecimal("0.15"));
    }
}
```

Assim, o comportamento fica modularizado e pode ser trocado sem alterar todo o sistema.

---

# 27. Observer

## 27.1. Entrega posterior

O padrão Observer foi citado como requisito para a entrega de 20 de julho de 2026.

## 27.2. Ideia geral do Observer

Observer é um padrão usado quando um objeto precisa notificar outros objetos sobre mudanças ou eventos.

Exemplo conceitual:

- quando um pedido é criado, notificar módulo de e-mail;
- quando um pagamento é confirmado, atualizar o status do pedido;
- quando um usuário é cadastrado, registrar log;
- quando um produto fica sem estoque, notificar o responsável.

A ideia é evitar que o objeto principal fique fortemente acoplado a todos os interessados no evento.

---

# 28. Uso de IA no desenvolvimento do projeto

## 28.1. IA como ferramenta de implementação guiada

Foi orientado que os alunos usem IA para implementar o projeto, mas de forma controlada.

A IA não deve ser usada simplesmente para implementar uma funcionalidade inteira de uma vez sem acompanhamento.

Exemplo de pedido amplo demais:

```text
Implemente cadastrar, listar, editar e remover produto.
Produto tem nome, descrição e preço.
```

O problema desse tipo de pedido é que a IA pode gerar muitas partes do sistema de uma vez.

Isso pode fazer a equipe perder controle sobre:

- arquitetura;
- responsabilidades;
- organização;
- regras de negócio;
- testes;
- padrões utilizados;
- duplicações;
- acoplamentos.

## 28.2. Forma recomendada de usar IA

A recomendação é guiar a IA por partes.

Exemplos:

```text
Implemente o controller de produto seguindo a estrutura atual do projeto.
```

```text
Implemente o service de produto, mantendo as regras de validação separadas do controller.
```

```text
Implemente o DAO de produto usando o padrão já existente no projeto.
```

```text
Implemente testes para os casos felizes do cadastro de produto.
```

```text
Implemente testes para os casos de exceção do cadastro de produto.
```

## 28.3. Responsabilidade pelo código

Foi reforçado que a responsabilidade pelo código é da equipe.

Não é aceitável justificar problemas dizendo que a IA gerou o código.

A equipe deve:

- revisar o código;
- entender o que foi gerado;
- testar;
- refatorar;
- corrigir;
- garantir que o projeto atende aos requisitos.

---

# 29. IA, contexto e arquitetura do código

## 29.1. IA trabalha com contexto limitado

A aula destacou que modelos de IA trabalham com uma janela de contexto.

Isso significa que a IA nem sempre enxerga todo o sistema ao mesmo tempo.

Ela pode estar focada apenas em uma parte do código.

## 29.2. Problema causado por contexto limitado

Se o projeto estiver mal organizado, a IA pode não perceber que já existe um componente pronto.

Consequências:

- código duplicado;
- componentes diferentes fazendo a mesma coisa;
- inconsistência visual;
- regras de negócio repetidas;
- estilos CSS divergentes;
- métodos semelhantes espalhados;
- aumento do acoplamento;
- perda de coesão;
- código macarrônico.

## 29.3. Exemplo de duplicação causada pela IA

Se já existe um componente de botão com estilo padronizado, mas a IA não sabe disso, ela pode criar outro botão com outra cor ou outro CSS.

Exemplo:

- padrão do projeto: botão vermelho;
- nova funcionalidade gerada pela IA: botão azul.

Isso indica que a IA ignorou o padrão existente.

O mesmo pode acontecer em código não visual, como:

- validações duplicadas;
- services repetidos;
- DAOs duplicados;
- queries semelhantes;
- componentes HTML recriados;
- funções utilitárias duplicadas.

## 29.4. Por que baixo acoplamento e alta coesão ajudam a IA?

Quando o código é bem organizado, a IA consegue trabalhar melhor.

Se tudo relacionado a aluno está em um módulo de aluno, a IA consegue localizar melhor os elementos relevantes.

Se tudo relacionado a impressão de cupom está em um módulo de cupom, a IA tem menos chance de recriar a mesma funcionalidade em outro lugar.

Organização ajuda a IA a:

- entender o escopo;
- reutilizar componentes;
- manter padrões;
- evitar duplicação;
- preservar consistência;
- gerar código mais adequado ao projeto.

---

# 30. Índice de componentes para desenvolvimento com IA

## 30.1. Ideia apresentada

Foi sugerido criar uma memória ou arquivo Markdown com um índice de componentes do projeto.

Esse arquivo deve registrar:

- quais componentes existem;
- o que cada componente faz;
- onde ele está no código;
- quando deve ser reutilizado.

## 30.2. O que pode ser considerado componente?

Na aula, componente foi definido de forma ampla.

Pode ser componente qualquer coisa reutilizável, como:

- função;
- classe;
- módulo;
- biblioteca;
- trecho de HTML;
- componente de interface;
- classe de serviço;
- DAO;
- validador;
- CSS;
- helper;
- template;
- padrão de tela.

## 30.3. Exemplo de índice de componentes

```markdown
# Índice de Componentes

## Componentes de Interface

### Botão primário
- Arquivo: `src/main/resources/templates/components/botao-primario.html`
- Uso: botões principais de confirmação
- Observação: deve usar o padrão visual definido para o sistema

### Mensagem de erro
- Arquivo: `src/main/resources/templates/components/mensagem-erro.html`
- Uso: exibir erros de validação em formulários

## Componentes de Validação

### Validador de CPF
- Arquivo: `src/main/java/app/validacao/ValidadorCpf.java`
- Uso: validar CPF em cadastros de pessoa

### Validador de datas
- Arquivo: `src/main/java/app/validacao/ValidadorData.java`
- Uso: validar campos de data

## Componentes de Autorização

### Autorizador
- Arquivo: `src/main/java/app/autorizacao/Autorizador.java`
- Uso: verificar permissões de usuários antes de executar ações protegidas

## Componentes de Persistência

### ProdutoDAO
- Arquivo: `src/main/java/app/produto/ProdutoDAO.java`
- Uso: acessar o banco de dados para operações relacionadas a Produto
```

## 30.4. Regra para o agente de IA

Foi sugerido criar uma regra para o agente de IA consultar esse índice antes de implementar algo novo.

Exemplo de regra:

```markdown
Antes de implementar qualquer funcionalidade, consulte o arquivo de índice de componentes.
Verifique se já existe algum componente, classe, função, template, DAO ou CSS que possa ser reutilizado.
Não recrie funcionalidades existentes.
Quando reutilizar um componente, mantenha o padrão arquitetural e visual já definido no projeto.
Se precisar criar um novo componente reutilizável, atualize o índice de componentes.
```

## 30.5. Benefícios do índice de componentes

Benefícios:

- reduz duplicação;
- aumenta reuso;
- melhora consistência;
- ajuda a IA a trabalhar com o projeto;
- reduz código divergente;
- melhora manutenção;
- diminui acoplamento desnecessário;
- reforça padrões internos do projeto.

---

# 31. Arquivos de memória para agentes de IA

## 31.1. Memórias em Markdown

Foi comentado que algumas ferramentas de IA usam arquivos Markdown como memória ou orientação do projeto.

Esses arquivos podem registrar:

- padrões arquiteturais;
- comandos;
- regras de estilo;
- estrutura do projeto;
- componentes reutilizáveis;
- decisões técnicas;
- regras para geração de código.

## 31.2. Exemplo de conteúdo para memória do projeto

```markdown
# Regras do Projeto

## Arquitetura

O projeto deve separar responsabilidades em:
- controller;
- service;
- DAO;
- model;
- validators;
- authorization.

## Reuso

Antes de criar uma nova classe, função, template ou CSS, verificar o índice de componentes.

## Autorização

Não espalhar regras de autorização diretamente pelos controllers.
Usar o serviço de autorização definido no projeto.

## Validações

Validações de formulário devem ficar em classes ou módulos próprios.
Controllers não devem concentrar regras complexas de validação.

## Persistência

Não escrever SQL diretamente nos controllers.
Usar DAOs para concentrar o acesso ao banco de dados.

## Testes

Sempre criar testes para casos felizes e casos de exceção.
```

---

# 32. Pipeline: qualidade, segurança, build e deploy

## 32.1. Etapas previstas

O pipeline do GitHub Actions deverá executar etapas como:

1. Qualidade.
2. Segurança.
3. Build.
4. Deploy.

## 32.2. Qualidade

A etapa de qualidade poderá verificar:

- se o código compila;
- se os testes passam;
- se a cobertura de testes é suficiente;
- se há problemas básicos de estrutura;
- se o código segue critérios mínimos.

## 32.3. Cobertura de testes

Foi mencionado que o sistema deverá ter pelo menos uma cobertura mínima de testes, em torno de 80%.

A cobertura indica quanto do código é executado pelos testes.

Entretanto, cobertura não garante sozinha que os testes são bons.

É necessário que os testes verifiquem comportamentos relevantes, incluindo:

- cenários válidos;
- cenários inválidos;
- erros esperados;
- permissões;
- validações;
- integrações importantes.

## 32.4. Segurança

A etapa de segurança deverá executar ferramentas para procurar vulnerabilidades básicas no código.

A ferramenta específica para Java será informada.

O objetivo é evitar colocar em produção código com falhas simples de segurança.

Essas ferramentas ajudam a encontrar problemas, mas não garantem ausência total de vulnerabilidades.

## 32.5. Build

A etapa de build prepara a aplicação para execução.

No contexto do projeto, isso envolve:

- compilar o código;
- empacotar a aplicação;
- gerar a imagem Docker.

## 32.6. Deploy

A etapa de deploy publica a aplicação no servidor.

Ela deve:

- acessar o servidor;
- atualizar a imagem;
- subir ou reiniciar o container;
- deixar o sistema disponível no endereço da equipe.

---

# 33. Integração de códigos diferentes

Foi destacado que uma funcionalidade pode funcionar isoladamente em uma branch, mas falhar quando integrada ao código de outra pessoa.

Exemplo:

- o código de uma pessoa passa nos testes;
- o código de outra pessoa também passa nos testes;
- depois do merge, os dois códigos juntos geram erro.

Por isso, é importante:

- revisar pull requests;
- executar testes;
- manter comunicação;
- atualizar a branch com frequência;
- evitar grandes alterações acumuladas;
- dividir tarefas de forma clara.

---

# 34. Avaliação com apoio de IA

## 34.1. Uso de IA na correção

Foi informado que a correção dos projetos contará com apoio de IA.

A IA poderá ser usada para verificar aspectos como:

- existência de Strategy;
- modularidade;
- acoplamento;
- organização do código;
- presença de testes;
- uso de autenticação;
- uso de autorização;
- logs;
- estrutura geral.

## 34.2. Avaliação conduzida pelo professor

A IA será conduzida pelo professor.

Ou seja, ela será usada como ferramenta de apoio, não como substituta automática da avaliação.

## 34.3. Uso da IA pelos alunos para autoavaliação

Os alunos também podem usar IA para avaliar o próprio projeto antes da entrega.

Exemplos de perguntas:

```text
Analise meu projeto e verifique se há uma implementação clara do padrão Strategy.
```

```text
Verifique se minha lógica de autorização está espalhada pelo sistema ou centralizada.
```

```text
Analise se há duplicação de código nos meus services e DAOs.
```

```text
Verifique se meus testes cobrem casos felizes e casos de exceção.
```

```text
Avalie se o projeto apresenta baixo acoplamento e alta coesão.
```

---

# 35. Desenvolvimento com IA e futuro da programação

## 35.1. Período de transição

A aula comentou que os estudantes estão vivendo um período de transição no desenvolvimento de software.

A programação com IA tende a mudar a forma como software é construído.

A forma de programar pode mudar bastante com IA. Mesmo que o desenvolvedor escreva menos código manualmente, continuará sendo essencial saber:

- orientar a IA;
- revisar código;
- testar;
- integrar;
- depurar;
- arquitetar sistemas;
- entender regras de negócio;
- tomar decisões técnicas.

## 35.2. Modelos de IA como ferramentas

Foi explicado que modelos de IA podem usar ferramentas.

Exemplos de ferramentas:

- terminal;
- shell;
- SSH;
- comandos de sistema;
- leitura e escrita de arquivos;
- execução de scripts;
- ferramentas de build;
- ferramentas de teste.

Quando um agente de IA programa, ele pode usar funções e programas auxiliares para executar tarefas.

## 35.3. Competência do desenvolvedor continua importante

Foi destacado que o que se consegue fazer com IA é proporcional à competência do desenvolvedor.

A IA não elimina a necessidade de compreender:

- arquitetura;
- modularidade;
- acoplamento;
- coesão;
- testes;
- segurança;
- regras de negócio;
- deploy;
- logs;
- manutenção;
- padrões de projeto.

Quanto melhor o desenvolvedor entende esses conceitos, melhor consegue orientar, revisar e corrigir o trabalho da IA.

## 35.4. Modelos, ferramentas e contexto

Na percepção apresentada na aula, os principais modelos comerciais têm se aproximado em várias capacidades.

Por isso, a diferença prática passa a depender bastante de:

- ferramentas disponíveis para o modelo;
- integrações;
- acesso ao terminal;
- acesso ao código;
- contexto fornecido;
- memória do projeto;
- regras de uso;
- capacidade do desenvolvedor de orientar a IA.

Também foi citado que há uma grande quantidade de modelos disponíveis em plataformas de IA, indicando que o ecossistema de IA já está bastante consolidado.

---

# 36. Erros como parte da experiência

A aula destacou que erros fazem parte do aprendizado em desenvolvimento de software.

A experiência foi associada ao acúmulo de erros vividos e resolvidos.

No contexto da disciplina, os alunos devem esperar problemas como:

- erro de deploy;
- erro de configuração;
- falha de build;
- conflito de merge;
- problema com banco de dados;
- problema de autenticação;
- problema de autorização;
- falha de teste;
- problema de segurança;
- exceção em produção.

Esses problemas são parte da formação prática.

---

# 37. Recomendações práticas para as equipes

## 37.1. Organização do trabalho

As equipes devem:

- criar issues;
- dividir tarefas;
- criar branches por funcionalidade;
- fazer commits frequentes;
- abrir pull requests;
- revisar código dos colegas;
- evitar mexer nos mesmos arquivos sem combinar;
- usar logs para depurar problemas;
- manter o projeto modularizado.

## 37.2. Organização do código

O código deve:

- evitar duplicação;
- separar responsabilidades;
- ter baixo acoplamento;
- ter alta coesão;
- usar componentes reutilizáveis;
- centralizar autorização;
- separar validações;
- usar DAOs para acesso ao banco;
- usar banco de dados;
- ter testes automatizados;
- ter logs.

## 37.3. Uso de IA

Ao usar IA, as equipes devem:

- pedir implementações pequenas e específicas;
- revisar tudo que for gerado;
- pedir testes;
- pedir casos de exceção;
- manter controle arquitetural;
- evitar aceitar código sem entender;
- criar memória de componentes;
- orientar a IA a reutilizar código existente.

---

# 38. Resumo dos requisitos da primeira entrega avaliativa

Para a entrega de 06 de julho de 2026, espera-se que o projeto tenha:

- CRUDs implementados;
- autenticação;
- autorização;
- logs;
- banco de dados;
- testes automatizados;
- validações rigorosas de formulário;
- pelo menos um uso do padrão Strategy;
- estratégias de quebra de acoplamento;
- componentes ou módulos bem organizados;
- código com preocupação de coesão;
- código sem duplicações desnecessárias;
- projeto publicado anteriormente em produção.

---

# 39. Orientações da Aula

- O projeto deve usar Docker.
- O frontend deve usar Thymeleaf e Bootstrap.
- O backend deve usar Javalin.
- O banco de dados deve ser PostgreSQL.
- Não será permitido escolher outra tecnologia, pois o foco da disciplina não é a tecnologia em si.
- O projeto será usado como base para estudar modularidade, reuso e padrões de projeto.
- As equipes devem se comunicar para evitar conflitos de merge.
- As equipes devem usar issues para registrar funcionalidades a serem implementadas.
- Cada funcionalidade deve ser desenvolvida em uma branch própria.
- Ninguém deve programar diretamente na branch `main`.
- Commits e pushs devem ser feitos com frequência.
- As equipes devem usar pull requests.
- É recomendável que uma pessoa revise o pull request da outra.
- As equipes devem exercitar criação de branch, pull request e merge.
- O código integrado à `main` será publicado em produção por meio de pipeline.
- Os alunos terão uma aula prática online sobre o processo de colocar o sistema no ar.
- A aula prática online foi marcada para 11 de junho de 2026, às 19h.
- Até 22 de junho de 2026, todos os projetos devem estar no ar.
- A entrega de 06 de julho de 2026 terá peso 1.
- A entrega de 20 de julho de 2026 terá peso 3.
- A entrega final terá peso 6.
- A primeira entrega avaliativa deve incluir CRUDs, autenticação, autorização, logs, banco de dados, testes automatizados, validações rigorosas, Strategy e estratégias de quebra de acoplamento.
- Os formulários devem ter validações rigorosas.
- Os testes devem cobrir casos felizes e casos de exceção.
- A IA pode ser usada para implementar o projeto, mas a equipe deve guiar a implementação.
- A IA não deve ser usada de forma que a equipe perca o controle sobre o código.
- A equipe deve revisar o código gerado por IA.
- A responsabilidade pelo código é da equipe.
- Os alunos podem pedir à IA sugestões de casos de exceção.
- Todos os projetos precisam ter autenticação.
- Todos os projetos precisam ter autorização.
- A autorização não deve ser uma lógica espalhada de qualquer forma pelo sistema.
- A lógica de autorização deve ser pensada como um módulo, classe, serviço ou componente.
- Os alunos devem pesquisar técnicas e estratégias de autenticação e autorização.
- O objetivo da disciplina é implementar módulos e compreender os conceitos, não apenas usar frameworks prontos.
- Os alunos devem buscar baixo acoplamento e alta coesão.
- Os alunos devem criar componentes, módulos e métodos reutilizáveis.
- Os alunos não devem repetir código desnecessariamente.
- Os alunos devem usar DAO para organizar o acesso ao banco de dados.
- Os alunos devem criar um índice de componentes para ajudar o agente de IA a reutilizar código existente.
- O pipeline terá etapas de qualidade, segurança, build e deploy.
- O sistema deverá ter cobertura mínima de testes.
- As ferramentas de segurança para Java serão informadas.
- Os alunos devem usar logs para diagnosticar problemas em produção.
- A aula presencial não deve ser tratada como aula remota.

---

# 40. Conceitos para se Aprofundar

- Docker
- Imagem Docker
- Container Docker
- Git
- GitHub
- Branch
- Branch `main`
- Commit
- Push
- Pull
- Merge
- Conflito de merge
- Issue
- Pull request
- Revisão de código
- GitHub Actions
- Pipeline
- Build
- Deploy
- SSH
- Secrets
- Produção
- Logs
- Debug em produção
- CRUD
- Validação de formulário
- Testes automatizados
- Casos felizes
- Casos de exceção
- Cobertura de testes
- Segurança em pipeline
- Autenticação
- Autorização
- Papéis de usuário
- Permissões
- Baixo acoplamento
- Alta coesão
- Modularidade
- Reuso
- Código macarrônico
- Controller
- Service
- Repository
- DAO
- Data Access Object
- Model
- Interface
- Contrato
- Strategy
- Observer
- Persistência
- JPA
- Hibernate
- Spring Data JPA
- Mapeamento objeto-relacional
- Componentes reutilizáveis
- Índice de componentes
- Memória de agentes de IA
- Contexto em modelos de IA
- Desenvolvimento guiado por IA

---

# 41. Questões para Revisão

1. Quais tecnologias devem ser usadas obrigatoriamente no projeto da disciplina?

2. Qual é o papel do Bootstrap no frontend?

3. Por que a disciplina não permite escolher livremente outra tecnologia?

4. O que é um conflito de merge?

5. Como a comunicação da equipe pode reduzir conflitos de merge?

6. Por que não se deve programar diretamente na branch `main`?

7. Qual é a vantagem de criar uma branch por funcionalidade?

8. O que é uma issue no GitHub?

9. Por que as funcionalidades devem ser registradas em issues?

10. O que é um pull request?

11. Qual é a relação entre pull request e revisão de código?

12. O que significa fazer merge na branch `main`?

13. Qual é o papel do GitHub Actions no projeto?

14. O que deve acontecer quando houver push ou merge na branch `main`?

15. O que é uma imagem Docker?

16. O que é um container Docker?

17. Para que serve o SSH no processo de deploy?

18. O que são secrets no GitHub?

19. Por que chaves de acesso não devem ser colocadas diretamente no código?

20. O que são logs?

21. Como os logs ajudam a depurar problemas em produção?

22. Qual é a primeira meta obrigatória para 22 de junho de 2026?

23. Quais são os principais requisitos da entrega de 06 de julho de 2026?

24. O que significa CRUD?

25. Quais validações devem ser consideradas em formulários?

26. O que são casos felizes em testes automatizados?

27. O que são casos de exceção em testes automatizados?

28. Qual é a diferença entre autenticação e autorização?

29. Por que não é adequado espalhar a lógica de autorização por todo o sistema?

30. Como a lógica de autorização pode ser melhor organizada?

31. O que é acoplamento?

32. O que significa baixo acoplamento?

33. O que é coesão?

34. O que significa alta coesão?

35. Por que juntar conceitos coesos melhora o projeto?

36. Por que separar conceitos pouco relacionados melhora o projeto?

37. Qual é a função de um controller?

38. Qual é a função de um service?

39. Qual é a função de um DAO?

40. Por que o uso de DAO ajuda a reduzir acoplamento com o banco de dados?

41. Qual é a função de um model?

42. Como uma interface ajuda a quebrar acoplamento?

43. No exemplo do restaurante, por que o cliente deve depender da interface `Restaurante` em vez de depender diretamente de `Pizzaria` ou `Hamburgueria`?

44. Quando pode ser necessário adaptar uma classe concreta a uma interface comum?

45. O que é o padrão Strategy?

46. Em que tipo de situação o Strategy pode ser útil?

47. O que é o padrão Observer?

48. Por que o uso de IA exige mais cuidado com modularidade e reuso?

49. O que significa dizer que a IA trabalha com contexto limitado?

50. Como o contexto limitado da IA pode gerar duplicação de código?

51. O que é um índice de componentes?

52. Como um índice de componentes pode ajudar um agente de IA?

53. Por que a responsabilidade pelo código continua sendo da equipe, mesmo quando ele é gerado por IA?

54. Quais etapas devem existir no pipeline de qualidade, segurança, build e deploy?

55. Por que cobertura de testes é importante?

56. Por que cobertura de testes não garante sozinha que os testes são bons?

57. Por que ferramentas de segurança serão usadas no pipeline?

58. Por que ferramentas automatizadas de segurança não garantem ausência total de vulnerabilidades?

59. Por que erros em produção fazem parte da experiência de aprendizagem da disciplina?

60. Como a IA pode ser usada para revisar o próprio projeto antes da entrega?
---
feature: projetos/UFPB.2026.1/APS2026.1/anotacoes-aps-2026.1/2026-05-11 web basico/attachments/2026-05-11 web basico 2026-05-11 08.40.53.excalidraw.svg
---
![](attachments/2026-05-11%20web%20basico%202026-05-11%2008.40.53.excalidraw.svg)
%%[🖋 Edit in Excalidraw](attachments/2026-05-11%20web%20basico%202026-05-11%2008.40.53.excalidraw.md)%%


# Fichamento da Aula — APS 2026.1

**Data:** 11 de maio de 2026  
**Disciplina:** APS 2026.1  
**Tema central:** Desenvolvimento web com Javalin, fundamentos de redes/HTTP e preocupações reais além do código

---

## 1. Código como “ponta do iceberg”

O professor iniciou a aula destacando que, em sistemas reais em produção, o código é apenas a “ponta do iceberg”.

Segundo ele, quando se desenvolve software para uso real, há inúmeras preocupações que vão muito além de escrever classes, métodos e comandos.

Entre essas preocupações, foram citadas:

- Manutenibilidade;
- Monitoramento;
- Segurança;
- Auditoria;
- Gestão de incidentes;
- Backup;
- Plano de recuperação de backup;
- Parte administrativa do sistema;
- Tolerância a falhas;
- Escalabilidade;
- Implantação;
- Processos de suporte e operação.

O professor explicou que a inteligência artificial já consegue gerar código com qualidade acima da média do programador comum, mas isso não elimina a necessidade de formação técnica sólida.

A IA pode implementar código, mas, se o desenvolvedor não souber orientar corretamente, o sistema pode ficar ruim, frágil ou difícil de manter.

---

## 2. Uso de IA na programação

O professor mostrou uma ferramenta chamada **AntiGravity**, da Google, descrita como um “VS Code enrustido” com Gemini integrado.

Ele apresentou um exemplo de sistema gerado a partir de um prompt simples:

> “Implemente CRUD de usuário utilizando Javalin e Thymeleaf com persistência em arquivo usuários.csv.”

Com esse prompt, a IA foi capaz de gerar um sistema funcional com:

- Cadastro de usuários;
- Login e senha;
- Controladores;
- Persistência em arquivo CSV;
- Interface web.

O professor destacou que esse tipo de código não precisa mais ser feito manualmente em muitos casos. Porém, alertou que a IA tende a seguir o menor caminho para entregar o que foi pedido.

Isso pode gerar uma falsa sensação de conclusão:

> O sistema funciona, mas pode não estar pronto para a vida real.

---

## 3. POC, protótipo e MVP

### 3.1 POC — Proof of Concept

POC significa **Proof of Concept**, ou **prova de conceito**.

Na aula, a POC foi apresentada como uma forma pequena de validar uma ideia ou possibilidade técnica.

### 3.2 Protótipo

O professor explicou que um protótipo é algo feito para testar se o caminho está correto antes de construir o produto real.

Ele usou o exemplo de uma garrafa:

- Para produzir uma garrafa real, seria necessário maquinário, moldes, fornecedores, materiais e cadeia logística;
- Antes de investir nisso, é melhor fazer um protótipo;
- O protótipo permite verificar forma, tampa, encaixes e funcionamento;
- Depois da validação, parte-se para a produção real.

No software, o protótipo pode ser algo simples, como:

- Um desenho no Canva;
- Uma tela no Figma;
- Um rascunho de relatório;
- Uma simulação clicável para mostrar ao cliente.

O protótipo pode ser descartável.

### 3.3 MVP — Minimum Viable Product

MVP significa **Minimum Viable Product**, ou **Produto Mínimo Viável**.

O professor destacou que muitas pessoas tratam MVP como se fosse protótipo, mas, na visão apresentada na aula, o MVP já deve ser um produto real no mercado.

Ele resolve uma dor pequena, mas real, do cliente.

---

## 4. Exemplo de desenvolvimento rápido com IA

O professor relatou uma situação com um parceiro chamado Porto/Portomar.

Durante uma reunião, surgiu a ideia de criar um aplicativo para:

- Corretores acessarem informações;
- Clientes acompanharem a produção da obra.

O professor respondeu que apresentaria algo na semana seguinte. Depois, desenvolveu uma versão do sistema na sexta-feira à noite.

Ele comentou que acabou exagerando no escopo, incluindo:

- Sistema multitenant;
- Troca de mensagens;
- Feed;
- Envio de notícias;
- Álbum de fotos;
- Suporte a várias construtoras.

### 4.1 Multitenant

O professor explicou que **tenant** está relacionado à quantidade de clientes diferentes.

Um sistema **multitenant** é um sistema preparado para atender vários clientes ou empresas diferentes no mesmo serviço.

No exemplo, embora o sistema tenha começado para uma construtora, ele foi pensado para ser vendido também para outras construtoras.

---

## 5. Gestão de incidentes em sistemas reais

O professor explicou que sistemas reais em produção podem passar por incidentes, especialmente quando sustentam operações importantes de empresas.

A ideia central foi mostrar que, além de desenvolver o sistema, é necessário manter processos para lidar com falhas e indisponibilidades.

Entre os pontos destacados estão:

- Detectar problemas rapidamente;
- Comunicar o cliente ou usuário impactado;
- Investigar a causa do problema;
- Recuperar o serviço;
- Registrar o que aconteceu;
- Identificar ações para evitar que o problema se repita;
- Melhorar continuamente o processo de operação.

O professor reforçou que, em incidentes, o foco não deve ser procurar culpados, mas entender o que falhou no processo e como melhorar.

---

## 6. Monitoramento com endpoint `/health`

O professor explicou que sistemas em produção devem ter mecanismos de monitoramento.

Um exemplo citado foi o uso de um endpoint chamado:

```
/health
```

A palavra **health** significa “saúde”.

Esse endpoint serve para indicar se o sistema está saudável.

### 6.1 Uptime Kuma

O professor mostrou o **Uptime Kuma**, um serviço de monitoramento open source.

Ele explicou que o Uptime Kuma verifica periodicamente se um sistema está respondendo.

Exemplo de funcionamento:

- O monitor envia uma requisição para o sistema;
- O sistema responde “OK”;
- O monitor marca o serviço como “up”.

O professor comentou que o Uptime Kuma é usado inclusive por empresas maiores, como a Phoebus, entre outros mecanismos de monitoramento.

### 6.2 Monitoramento adequado

O professor destacou que o monitoramento deve verificar não apenas se a API responde, mas também se os componentes essenciais do sistema estão funcionando.

Por exemplo, um sistema só deve ser considerado saudável se:

- A API estiver no ar;
- O banco de dados estiver acessível;
- Os serviços essenciais estiverem respondendo corretamente.

Uma prática citada foi fazer uma consulta simples ao banco de dados dentro do endpoint de saúde.

---

## 7. Backup e plano de recuperação

O professor reforçou que não basta fazer backup.

É necessário ter:

- Backup;
- Plano de recuperação de backup;
- Plano de recuperação de incidentes.

O backup deve fazer parte de uma estratégia maior de continuidade do serviço.

---

## 8. Processos de comunicação em emergências

O professor explicou que sistemas em produção precisam de processos claros de comunicação em situações emergenciais.

Isso inclui definir:

- Quem deve ser acionado;
- Como essas pessoas serão acionadas;
- Em quais situações o acionamento deve ocorrer;
- Quais responsabilidades cada pessoa possui;
- Como garantir que a equipe consiga responder a problemas sérios.

O professor reforçou a ideia de melhoria de processo: quando algo falha, a equipe deve analisar o processo e ajustá-lo para reduzir riscos futuros.

---

## 9. On-call

O professor apresentou o conceito de **on-call**.

Uma pessoa on-call é alguém que fica disponível para responder a incidentes.

No exemplo citado da Phoebus, sistemas precisam atender operações de cartão de crédito de empresas no Brasil e fora do país, exigindo alto nível de qualidade.

A pessoa on-call pode estar no fim de semana, mas precisa cumprir protocolos, por exemplo:

- Estar disponível;
- Ter conectividade;
- Ter notebook;
- Conseguir ficar online em até 30 minutos.

O professor explicou que, em empresas, a pessoa é paga por essa disponibilidade.

---

## 10. Backup e plano de recuperação

O professor explicou que, durante o incidente, quando o tempo de indisponibilidade estava aumentando, ele iniciou também a preparação para recuperação de backup.

O sistema tinha backup a cada 60 minutos.

Como a empresa havia fechado à noite e o incidente ocorreu no início do expediente, o backup estava adequado e não haveria perda de dados.

O professor reforçou que não basta fazer backup.

É necessário ter:

- Backup;
- Plano de recuperação de backup;
- Plano de recuperação de incidentes.

---

## 11. Auditoria

Auditoria foi apresentada como a existência de logs que permitem identificar ações realizadas no sistema.

Exemplos de perguntas que logs de auditoria devem responder:

- Quem cadastrou um pedido?
- Quem mudou o estado de uma venda?
- Quem marcou algo como vendido?
- Quem marcou que recebeu o dinheiro?
- Em que momento a ação aconteceu?

A auditoria foi relacionada também à segurança.

---

## 12. Parte administrativa do sistema

O professor explicou que muitos sistemas começam com um CRUD simples, mas depois precisam de funcionalidades administrativas.

Exemplo:

O cliente pede um sistema para gerenciar clientes. O desenvolvedor faz apenas o CRUD de clientes.

Depois, surgem necessidades como:

- Usuário perdeu a senha;
- Usuário precisa trocar senha;
- Alguém cadastrou algo errado;
- Alguém precisa corrigir dados;
- Alguém precisa administrar usuários.

Se o sistema não tiver uma parte administrativa, o desenvolvedor acaba tendo que alterar dados diretamente no banco.

---

## 13. Tolerância a falhas

O professor explicou que sistemas reais precisam lidar com falhas.

Exemplos de falhas citadas:

- Servidor pode dar problema;
- HD pode falhar;
- Sistema pode cair;
- Rede pode ficar fora do ar;
- Internet da empresa pode cair.

No caso da Lê Pessoa, o professor recomendou que a empresa tivesse duas conexões de internet.

A empresa considerou usar uma conexão via satélite, porque já havia ocorrido uma situação em que um caminhão arrancou fios na frente da loja.

Também foram mencionados:

- Roteador com nobreak;
- Computadores com nobreak.

O professor reforçou que a IA pode ajudar a codificar, mas cabe ao desenvolvedor se preocupar com esse tipo de questão.

---

## 14. WordPress, SSH, FTP e SFTP

O professor relatou outro caso envolvendo um sistema em WordPress.

Ele disse que o site estava fora do ar ou muito lento, e o prestador de serviço alegava que havia muitos acessos.

Ao olhar os logs, havia cerca de mil acessos por dia, o que o professor afirmou não ser suficiente para causar grande impacto.

### 14.1 WordPress

WordPress foi descrito como a maior plataforma do mundo para sites e blogs.

O professor criticou a estrutura do WordPress, chamando-o de sistema ruim e “Frankenstein mal feito”.

### 14.2 SSH

SSH foi explicado como um protocolo seguro para acessar remotamente um servidor.

Com SSH, é possível acessar o servidor pelo terminal e executar comandos.

### 14.3 FTP

FTP foi explicado como um protocolo de transferência de arquivos.

Com FTP, é possível:

- Conectar ao servidor;
- Baixar arquivos;
- Enviar arquivos.

### 14.4 SFTP

SFTP foi explicado como uma versão segura do FTP.

O professor destacou que FTP/SFTP e SSH não são a mesma coisa.

---

## 15. Portas de rede

A partir da confusão entre SSH e FTP, o professor iniciou uma explicação sobre portas.

### 15.1 Sistema operacional e processos

Um computador possui um sistema operacional.

Sobre o sistema operacional, rodam aplicações como:

- Chrome;
- Word;
- Outros programas.

Cada programa em execução pode ser entendido como um processo.

O professor explicou que um processo é algo que funciona dentro do sistema operacional.

### 15.2 IP

O IP foi apresentado como o endereço usado para comunicação na rede.

Exemplo usado pelo professor:

```text
10.0.1.54
```

Esse era o IP do notebook dele no laboratório.

### 15.3 Porta

A porta é o número que permite ao sistema operacional saber para qual processo entregar uma mensagem recebida pela rede.

Um computador pode ter vários processos, mas cada processo que recebe mensagens de rede precisa estar associado a uma porta.

O professor afirmou:

- Uma porta pode estar ligada a apenas um processo;
- Não é possível ter SSH e SFTP usando a mesma porta ao mesmo tempo.

### 15.4 Exemplo com Javalin

O professor iniciou uma aplicação Java/Javalin na porta 8000.

Os alunos acessaram o computador dele usando:

```text
http://10.0.1.54:8000
```

Esse endereço acessava o sistema em execução no notebook do professor.

---

## 16. Rede local — LAN

O professor explicou que todos os computadores do laboratório estavam ligados em uma rede local.

LAN significa **Local Area Network**.

Na rede local, as máquinas possuem IPs da mesma rede.

Quando um computador envia uma mensagem para outro IP da rede, a mensagem passa pelo equipamento de rede e chega às máquinas.

Apenas a máquina cujo IP corresponde à mensagem aceita a comunicação.

---

## 17. Servidor web e aplicação Java

O professor explicou que, ao iniciar o projeto, estava rodando:

- Um programa Java;
- O framework Javalin;
- Um servidor web Jetty por baixo dos panos.

O Javalin usa um servidor web para receber requisições HTTP.

### 17.1 Servidores web citados

Foram citados exemplos de servidores web:

- Apache HTTP;
- Nginx;
- Caddy;
- Tomcat;
- Jetty;
- Node.js.

Tomcat e Jetty foram mencionados como servidores web relacionados a aplicações Java.

---

## 18. URL

O professor analisou uma URL como exemplo:

```text
http://10.0.1.54:8000/
```

A URL foi explicada em partes:

- `http://` — protocolo;
- `10.0.1.54` — servidor, ou seja, o computador que se quer acessar;
- `8000` — porta;
- `/` — recurso ou endpoint solicitado.

---

## 19. Protocolo HTTP

O professor definiu protocolo como um conjunto de regras ou acordo de comunicação.

Ele comparou o protocolo com a língua portuguesa:

- O professor fala português;
- Os alunos entendem português;
- Isso permite comunicação.

No caso de computadores, o HTTP define regras para que programas conversem entre si.

### 19.1 Verbos HTTP

Foram citados os principais verbos HTTP:

- GET;
- POST;
- PUT;
- DELETE;
- PATCH.

Na aula, o professor enfatizou principalmente GET e POST.

### 19.2 GET

GET foi explicado como o comando usado para recuperar ou pegar algo do servidor.

Originalmente, o servidor possuía arquivos, e o cliente fazia GET para pegar um arquivo.

Exemplo:

```text
GET /index.html
```

### 19.3 POST

POST foi explicado como o verbo usado para enviar informações para o servidor.

No exemplo do login, ao enviar e-mail e senha, o navegador fazia uma requisição POST.

---

## 20. DNS

O professor explicou que, normalmente, usuários não digitam IPs para acessar sites.

Eles digitam nomes, como o site da UFPB.

O serviço que relaciona nomes a IPs é o DNS.

DNS significa **Domain Name System**.

O DNS foi explicado como uma tabela que relaciona um nome a um IP.

---

## 21. Localhost e 127.0.0.1

O professor explicou que toda máquina possui um endereço local padrão:

```text
127.0.0.1
```

Esse endereço aponta para a própria máquina.

Também foi apresentado o nome:

```text
localhost
```

O `localhost` é um nome associado ao IP `127.0.0.1`.

No desenvolvimento de software, é comum usar `localhost` ou `127.0.0.1` para acessar serviços rodando na própria máquina.

---

## 22. Portas padrão HTTP e HTTPS

O professor explicou que servidores HTTP possuem portas padrão.

As portas citadas foram:

- HTTP: porta 80;
- HTTPS: porta 443.

Quando um site usa essas portas padrão, o usuário não precisa digitar a porta na URL.

### 22.1 HTTPS

HTTPS foi explicado como uma conexão segura e criptografada.

O professor destacou que o cadeado no navegador indica que a comunicação entre o computador do usuário e o servidor está criptografada.

Mas o cadeado não garante que o servidor em si seja confiável.

Ele explicou que um atacante poderia ter um servidor malicioso com conexão criptografada.

---

## 23. Sniffer e segurança em redes

O professor explicou o conceito de **sniffer**.

Um sniffer é um programa que monitora o tráfego da rede.

Ele permite ver mensagens trafegando na rede.

Em uma rede sem criptografia, senhas e dados podem ser capturados.

O professor alertou sobre riscos em redes públicas, como:

- Lan houses;
- Cafeterias;
- Shoppings;
- Wi-Fi gratuito.

Se a conexão for segura, quem estiver monitorando verá apenas dados embaralhados.

---

## 24. Cliente e servidor

O navegador foi apresentado como um **cliente HTTP**.

Exemplos de navegadores:

- Chrome;
- Firefox;
- Safari.

O servidor foi definido como um computador com algum programa escutando na rede.

Quando se acessa um site, acessa-se um computador em algum lugar, com uma porta aberta e um programa escutando nessa porta.

---

## 25. IPs locais e roteáveis

O professor explicou que alguns IPs são usados em redes locais e não são roteáveis na internet.

Exemplos citados:

- Redes `10.0.x.x`;
- Redes `192.168.x.x`;
- O endereço local `127.0.0.1`.

Esses IPs não podem ser acessados diretamente por alguém fora da rede local.

Para que uma máquina seja acessível pela internet, é necessário um IP roteável ou algum mecanismo intermediário.

---

## 26. Ngrok

O professor apresentou o **Ngrok** como um serviço útil no desenvolvimento.

O Ngrok permite expor um serviço local para acesso externo.

Ele funciona criando uma conexão entre a máquina local e o serviço do Ngrok.

Depois, outras pessoas acessam o Ngrok, e o Ngrok encaminha as requisições para a máquina local.

O professor explicou que o Ngrok usa uma conexão reversa:

- O computador local se conecta ao Ngrok;
- O Ngrok recebe requisições externas;
- O Ngrok repassa essas requisições para a máquina local.

Ele também explicou que o Ngrok atua como um gateway.

### 26.1 Gateway

Gateway foi explicado como um elemento que pega uma requisição e a reencaminha.

---

## 27. Estrutura da aplicação com Javalin

O professor explicou a estrutura geral da aplicação:

- O navegador faz uma requisição HTTP;
- A requisição chega à porta 8000;
- O Javalin está rodando em cima do Jetty;
- O Javalin mapeia endpoints para métodos Java;
- O método Java processa a requisição;
- O servidor devolve uma resposta.

### 27.1 Request e response

Foram apresentados dois conceitos:

- **Request:** requisição enviada pelo cliente ao servidor;
- **Response:** resposta enviada pelo servidor ao cliente.

A resposta pode conter diferentes tipos de conteúdo:

- HTML;
- Imagem;
- PDF;
- Arquivo do Word;
- Outros arquivos.

---

## 28. HTML

HTML foi apresentado como uma linguagem de marcação.

O professor enfatizou que HTML não é linguagem de programação.

HTML serve para descrever elementos de uma página, como:

- Título;
- Parágrafo;
- Imagem;
- Cabeçalho;
- Corpo da página.

### 28.1 Exemplo de HTML mostrado em aula

```html
<html>
  <head>
    <title>Título da página</title>
  </head>
  <body>
    <h1>Título da página</h1>
    <p>Isso é um parágrafo.</p>
  </body>
</html>
```

No exemplo:

- `<html>` define o documento HTML;
- `<head>` define o cabeçalho;
- `<title>` define o título da página;
- `<body>` define o corpo;
- `<h1>` define um cabeçalho grande;
- `<p>` define um parágrafo.

---

## 29. CSS

CSS foi apresentado como um conjunto de marcações usado para alterar o HTML.

Com CSS, é possível definir:

- Layout;
- Visualização;
- Aparência dos elementos na tela.

O professor afirmou que os alunos devem entender o básico de HTML e CSS.

---

## 30. Projeto de exemplo: sistema de usuários

Na segunda parte da aula, o professor apresentou o sistema em funcionamento.

O sistema tinha:

- Tela de criação de conta;
- Nome;
- E-mail;
- Senha;
- Login;
- Listagem de usuários;
- Adição de usuário;
- Edição de usuário;
- Remoção de usuário.

O professor observou que era possível acessar a página de usuários mesmo sem login.

Isso foi proposital para simplificar o exemplo. O controle de acesso seria tratado em aula futura.

---

## 31. GET e POST no sistema de login

O professor explicou que, ao acessar `/login`, o navegador faz uma requisição GET.

Ao preencher e enviar o formulário de login, o navegador faz uma requisição POST.

### 31.1 GET para login

Ao acessar:

```text
/login
```

O navegador pede ao servidor a página de login.

### 31.2 POST para envio dos dados

Ao enviar e-mail e senha, o navegador envia informações para o servidor.

Esse envio usa POST.

---

## 32. Maven

O professor explicou que o projeto Java usa Maven.

Maven foi apresentado como uma ferramenta para:

- Padronizar a organização dos arquivos;
- Definir bibliotecas e versões;
- Fazer o build;
- Compilar o programa Java;
- Configurar o classpath.

### 32.1 Estrutura Maven

A estrutura citada foi:

```text
src/main/java
src/test
```

O código fonte Java fica em:

```text
src/main/java
```

A partir desse diretório, aparecem os pacotes do projeto.

### 32.2 Arquivo `pom.xml`

O arquivo `pom.xml` define as dependências do projeto.

O professor mostrou dependências como:

- Javalin 6.7.0;
- Thymeleaf 3.1.5;
- JUnit Jupiter;
- Plugin Maven na versão 3.4.0.

O professor explicou que, ao compartilhar o projeto com o mesmo `pom.xml`, todos trabalham com as mesmas versões das bibliotecas.

Isso evita problemas do tipo:

> “Na minha máquina funciona, na sua não.”

---

## 33. Docker

O professor apresentou Docker como uma forma de criar um ambiente isolado para o programa.

Ele explicou que, se o Maven ajuda a garantir as mesmas bibliotecas, o Docker ajuda a garantir o mesmo ambiente de execução.

Com Docker, é possível especificar:

- Banco de dados;
- Sistema operacional;
- Java;
- Outras dependências.

O professor diferenciou Docker de virtualização tradicional.

Segundo ele:

- Virtualização inicia um sistema operacional inteiro usando parte dos recursos do computador;
- Docker cria uma camada isolada, compartilhando o sistema operacional.

O professor afirmou que, se uma imagem Docker roda no computador do desenvolvedor, a mesma imagem pode ir para produção.

---

## 34. Uso de IA para estudar código

O professor mostrou o uso do GitHub Copilot para explicar um `Dockerfile`.

Ele digitou uma pergunta pedindo explicação do arquivo e do que precisava saber para entendê-lo.

A IA explicou o Dockerfile linha por linha.

O professor incentivou os alunos a usarem IA para estudar, entender arquivos e aprender tecnologias.

---

## 35. App.java e mapeamento de rotas no Javalin

O professor mostrou que a aplicação começa em uma classe `App.java`, com um método `main`.

Nessa classe, são criados objetos como:

- Repository;
- Service;
- Aplicação Javalin.

O Javalin é criado com algo semelhante a:

```java
Javalin app = Javalin.create(...);
```

Depois, são configuradas páginas de erro e rotas.

### 35.1 Exemplo de rota

O professor mostrou a ideia de uma rota como:

```java
app.get("/login", LoginController::mostrarPaginaDeLogin);
```

Isso significa:

- Quando chegar uma requisição GET para `/login`;
- O Javalin deve chamar o método `mostrarPaginaDeLogin` do `LoginController`.

---

## 36. Context no Javalin

O professor explicou que o `Context`, abreviado como `ctx`, encapsula informações do protocolo HTTP em um objeto Java.

O Javalin pega as informações HTTP e as transforma em um objeto Java para facilitar o trabalho do programador.

Exemplo de recuperação de parâmetro de formulário:

```java
String nome = ctx.formParam("nome");
```

---

## 37. Formulários HTML

O professor mostrou o código fonte da página de login.

O formulário HTML possuía:

- `action`, indicando para onde os dados devem ser enviados;
- `method`, indicando o método HTTP usado;
- Campos `input`, como e-mail e senha.

Exemplo conceitual:

```html
<form action="/login" method="post">
  <input type="email" id="email" name="email">
  <input type="password" id="senha" name="senha">
  <button type="submit">Entrar</button>
</form>
```

O professor explicou que os nomes dos campos no HTML precisam bater com os nomes usados no backend.

Se o formulário envia `email`, o backend precisa buscar `email`.

Se houver diferença, como `email_` no HTML e `email` no Java, haverá problema.

---

## 38. Renderização

Renderizar foi explicado como construir ou montar a página que será exibida para o cliente.

No modelo usado na aula:

- O cliente chama o servidor;
- O servidor processa a requisição;
- O servidor pega uma página/template;
- O servidor coloca essa página na resposta;
- O navegador exibe a página.

---

## 39. Server-side rendering

O professor explicou que o modelo usado no projeto é **server-side rendering**.

Nesse modelo, o servidor constrói a página e envia o HTML pronto para o cliente.

O professor diferenciou esse modelo de uma arquitetura em que o cliente baixa uma aplicação inteira em JavaScript, que passa a rodar no navegador e faz requisições ao servidor.

O professor afirmou que server-side rendering foi escolhido porque é mais simples para os alunos e resolve muitos problemas básicos de internet.

---

## 40. Thymeleaf

O professor mostrou que as páginas ficam em:

```text
src/main/resources/templates
```

Essas páginas são templates usados pelo Thymeleaf.

O Thymeleaf pega o template HTML e ajuda a construir a resposta enviada ao navegador.

Exemplo de template citado:

```text
/login/login.html
```

---

## 41. Bootstrap

O professor explicou que o projeto usa Bootstrap.

Bootstrap foi apresentado como uma biblioteca de componentes HTML.

Ela permite deixar páginas mais bonitas e organizadas usando classes prontas.

Exemplos citados de classes Bootstrap:

```html
<div class="row justify-content-center">
```

O professor explicou que, nesse exemplo:

- `row` indica uma linha;
- `justify-content-center` centraliza o conteúdo.

### 41.1 Componentes e exemplos do Bootstrap

O professor mostrou a documentação do Bootstrap, incluindo exemplos de:

- Tabelas;
- Cores;
- Imagens;
- Thumbnails;
- Formulários;
- Layout;
- Containers;
- Colunas.

Ele recomendou seguir padrões conhecidos de interface, pois os usuários já estão acostumados com eles.

### 41.2 Modal

O professor explicou o que é um modal.

Um modal é um componente de interface que aparece sobre a tela principal.

Ele pediu à IA que alterasse o comportamento de erro de login para exibir um modal indicando login errado.

A IA modificou o template e passou a exibir o erro em um modal do Bootstrap.

---

## 42. Padrões de projeto, modularidade e IA

O professor afirmou que está programando intensamente com IA e aplicando padrões de projeto em seus projetos.

Ele citou o uso de padrões para melhorar a manutenibilidade.

Exemplo mencionado:

- Aplicar um **Observer** em notificações para quebrar acoplamento.

O professor explicou que a IA sabe implementar padrões de projeto, mas precisa ser orientada.

Se o desenvolvedor não pedir, a IA pode não aplicar o padrão.

---

## 43. Modularidade, contexto e redução de tokens

O professor relacionou modularidade com uso eficiente de IA.

A IA trabalha com contexto.

Se um sistema é muito grande, a IA não consegue colocar todo o código no contexto de uma vez, ou isso consumiria muito processamento e dinheiro.

Quando o sistema é modular:

- A IA consegue focar nos pontos certos;
- O contexto necessário é menor;
- Há menos consumo de tokens;
- A chance de erro diminui;
- A manutenção fica melhor.

### 43.1 Catálogo de reutilização

O professor comentou que, em suas regras de uso de IA, pede a criação de um catálogo de coisas reutilizáveis.

Esse catálogo pode ser um arquivo Markdown indicando onde estão componentes reutilizáveis.

Exemplo:

- Se há um componente de listagem, ele deve ser reutilizado em outras listagens;
- Não se deve copiar e colar código;
- Deve-se importar e reutilizar o componente.

O professor explicou que o ser humano precisa orientar a IA a reutilizar, pois nem sempre ela saberá sozinha que algo será reutilizável.

---

## 44. Mensagem final sobre o mercado

O professor reforçou que codificar, por si só, está perdendo valor.

O diferencial está em saber:

- Projetar sistemas;
- Manter sistemas;
- Implantar sistemas;
- Monitorar sistemas;
- Garantir segurança;
- Pensar em incidentes;
- Usar IA com orientação técnica;
- Aplicar modularidade e padrões.

Ele alertou que haverá muitos sistemas ruins sendo produzidos por IA por pessoas que não sabem o que estão fazendo.

Segundo ele, isso pode gerar casos de invasões, quedas de sistemas e problemas sérios nos próximos anos.

---

# Orientações do Professor

- Experimentar a ferramenta AntiGravity, da Google.
- Baixar o projeto da aula em casa.
- Estudar e brincar com o projeto.
- Fazer modificações no projeto.
- Mudar cores, telas e elementos para se familiarizar com o código.
- Ler sobre HTML e CSS até a próxima segunda-feira.
- Entender o básico de HTML.
- Entender o básico de CSS.
- Rodar um programa Java pela linha de comando, caso ainda não tenha feito isso.
- Estudar Docker.
- De preferência, montar o projeto usando Docker.
- Usar vídeos, materiais e prática para aprender Docker.
- Não apenas assistir vídeos: é necessário fazer.
- Estudar Javalin.
- Consultar a documentação do Javalin.
- Estudar Thymeleaf.
- Estudar Bootstrap.
- Usar IA como apoio para estudar código e tecnologias.
- Usar IA com paciência, um passo de cada vez.
- Não tentar aprender tudo “na mão”, mas entender o que está acontecendo.
- Aprender Sistemas Operacionais com seriedade.
- Aprender Redes de Computadores com seriedade.
- Aprender Sistemas Distribuídos e Banco de Dados com seriedade.
- Seguir padrões de interface quando fizer sentido, para facilitar a usabilidade.
- Estudar bastante.

---

# Conceitos para se Aprofundar

- Manutenibilidade;
- Inteligência artificial aplicada à programação;
- POC — Proof of Concept;
- Protótipo;
- MVP — Minimum Viable Product;
- Multitenancy;
- Gestão de incidentes;
- Monitoramento;
- Endpoint `/health`;
- Uptime Kuma;
- Backup;
- Plano de recuperação de backup;
- Auditoria;
- Logs de auditoria;
- Tolerância a falhas;
- On-call;
- WordPress;
- SSH;
- FTP;
- SFTP;
- Sistema operacional;
- Processo;
- IP;
- Porta;
- LAN;
- Servidor web;
- Apache HTTP;
- Nginx;
- Caddy;
- Tomcat;
- Jetty;
- Node.js;
- URL;
- HTTP;
- HTTPS;
- GET;
- POST;
- PUT;
- DELETE;
- PATCH;
- DNS;
- Localhost;
- `127.0.0.1`;
- Sniffer;
- Cliente HTTP;
- Servidor;
- IP local;
- IP roteável;
- Ngrok;
- Gateway;
- Java Runtime Environment;
- JVM;
- Javalin;
- Thymeleaf;
- Maven;
- `pom.xml`;
- Docker;
- Dockerfile;
- Docker Compose;
- HTML;
- CSS;
- Formulários HTML;
- Server-side rendering;
- Bootstrap;
- Modal;
- Padrões de projeto;
- Observer;
- Modularidade;
- Reutilização de componentes;
- Catálogo de componentes reutilizáveis;
- Contexto e tokens no uso de IA.

---

# Questões para Revisão

1. Por que o professor afirma que o código é apenas a “ponta do iceberg” no desenvolvimento de software?
2. Quais preocupações existem em um sistema real além da implementação do código?
3. Por que a IA pode gerar uma falsa sensação de sistema pronto?
4. O que é uma POC?
5. Qual é a diferença entre protótipo e MVP apresentada na aula?
6. O que significa dizer que um sistema é multitenant?
7. O que aconteceu no incidente relatado com o sistema da Lê Pessoa?
8. Por que o endpoint `/health` não detectou o problema imediatamente?
9. Que melhoria foi feita no endpoint `/health` depois do incidente?
10. O que é o Uptime Kuma?
11. Por que o professor afirma que o processo, e não uma pessoa específica, precisava ser melhorado no incidente?
12. O que significa estar on-call?
13. Por que não basta apenas fazer backup?
14. O que é um plano de recuperação de backup?
15. O que são logs de auditoria?
16. Por que uma parte administrativa é importante em sistemas reais?
17. O que é tolerância a falhas?
18. Por que uma empresa pode precisar de duas conexões de internet?
19. O que é SSH?
20. Qual é a diferença entre SSH e FTP?
21. O que é uma porta em redes de computadores?
22. Por que uma porta não pode estar ligada a dois serviços diferentes ao mesmo tempo?
23. O que é um IP?
24. O que é uma LAN?
25. O que é uma URL e quais partes foram explicadas na aula?
26. O que é um protocolo?
27. Quais verbos HTTP foram citados?
28. Qual é a diferença entre GET e POST?
29. O que é DNS?
30. Para que serve o `localhost`?
31. O que representa o IP `127.0.0.1`?
32. Quais são as portas padrão de HTTP e HTTPS?
33. O que o cadeado do navegador realmente indica?
34. O que é um sniffer?
35. Por que redes públicas podem representar risco de segurança?
36. O que é um servidor?
37. Por que IPs como `10.x.x.x` e `192.168.x.x` não são acessíveis diretamente pela internet?
38. Para que serve o Ngrok?
39. O que é um gateway?
40. Como o Javalin mapeia uma rota para um método Java?
41. O que é o objeto `Context` no Javalin?
42. O que é HTML?
43. O que é CSS?
44. O que é Maven e qual problema ele ajuda a resolver?
45. Para que serve o arquivo `pom.xml`?
46. O que é Docker?
47. Qual é a diferença apresentada entre Docker e virtualização?
48. O que é server-side rendering?
49. Para que serve o Thymeleaf no projeto?
50. Para que serve o Bootstrap?
51. O que é um modal?
52. Por que padrões de projeto continuam importantes usando IA?
53. Como a modularidade ajuda no uso de IA para programação?
54. O que é um catálogo de componentes reutilizáveis?
55. Por que codificar, por si só, tende a ter menos valor no mercado segundo o professor?

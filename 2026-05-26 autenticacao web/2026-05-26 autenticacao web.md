---
feature: projetos/UFPB.2026.1/APS2026.1/anotacoes-aps-2026.1/2026-05-26 autenticacao web/attachments/2026-05-26 autenticacao web 2026-05-25 08.28.13.excalidraw.svg
---
![2026-05-26 autenticacao web 2026-05-25 08.28.13.excalidraw](attachments/2026-05-26%20autenticacao%20web%202026-05-25%2008.28.13.excalidraw.md)

![](attachments/2026-05-26%20autenticacao%20web%202026-05-25%2008.28.13.excalidraw.svg)

# Fichamento da Aula — 25/05/2026

**Disciplina:** APS 2026.1  
**Tema geral:** Reuso, controle de estado em aplicações web, autenticação, escalabilidade e orientações para o projeto da disciplina

---

## 1. Abertura da aula e orientações iniciais

O professor iniciou a aula perguntando se os alunos conseguiram programar e executar o sistema desenvolvido nas aulas anteriores.

Ele chamou atenção para o fato de alguns alunos não terem mexido no código desde a aula anterior e reforçou que isso não deve acontecer, pois o conteúdo começará a acelerar.

Segundo o professor, as anotações das aulas já acumulam muitos pontos importantes. Mesmo conteúdos aparentemente pequenos podem se desdobrar em muito estudo.

### Mensagem central

- Não deixar o conteúdo acumular.
- Praticar programação entre uma aula e outra.
- Acompanhar o desenvolvimento do sistema aos poucos.
- Entender que o objetivo não é apenas obter nota, mas desenvolver formação profissional.

O professor destacou que a maioria da turma está realizando as atividades e propôs que a primeira avaliação fosse um projeto.

---

## 2. Organização das avaliações

O professor apresentou uma proposta de avaliação para a disciplina.

### Proposta discutida na aula

1. **Primeira avaliação:** primeira parte do projeto.
2. **Segunda avaliação:** continuidade do projeto, com possibilidade de aplicação de padrões de projeto.
3. **Terceira avaliação:** prova sobre padrões de projeto.

Inicialmente, o professor comentou que gostaria de fazer apenas duas avaliações. Depois, explicou que o projeto seria dividido em duas partes, correspondendo à primeira e à segunda nota, e que a terceira nota seria uma prova sobre padrões de projeto.

### Projeto como avaliação

O projeto poderá usar inteligência artificial, mas o professor alertou que isso não dispensa a compreensão do que está sendo feito.

A ideia não é simplesmente gerar código com IA e entregar sem entender. O professor deixou claro que isso pode até gerar uma nota, mas não contribui para a formação profissional.

### Uso de IA

O professor permitiu explicitamente o uso de IA no projeto. No entanto, destacou que:

- o aluno precisa entender o sistema gerado;
- a IA pode ser usada como ferramenta de apoio;
- usar IA sem maturidade pode levar a soluções frágeis;
- a avaliação levará em conta a estrutura e a qualidade do projeto;
- o professor poderá usar IA para auxiliar na correção dos projetos.

---

## 3. O objetivo do conteúdo de desenvolvimento web na disciplina

O professor explicou que, embora a turma esteja trabalhando com desenvolvimento web, o foco principal da disciplina não é ensinar detalhes específicos de Javalin, Thymeleaf, HTML ou CSS.

O objetivo é entender a arquitetura de sistemas em um ambiente muito utilizado profissionalmente: o ambiente web.

### O que realmente importa

O professor destacou que a preocupação principal é que os alunos aprendam a desenvolver sistemas:

- modulares;
- reutilizáveis;
- organizados;
- mais fáceis de manter;
- adequados para evolução futura.

Segundo ele, a capacidade de desenvolver software reutilizável será um diferencial importante no mercado, inclusive no contexto de uso de inteligência artificial.

---

## 4. Reuso de código e componentização

Um dos temas centrais da aula foi o reuso de código.

O professor explicou que, quando um sistema começa a crescer, a IA pode perder o controle da estrutura do projeto e começar a gerar código repetido. Isso também acontece com desenvolvedores humanos.

### Exemplo de um sistema com vários módulos

O professor apresentou um exemplo de um sistema que já possuía quatro módulos:

- um módulo de OKRs;
- um módulo de gestão de incidentes;
- um módulo de help desk;
- um módulo de processos.

Para uma empresa específica, apenas dois módulos estavam ativos. O sistema possuía um menu lateral e uma barra de navegação superior com elementos como:

- nome da empresa;
- nome do sistema;
- módulos disponíveis;
- notificações;
- menu de usuário;
- seletor de tema claro/escuro;
- opção de feedback.

Ao criar um novo módulo, a IA não reutilizou corretamente a barra de navegação. O professor percebeu que havia código repetido entre os módulos.

### Problema identificado

A IA havia implementado uma nova barra de navegação em vez de reutilizar a barra principal já existente.

Isso gerou inconsistência visual e funcional, pois alguns elementos não apareciam corretamente no novo módulo.

### Solução esperada

A solução correta seria criar uma barra de navegação genérica e parametrizável, reutilizada pelos diferentes módulos.

A ideia é identificar o que existe em comum entre as telas e transformar isso em um componente reutilizável.

---

## 5. Evitar cópia e cola

O professor enfatizou que os alunos devem desenvolver o hábito de evitar código duplicado.

Quando algo aparece repetido em mais de um lugar, é preciso perguntar:

- O que essas partes têm em comum?
- O que muda entre elas?
- Como posso generalizar esse comportamento?
- Como posso transformar isso em componente, método, classe ou template reutilizável?

### Exemplo de listagens

Se o sistema possui várias listagens de tabelas, essas listagens devem seguir um padrão comum e, sempre que possível, ser implementadas de forma reutilizável.

Isso ajuda a manter:

- consistência visual;
- padronização de comportamento;
- facilidade de manutenção;
- menor quantidade de erros;
- evolução mais rápida do sistema.

---

## 6. Exemplo de um aluno em uma empresa

O professor contou a história de um aluno que trabalhou em uma equipe de uma empresa.

Esse aluno percebeu que havia componentes de front-end repetidos nos projetos e, durante um fim de semana, recriou componentes reutilizáveis, como listagens e elementos comuns da interface.

### Aspecto positivo

O professor elogiou a iniciativa do aluno, pois ele teve a visão de componentizar e melhorar a estrutura do sistema.

### Problema ocorrido

O aluno fez essa alteração sem combinar previamente com a equipe.

Na época, havia várias pessoas trabalhando em branches diferentes. Como o aluno mexeu na base comum do front-end, isso poderia gerar muitos conflitos de merge.

### Solução posterior

A equipe precisou organizar um momento de congelamento do código, no qual todos fizeram commit e sincronizaram o trabalho. Depois disso, o aluno refez parte do trabalho de forma coordenada com a equipe.

### Lição do exemplo

A componentização é importante, mas precisa ser feita com maturidade e coordenação em equipe.

A atitude do aluno demonstrou um mindset de reutilização e melhoria de código, e isso contribuiu para que ele se destacasse profissionalmente.

---

## 7. Reuso como diferencial competitivo

O professor afirmou que o comportamento comum no mercado é copiar e colar código parecido, fazer pequenas alterações e entregar.

No entanto, desenvolver a capacidade de perceber repetições e criar componentes reutilizáveis é um diferencial competitivo.

### Por que dá mais trabalho?

Criar algo reutilizável costuma dar mais trabalho na primeira vez, porque exige:

- análise do que é comum;
- identificação do que varia;
- desenho de uma solução genérica;
- organização do código;
- cuidado com a manutenção.

Porém, depois de criado, o componente acelera o desenvolvimento futuro.

---

## 8. Exemplo de CSS e padronização visual

O professor também apresentou um exemplo envolvendo CSS e identidade visual.

Ele relatou uma situação em que um sistema precisava ter cores e marca ajustadas para uma apresentação a um cliente. A alteração parecia simples, mas deu muito trabalho porque os estilos estavam copiados em vários lugares.

### Problema

As cores, botões e estilos não estavam centralizados nem reutilizáveis.

Assim, para mudar a identidade visual, era necessário alterar várias telas manualmente.

### Lição

O sistema deve ter estilos padronizados e parametrizados.

O professor sugeriu que, ao implementar um sistema, especialmente com IA, os alunos já definam pelo menos três cores básicas:

- cor principal;
- cor de background;
- cor de destaque.

Com isso, se um botão não segue a cor padrão, fica mais fácil perceber que o CSS está inconsistente.

---

## 9. Reuso no front-end com Thymeleaf

O professor comentou que, no sistema de exemplo com Javalin e Thymeleaf, já existe um mecanismo de reuso no front-end.

Esse mecanismo envolve o conceito de template.

### Orientação do professor

Os alunos devem estudar na documentação do Thymeleaf os temas de:

- reuso;
- componentização;
- templates;
- reaproveitamento de partes comuns da interface.

O professor afirmou que essa será uma das coisas avaliadas no sistema.

### Critério de avaliação destacado

Se houver duas listagens feitas com cópia e cola, isso será considerado um problema.

O professor afirmou que quer “ligar o botão do reuso no máximo” neste momento da disciplina, para que os alunos exercitem esse modo de pensar.

---

## 10. Controle de estado em aplicações web

Após a discussão sobre reuso, o professor introduziu o tema principal da aula: **controle de estado em aplicações web**.

### O que é estado?

Estado é uma informação mantida pelo sistema sobre uma determinada situação.

Exemplos:

- um usuário fez login;
- uma cesta de compras contém produtos;
- uma sessão está ativa;
- um formulário possui dados preenchidos;
- uma aplicação guarda preferências do usuário.

Quando um usuário faz login, o sistema passa a ter a informação de que aquele usuário está autenticado. Isso é um estado.

---

## 11. Aplicações stateful e stateless

O professor explicou dois conceitos importantes.

### Aplicação stateful

Uma aplicação **stateful** guarda estado.

Exemplo: o servidor mantém na memória a informação de que um usuário está logado.

Nesse caso, se outros usuários também fizerem login, o servidor precisará guardar informações de cada um deles.

### Aplicação stateless

Uma aplicação **stateless** não guarda estado entre as requisições.

O servidor processa uma requisição, envia a resposta e depois esquece aquela interação.

### Observação conceitual

Uma aplicação que usa sessão armazenada no servidor, como no exemplo com `JSESSIONID` e `sessionAttribute`, continua sendo **stateful no servidor**.

Nesse caso:

- o navegador guarda apenas o identificador da sessão;
- os dados da sessão ficam no servidor;
- o servidor precisa manter uma estrutura para recuperar os dados associados àquele identificador.

---

## 12. Estado e consumo de recursos

Guardar estado consome recursos do servidor.

O professor explicou isso usando o exemplo de usuários logados.

Quando um usuário faz login, o sistema pode buscar suas informações no banco de dados e armazenar algo em memória, como:

- identificador do usuário;
- nome;
- e-mail;
- outros dados da sessão.

Se vários usuários fizerem login, várias informações precisarão ser mantidas.

### Exemplo da cesta de compras

Em um comércio eletrônico, além do usuário logado, há também a cesta de compras.

Cada produto adicionado representa novo estado associado ao usuário.

Exemplo:

- o usuário está logado;
- o usuário adicionou um lápis;
- o usuário adicionou uma caneta;
- o usuário adicionou uma resma de papel.

Se milhares de usuários estiverem acessando o sistema simultaneamente, o servidor poderá precisar controlar milhares de estados.

---

## 13. Estado em termos de código

O professor relacionou o estado com objetos em memória.

Quando se cria um objeto em Java, por exemplo:

***java
Usuario usuario = new Usuario();
***

esse objeto passa a ocupar espaço na memória do servidor.

Da mesma forma, quando dados são consultados no banco e armazenados em uma lista, como um `ArrayList` ou `LinkedList`, essa lista também ocupa memória.

### Exemplo

Se para cada usuário o sistema consulta dados no banco e guarda esses dados em uma lista, o consumo de memória cresce conforme o número de usuários.

Em termos simples:

***text
memória consumida ≈ número de usuários × volume de dados carregados por usuário
***

---

## 14. Performance e escalabilidade

O professor explicou que escalabilidade é a capacidade de um sistema suportar mais usuários simultâneos mantendo uma qualidade aceitável.

### Diferença entre performance e escalabilidade

**Performance** está relacionada a quão rápido o sistema responde e a quão bem ele utiliza os recursos disponíveis.

**Escalabilidade** está relacionada à capacidade de manter uma performance aceitável quando aumenta a quantidade de usuários, requisições ou dados.

### Escala não é apenas “não cair”

Um sistema não é considerado escalável apenas porque ainda responde. Ele precisa responder dentro de um tempo aceitável.

### Tempo de resposta

Tempo de resposta é o intervalo entre a ação do usuário e a resposta do sistema.

Exemplo:

- o usuário clica em um botão;
- o sistema processa;
- a página ou resposta aparece.

O professor comentou que, em comércio eletrônico, tempos de resposta acima de poucos segundos já podem ser considerados ruins, pois o usuário tende a achar que o sistema travou.

### Relação entre usuários e tempo de resposta

À medida que o número de usuários aumenta, o tempo de resposta tende a aumentar.

Em determinado ponto, o sistema pode ficar tão lento que, na prática, deixa de ser utilizável. Em outro ponto, pode cair completamente.

### Capacidade do sistema

Se um sistema mantém bom tempo de resposta até 1000 usuários, mas degrada depois disso e cai com 2000, a capacidade considerada adequada é 1000 usuários, pois é até esse ponto que a qualidade é mantida.

---

## 15. Recursos computacionais relevantes

O professor destacou quatro recursos principais que influenciam a performance de um sistema:

1. Processamento.
2. Memória.
3. Disco.
4. Rede.

Dependendo da aplicação, um recurso pode ser mais exigido do que outro.

### Exemplo: jogos

Jogos costumam exigir bastante:

- memória;
- processamento;
- GPU;
- rede, quando há modo online.

O professor citou jogos digitais para explicar que jogos mantêm muitos estados simultâneos.

### Exemplo: upload de arquivos

Em um sistema em que vários usuários fazem upload de arquivos, os recursos mais usados podem ser:

- rede;
- disco;
- memória, dependendo da implementação;
- processamento, se o servidor precisar redimensionar imagens.

Se o usuário envia uma imagem grande e o servidor precisa reduzi-la, há consumo de memória e processamento para realizar essa operação.

---

## 16. Infraestrutura e performance

O professor explicou que a performance depende de uma relação adequada entre sistema e infraestrutura.

Não basta desenvolver o sistema sem considerar onde ele será executado.

### Exemplo do contrato com cliente

Se um cliente contrata um sistema e afirma que já possui um computador para executá-lo, o desenvolvedor precisa deixar claro qual capacidade aquele ambiente suporta.

Por exemplo:

- o sistema suporta até 1000 usuários simultâneos;
- com tempo de resposta de até 3 segundos;
- em uma determinada configuração de servidor.

Se isso não for definido, quando o sistema cair ou ficar lento, poderá haver conflito entre cliente e desenvolvedor.

---

## 17. Teste de performance

O professor explicou que a forma de descobrir a capacidade de um sistema é testando.

### Como funciona um teste de performance

Um programa dispara várias requisições contra o servidor, enquanto se observa o comportamento da aplicação.

No caso dos alunos, o professor sugeriu usar o sistema local rodando na porta 8080 ou similar e outro programa para enviar requisições.

### Ferramenta citada: JMeter

O professor citou o JMeter como uma ferramenta muito usada para testes de performance.

Com ele, é possível configurar:

- número de requisições;
- quantidade de usuários simulados;
- tempo de crescimento da carga;
- comportamento gradual ou abrupto das requisições.

### Teste abrupto x teste gradual

O professor explicou que há diferença entre:

- enviar muitas conexões de uma vez;
- aumentar gradualmente a carga em alguns minutos.

Dependendo da arquitetura, a aplicação pode suportar crescimento gradual, mas quebrar diante de um aumento repentino.

### Cuidados no teste local

O professor lembrou que, se o programa de teste e o servidor estiverem na mesma máquina, ambos competem pelos mesmos recursos.

Na vida real, o ideal é que a máquina que testa não seja a mesma máquina testada.

---

## 18. Monitoramento durante testes

O professor sugeriu que os alunos abram o gerenciador de tarefas ou monitor de atividade para observar o consumo de recursos.

Durante o teste, é possível acompanhar:

- uso de CPU;
- uso de memória;
- processos ativos;
- degradação do sistema;
- travamentos.

### Swap

O professor explicou que, quando a memória RAM enche, o sistema operacional pode começar a usar o disco como memória, processo conhecido como swap.

Quando isso acontece, a performance tende a cair bastante.

---

## 19. Exemplo de uma empresa e alto volume de transações

O professor citou uma empresa como exemplo de sistema de alta escala.

Segundo ele, essa empresa processa mais de 700 mil transações por segundo.

Ele relatou uma situação em que a empresa precisava atender a um cliente internacional de grande porte. O sistema precisava suportar cerca de 600 mil transações por segundo.

Após meses de ajustes, testes e otimizações, a equipe conseguiu atingir mais de 600 mil transações por segundo na apresentação.

### Lição do exemplo

O professor destacou que esse tipo de resultado depende fortemente de arquitetura de software.

---

## 20. Reduzir estado para ganhar escala

Depois de discutir performance e escalabilidade, o professor apresentou uma ideia central:

> Para conseguir mais escala, é importante reduzir o estado mantido no servidor.

Se o servidor precisa guardar muita informação de cada usuário, o consumo de recursos cresce.

Se parte desse estado pode ser armazenada no cliente, o servidor fica mais leve.

### Exemplo

Em vez de guardar no servidor a informação completa de que um usuário está logado, o sistema pode guardar alguma identificação no navegador do usuário.

Assim, quando o usuário faz nova requisição, o navegador envia essa identificação, e o servidor pode reconhecer o usuário sem manter todo o estado na memória.

### Ressalva importante

Guardar parte do estado no cliente pode reduzir o uso de memória no servidor e favorecer a escalabilidade. Porém, essa estratégia exige cuidado, pois dados no navegador podem ser visualizados, copiados ou manipulados.

Por isso:

- informações sensíveis não devem ser armazenadas diretamente no cliente;
- o servidor deve validar as informações recebidas;
- tokens precisam ter prazo de expiração;
- cookies e tokens devem ser protegidos;
- é necessário considerar riscos como roubo de token e manipulação de dados.

---

## 21. Cliente e servidor na arquitetura web

O professor retomou a arquitetura cliente-servidor.

### Cliente

No contexto web, o cliente é o navegador.

### Servidor

O servidor é a aplicação web que processa requisições e retorna respostas.

### Estado no cliente

Guardar estado no cliente pode aumentar a escala da aplicação, pois reduz a necessidade de o servidor manter informações de cada usuário.

Porém, isso não elimina a responsabilidade do servidor de validar dados, controlar acesso e proteger informações sensíveis.

---

## 22. Cuidado para não exagerar na preocupação com escala

O professor alertou que os alunos não devem ficar paranoicos com escalabilidade.

Segundo ele, muitos sistemas não possuem volume de usuários suficiente para que esse seja o maior problema.

### Exemplo de sistema de gestão de conteúdo

O professor citou um sistema popular de gestão de páginas e blogs como uma aplicação muito usada que mantém bastante estado no servidor e, mesmo assim, atende a muitos contextos de uso.

Para a maioria das situações, o volume de usuários não chega a consumir tantos recursos a ponto de degradar a performance.

---

## 23. CDN e diagnóstico incorreto de performance

O professor explicou o conceito de CDN e contou um caso em que uma solução de CDN foi sugerida sem necessidade.

### O que é CDN?

CDN significa **Content Distribution Network**, ou rede de distribuição de conteúdo.

É uma rede de servidores distribuídos que armazenam e entregam conteúdo aos usuários.

### Relação com DNS

O professor também relembrou o conceito de DNS.

DNS é o serviço que associa nomes de domínio a endereços IP.

Exemplo hipotético:

***text
exemplo.br -> 200.42.7.32
***

Com uma CDN, o conteúdo pode ser distribuído por vários servidores, e as requisições podem ser direcionadas para servidores diferentes.

### Quando CDN faz sentido

CDNs são úteis em sistemas com muitos acessos e muito conteúdo estático, como:

- imagens;
- arquivos JavaScript;
- arquivos CSS;
- vídeos;
- páginas estáticas;
- conteúdo acessado por usuários geograficamente distribuídos.

O professor citou sistemas de e-commerce e serviços de streaming como exemplos de uso.

### O que uma CDN não resolve sozinha

Uma CDN não resolve automaticamente qualquer problema de lentidão.

Ela pode não resolver problemas como:

- consulta lenta ao banco de dados;
- código mal implementado;
- servidor subdimensionado;
- backend com excesso de processamento;
- página pesada por má construção;
- falta de otimização da aplicação.

### Caso citado

Uma empresa tinha uma página web lenta, e um técnico sugeriu colocar uma CDN, alegando excesso de acessos.

Porém, a página tinha algo em torno de 100 acessos por dia, o que não justificava a solução.

O problema provavelmente não era escala, e a CDN apenas geraria custo adicional sem resolver a causa real.

---

## 24. HTTP como protocolo stateless

Depois do intervalo, o professor explicou que o HTTP foi criado para funcionar de forma stateless.

### Funcionamento básico

1. O cliente envia uma requisição.
2. O servidor processa a requisição.
3. O servidor envia uma resposta.
4. O servidor esquece aquela interação.

Quando o cliente envia uma nova requisição, o servidor não sabe automaticamente que aquele mesmo cliente já passou por ali antes.

### Problema em sistemas reais

Em sistemas reais, é necessário manter estado.

Exemplo: se uma pessoa fez login, o sistema precisa saber que ela está autenticada para permitir acesso às páginas privadas.

---

## 25. Cookies

O professor apresentou os cookies como a forma mais básica e primitiva de manter estado no contexto web.

### O que é um cookie?

Um cookie é uma informação no formato chave-valor armazenada no navegador.

Exemplo conceitual:

***text
usuario = usuario123
***

Os cookies são armazenados por domínio.

Ou seja, o navegador associa cookies aos domínios dos sites acessados.

### Atributos importantes de cookies

Além de nome e valor, cookies podem ter atributos que controlam comportamento, duração e segurança.

Alguns atributos importantes são:

- `Max-Age` ou `Expires`: define por quanto tempo o cookie será mantido.
- `Domain`: define para qual domínio o cookie será enviado.
- `Path`: define para quais caminhos do domínio o cookie será enviado.
- `HttpOnly`: impede que o cookie seja acessado por JavaScript.
- `Secure`: faz com que o cookie seja enviado apenas por HTTPS.
- `SameSite`: ajuda a controlar o envio do cookie em requisições originadas de outros sites.

Esses atributos são importantes especialmente em cookies usados para autenticação.

---

## 26. Requisição HTTP: cabeçalho e corpo

O professor explicou que uma requisição HTTP possui, de forma simplificada, duas partes:

1. Cabeçalho.
2. Corpo.

### Cabeçalho

Contém informações de controle da requisição, como cookies e outros metadados.

### Corpo

Contém o conteúdo enviado, por exemplo:

- login;
- senha;
- dados de formulário;
- informações enviadas por POST.

---

## 27. Exemplo de login usando cookie

O professor explicou um fluxo simples de login usando cookie.

### Fluxo conceitual

1. O usuário acessa a página de login.
2. O usuário envia login e senha por POST.
3. O servidor verifica se os dados são válidos.
4. Se forem válidos, o servidor envia uma resposta com um cookie.
5. O navegador armazena o cookie.
6. Nas próximas requisições para o mesmo domínio, o navegador envia o cookie automaticamente.
7. O servidor lê o cookie e identifica que o usuário já passou pelo login.

### Logout

Para deslogar o usuário, o sistema pode apagar o cookie.

Depois disso, nas próximas requisições, o navegador não enviará mais aquela informação, e o servidor interpretará o usuário como não autenticado.

---

## 28. Segurança em cookies

O professor alertou que não se deve guardar informações sensíveis diretamente no navegador.

Tudo que está no navegador pode ser inspecionado pelo usuário por meio das ferramentas de desenvolvedor.

### Exemplo mostrado

O professor abriu a aba **Application** do navegador, onde é possível visualizar:

- cookies;
- local storage;
- session storage;
- outros dados mantidos pelo navegador.

### Recomendação apresentada

O professor afirmou que, ao guardar informações em cookies, deve-se evitar dados sensíveis e usar informações protegidas, como tokens ou valores criptografados.

### Ajuste conceitual importante

Em autenticação, não se deve guardar informações sensíveis diretamente no cookie, como senha, dados pessoais ou permissões sem proteção.

Uma prática mais adequada é armazenar no cookie apenas um identificador de sessão ou um token protegido, com configurações de segurança apropriadas.

Exemplo de atributos úteis para um cookie de autenticação:

***text
HttpOnly
Secure
SameSite
Max-Age
***

---

## 29. Rastreamento por cookies

O professor explicou que cookies também são usados para rastreamento.

Ao acessar um site, o navegador pode fazer requisições para vários domínios, não apenas para o domínio principal.

### Exemplo

Ao acessar uma página de notícias, a página pode carregar recursos de:

- domínio principal do site;
- serviços de vídeo;
- serviços de publicidade;
- ferramentas de rastreamento;
- outros serviços externos.

Cada serviço pode armazenar cookies próprios.

### Exemplo de identificação

Um serviço de publicidade pode atribuir ao usuário um identificador, como:

***text
usuario = 4223
***

Depois, ao navegar por outros sites que usam o mesmo serviço de publicidade, o navegador envia esse cookie, e o serviço consegue reconhecer que aquele mesmo usuário esteve em outros lugares.

### Associação futura com identidade real

Inicialmente, o serviço pode conhecer apenas o identificador. Mas, quando o usuário faz login em algum serviço, esse identificador pode ser associado a uma pessoa real.

O professor explicou que isso permite construir um perfil de interesses do usuário.

---

## 30. Privacidade, navegadores e compartilhamento de dados

O professor comentou que navegadores com maior foco em privacidade podem bloquear requisições para domínios diferentes do site acessado.

Também comentou que empresas podem trocar informações entre si, o que reduz o efeito de bloquear apenas parte do rastreamento.

### Exemplo sobre grandes empresas de tecnologia

O professor relatou que, ao acessar configurações de privacidade, já encontrou informações compartilhadas por vários aplicativos e serviços com uma grande empresa de tecnologia.

Ele mencionou exemplos como:

- aplicativos de banco;
- sites de comércio eletrônico;
- aplicativos e serviços diversos.

### Documentário citado

O professor recomendou o documentário **O Dilema das Redes** para entender melhor algoritmos e redes sociais.

---

## 31. Local storage e session storage

Além de cookies, o professor apresentou outras formas de armazenar estado no navegador.

### Local storage

O **local storage** é uma área de armazenamento no navegador que guarda dados em chave-valor.

Esses dados podem permanecer mesmo depois de fechar o navegador.

### Session storage

O **session storage** também armazena dados em chave-valor, mas apenas enquanto a sessão da aba ou do navegador estiver ativa.

Quando o usuário fecha a aba ou encerra a navegação, os dados podem ser perdidos.

### Possível uso

O session storage pode ser usado quando se deseja que o login funcione apenas enquanto o navegador estiver aberto.

### Acesso via JavaScript

O professor explicou que local storage e session storage são acessados via JavaScript.

### Observação de segurança

Como local storage e session storage podem ser acessados por JavaScript, é preciso cuidado ao armazenar tokens ou informações sensíveis nesses mecanismos.

Em caso de falhas de segurança no front-end, scripts maliciosos poderiam tentar acessar esses dados.

---

## 32. Session no servidor com Javalin

O professor demonstrou como o Javalin pode manter informações de sessão no servidor.

Ele explicou que, por baixo dos panos, o servidor cria uma estrutura semelhante a um mapa, ou `HashMap`, armazenando chaves e valores.

### JSESSIONID

O Javalin cria um cookie chamado `JSESSIONID`.

Esse cookie contém um identificador, geralmente um hash, que fica no navegador.

No servidor, esse identificador é usado para localizar os dados da sessão.

### Onde ficam os dados?

- No navegador: fica apenas o identificador da sessão.
- No servidor: ficam os dados associados à sessão, como o usuário logado.

### Consequência arquitetural

Essa abordagem mantém estado no servidor. Portanto, ela é stateful.

Isso facilita a implementação inicial de autenticação, mas exige que o servidor mantenha sessões ativas em memória ou em algum mecanismo de armazenamento de sessão.

---

## 33. Context no Javalin

O professor retomou o uso do objeto `Context`, ou `ctx`, do Javalin.

O `ctx` funciona como uma “casquinha” que encapsula informações da requisição e da resposta HTTP.

Com ele, é possível acessar ou manipular informações como:

- parâmetros da requisição;
- cookies;
- sessão;
- redirecionamentos;
- respostas.

### Criando um cookie simples

O professor mostrou que é possível criar um cookie com:

***java
ctx.cookie("email", usuario.getEmail());
***

Ele alertou que guardar o e-mail diretamente no navegador não é seguro.

### Usando atributo de sessão

Depois, o professor mostrou o uso de `sessionAttribute`:

***java
ctx.sessionAttribute("usuarioId", usuario.getId());
***

Nesse caso, a informação fica associada à sessão no servidor, enquanto o navegador guarda apenas o `JSESSIONID`.

### Diferença entre `ctx.attribute` e `ctx.sessionAttribute`

Uma diferença importante é:

- `ctx.attribute`: armazena dados apenas durante a requisição atual.
- `ctx.sessionAttribute`: armazena dados associados à sessão do usuário, podendo ser recuperados em requisições futuras.

Assim, para guardar a informação de que um usuário está logado entre diferentes páginas, faz sentido usar `sessionAttribute`, e não apenas `attribute`.

---

## 34. Verificação de usuário logado

O professor mostrou a lógica para impedir acesso a páginas privadas quando não houver usuário logado.

### Exemplo conceitual

***java
if (ctx.sessionAttribute("usuarioId") == null) {
    ctx.redirect("/login");
    return;
}
***

### Interpretação

- Se `usuarioId` estiver nulo, o usuário não está logado.
- O sistema redireciona para `/login`.
- Se `usuarioId` existir, o acesso é permitido.

### Demonstração

O professor mostrou que, ao apagar o cookie `JSESSIONID` no navegador e atualizar a página, o sistema redireciona para a página de login.

Isso acontece porque o navegador deixa de enviar o identificador da sessão, e o servidor não consegue recuperar o usuário logado.

---

## 35. Fluxo visual de sessão com `JSESSIONID`

O fluxo demonstrado pelo professor pode ser representado da seguinte forma:

***mermaid
sequenceDiagram
    participant Navegador
    participant Servidor

    Navegador->>Servidor: POST /login com e-mail e senha
    Servidor->>Servidor: valida usuário e senha
    Servidor-->>Navegador: resposta com cookie JSESSIONID
    Navegador->>Servidor: GET /usuarios com JSESSIONID
    Servidor->>Servidor: recupera sessão pelo JSESSIONID
    Servidor-->>Navegador: página protegida
***

Esse fluxo mostra que o navegador guarda o identificador da sessão, enquanto o servidor mantém os dados associados a essa sessão.

---

## 36. Duração de cookies

O professor mostrou que cookies podem ter tempo de duração configurado.

### Exemplo

***java
ctx.cookie("email", usuario.getEmail(), 60 * 60 * 24 * 30);
***

Nesse exemplo, o cookie poderia persistir por aproximadamente 30 dias.

### Uso típico

Esse tipo de configuração é usado em funcionalidades como:

- “lembrar de mim”;
- não pedir login novamente neste computador;
- manter preferências do usuário;
- preencher automaticamente parte dos dados de login.

O professor alertou que não é adequado guardar senha no navegador.

---

## 37. Senhas, BCrypt e hash

Durante a demonstração, o professor mencionou o uso de BCrypt no contexto de validação de senha.

### Ajuste conceitual importante

Conceitualmente, senhas não devem ser criptografadas para depois serem descriptografadas.

O mais adequado é armazenar um **hash seguro** da senha, usando algoritmos próprios para esse fim, como BCrypt.

No login, o sistema:

1. recebe a senha digitada;
2. compara essa senha com o hash armazenado;
3. decide se a autenticação é válida.

Exemplo conceitual:

***java
BCrypt.checkpw(senhaDigitada, hashArmazenado);
***

### Diferença importante

- **Criptografia:** normalmente permite reverter a informação original se houver uma chave.
- **Hash de senha:** não deve permitir recuperar a senha original; serve para comparar de forma segura.

---

## 38. Autenticação básica e JWT

O professor afirmou que a forma demonstrada em aula é uma forma básica de autenticação.

Depois, os alunos deverão aprender e usar JWT.

### O que é JWT?

JWT é um formato de token usado para representar informações assinadas, frequentemente usado em autenticação.

Ele não é exatamente um “tipo de cookie”. Um JWT pode ser:

- armazenado em um cookie;
- armazenado em local storage;
- armazenado em session storage;
- enviado no cabeçalho HTTP.

Exemplo de envio em cabeçalho HTTP:

***http
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
***

### Ideia geral

Em uma autenticação baseada em token, o servidor gera um token após o login. Nas requisições seguintes, o cliente envia esse token para provar que já foi autenticado.

O servidor deve verificar se o token é válido antes de permitir o acesso.

---

## 39. Autenticação e autorização

A aula tratou principalmente de autenticação, isto é, verificar se o usuário fez login.

Em sistemas reais, também é necessário tratar autorização.

### Autenticação

Autenticação responde à pergunta:

> Quem é o usuário?

Exemplo:

- o usuário informou e-mail e senha;
- o sistema verificou os dados;
- o sistema reconheceu aquele usuário como autenticado.

### Autorização

Autorização responde à pergunta:

> O que esse usuário pode acessar ou fazer?

Exemplo:

- um usuário comum pode visualizar seus próprios dados;
- um administrador pode cadastrar, editar ou remover registros;
- um usuário não autorizado deve ser bloqueado ao tentar acessar páginas restritas.

### Relação com o projeto

No projeto da disciplina, a autenticação é requisito explícito. A autorização pode aparecer quando houver diferentes tipos de usuários, papéis ou permissões.

---

## 40. Evitar repetição na verificação de autenticação

O professor explicou que, no exemplo demonstrado, cada endpoint privado precisava verificar se a sessão estava ativa.

No entanto, repetir o mesmo `if` em todos os endpoints não é uma boa prática.

### Problema

Se todas as páginas privadas tiverem código repetido como:

***java
if (ctx.sessionAttribute("usuarioId") == null) {
    ctx.redirect("/login");
    return;
}
***

isso gera duplicação.

### Orientação

Os alunos devem encontrar uma forma de reutilizar essa verificação.

O professor mencionou que o próprio Javalin tem mecanismos mais eficientes, como filtros, mas pediu que os alunos não usem isso agora.

Neste momento, eles devem implementar a lógica de forma explícita, mas sem copiar e colar o mesmo código em todos os endpoints.

---

## 41. Próxima missão dos alunos

O professor definiu como próxima missão implementar autenticação nos sistemas.

### Regras gerais

- A página de login pode ser pública.
- As demais páginas devem exigir login.
- Ao fazer login, o sistema deve salvar alguma informação de sessão.
- Ao acessar endpoint privado, o sistema deve verificar se existe sessão ativa.
- Se não houver sessão, deve redirecionar para `/login`.

---

## 42. Projeto da disciplina

No final da aula, o professor detalhou melhor o projeto da disciplina.

### Tamanho das equipes

As equipes devem ter:

- 2 ou 3 pessoas.

O professor comentou que criará uma atividade em grupo no Classroom.

### Possibilidade de projetos conectados

O professor sugeriu que equipes diferentes podem trabalhar em partes diferentes de um projeto maior, desde que sejam bases de código separadas.

### Exemplo de divisão

Em um sistema de comércio eletrônico:

- uma equipe poderia fazer a parte administrativa, com usuários e cadastro de produtos;
- outra equipe poderia fazer a parte pública ou comercial, onde clientes acessam e listam produtos.

Essas partes poderiam se comunicar entre si usando REST.

---

## 43. Requisitos do projeto

O professor listou vários requisitos esperados no projeto.

### 43.1 Reuso e modularização

O sistema deve evitar código repetido.

Tudo que puder ser modularizado deve ser modularizado.

Exemplos:

- componentes de interface;
- listagens;
- verificações repetidas;
- estruturas comuns;
- templates;
- partes comuns do front-end.

### 43.2 Autenticação

O projeto deve ter autenticação.

O professor destacou que não quer vários `if/else` repetidos em todos os endpoints.

Os alunos devem encontrar uma forma de reaproveitar a lógica de autenticação.

### 43.3 Banco de dados

O projeto deve usar persistência com banco de dados.

O professor explicou que não ensinará banco de dados na disciplina, pois esse não é o foco, mas afirmou que o necessário será básico.

Os alunos precisarão estudar operações como:

- criar tabela;
- inserir;
- selecionar;
- atualizar;
- apagar.

### Observação conceitual

Para o projeto, o uso de banco de dados exigirá principalmente operações básicas de CRUD.

CRUD envolve:

- criar registros;
- consultar registros;
- atualizar registros;
- remover registros.

No entanto, banco de dados como área envolve outros temas além do CRUD, como:

- modelagem;
- relacionamentos;
- índices;
- transações;
- segurança;
- integridade dos dados.

### 43.4 JWT

O projeto deverá usar autenticação com JWT.

O professor afirmou que isso não é para ser feito imediatamente, mas até o final do projeto.

### 43.5 Arquitetura

O projeto deve usar uma arquitetura organizada com:

- controller;
- service;
- modelos.

### 43.6 Testes

O projeto deve ter testes.

O professor mencionou:

- testes unitários;
- testes de integração com endpoints.

Ele afirmou que mostrará posteriormente como fazer testes de integração.

### 43.7 GitHub

Todos devem usar GitHub.

O professor explicou que a atividade em grupo no Classroom permitirá criar ou selecionar grupos.

### 43.8 Execução local

O projeto não precisa ser publicado em domínio nem colocado em servidor.

Pode rodar localmente nos computadores dos alunos, em `localhost`.

### 43.9 Plus: serviço externo ou conexão entre projetos

O uso de algum serviço externo ou a conexão entre projetos será considerado um plus.

Não é requisito obrigatório, mas será positivo.

Exemplo: duas equipes desenvolvendo módulos diferentes que se comunicam via REST.

---

## 44. REST como possibilidade de integração

O professor mencionou REST como forma de comunicação entre projetos.

No exemplo do comércio eletrônico, a parte administrativa e a parte pública poderiam trocar informações via REST.

### Observação do professor

Não é obrigatório usar REST no projeto.

Quem fizer um sistema monolítico não perderá ponto por isso, mas quem fizer integração terá uma experiência positiva e poderá ganhar destaque.

### Exemplo concreto

Em uma integração REST entre dois módulos, uma equipe poderia expor endpoints de produtos, e outra equipe poderia consumir esses endpoints para montar uma vitrine.

Exemplos:

***http
GET /produtos
***

Retorna a lista de produtos.

***http
GET /produtos/10
***

Retorna o produto de ID 10.

***http
POST /produtos
***

Cria um novo produto.

***http
PUT /produtos/10
***

Atualiza o produto de ID 10.

***http
DELETE /produtos/10
***

Remove o produto de ID 10.

### Relação com o projeto

Se uma equipe fizer a parte administrativa e outra fizer a parte pública, a equipe da parte pública poderia consultar produtos cadastrados pela equipe administrativa por meio de endpoints REST.

---

## 45. Apresentações e acompanhamento do projeto

Para verificar se os alunos realmente estão entendendo o que estão fazendo, o professor sugeriu realizar reuniões ou apresentações periódicas.

A ideia é definir metas intermediárias e pedir que os alunos apresentem o que implementaram.

Cada integrante deverá mostrar e explicar sua parte.

---

## 46. IA, programação e papel profissional

O professor comentou que a IA muda a relação dos alunos com a codificação.

Segundo ele, no futuro próximo, o mercado poderá valorizar menos a codificação manual e mais a capacidade de desenvolver software com IA.

### Competências destacadas

Mesmo usando IA, o profissional precisa entender:

- requisitos;
- estrutura do sistema;
- arquitetura;
- autenticação;
- organização em controllers e services;
- design;
- padrões de projeto;
- decisões técnicas.

O professor afirmou que a etapa de codificação pode ser acelerada pela IA, mas a compreensão estrutural continua sendo essencial.

---

## 47. Projeto dividido em duas partes

O professor explicou que o projeto será levado até o fim da disciplina, mas dividido em duas partes.

### Primeira parte

A primeira parte será a parte básica do sistema, sem foco em padrões de projeto.

Apesar de chamada de básica, o professor disse que o nível de exigência será elevado.

### Segunda parte

A segunda parte envolverá a aplicação de padrões de projeto no sistema.

### Terceira nota

A terceira nota será uma prova sobre padrões de projeto.

O professor afirmou que a prova será tranquila para quem fizer as atividades e acompanhar a disciplina.

---

# 1. Orientações do Professor

- Não deixar o conteúdo acumular.
- Mexer no código entre uma aula e outra.
- Prestar atenção durante as explicações e evitar distrações com celular ou computador.
- Usar IA é permitido no projeto.
- Não usar IA sem entender o que está sendo feito.
- Entender que a disciplina é parte da formação profissional, não apenas uma questão de nota.
- Estudar reuso e componentização na documentação do Thymeleaf.
- Evitar código duplicado.
- Criar componentes reutilizáveis sempre que possível.
- Implementar autenticação nos sistemas.
- Verificar sessão ativa nos endpoints privados.
- Não repetir o mesmo código de autenticação em todos os endpoints.
- Fazer testes de performance como experiência prática.
- Experimentar o JMeter para disparar requisições contra o sistema.
- Usar o gerenciador de tarefas ou monitor de atividade para acompanhar CPU e memória durante testes.
- Estudar banco de dados básico para o projeto.
- Usar banco de dados no projeto.
- Usar JWT no projeto.
- Usar arquitetura com controller, service e modelos.
- Criar testes unitários.
- Criar testes de integração com endpoints.
- Usar GitHub.
- Rodar o projeto localmente; não é necessário publicar em domínio.
- Formar equipes de 2 ou 3 pessoas.
- Apresentar o andamento do projeto em reuniões ou checkpoints.
- Não se escorar nos colegas.
- Aproveitar a disciplina para desenvolver maturidade profissional.
- Não ter medo da prova ou da nota, mas sim de terminar a disciplina sem estudar, acompanhar ou aproveitar o conteúdo.

---

# 2. Conceitos para se Aprofundar

- Reuso de código.
- Componentização.
- Código duplicado.
- Templates no Thymeleaf.
- Modularização.
- Arquitetura web.
- Cliente e servidor.
- HTTP stateless.
- Aplicações stateful.
- Aplicações stateless.
- Controle de estado.
- Sessão de usuário.
- Cookies.
- Atributos de cookies.
- `HttpOnly`.
- `Secure`.
- `SameSite`.
- Cabeçalho HTTP.
- Corpo da requisição HTTP.
- Local storage.
- Session storage.
- JSESSIONID.
- `ctx` no Javalin.
- `ctx.cookie`.
- `ctx.attribute`.
- `ctx.sessionAttribute`.
- Redirecionamento para login.
- Autenticação.
- Autorização.
- JWT.
- Token.
- Hash de senha.
- BCrypt.
- Escalabilidade.
- Performance.
- Tempo de resposta.
- Teste de performance.
- JMeter.
- CPU.
- Memória.
- Disco.
- Rede.
- Swap.
- CDN.
- DNS.
- REST.
- CRUD.
- Banco de dados.
- SQL básico.
- Controllers.
- Services.
- Modelos.
- Testes unitários.
- Testes de integração.
- GitHub.
- Padrões de projeto.

---

# 3. Questões para Revisão

1. Por que o professor afirmou que o foco do conteúdo de desenvolvimento web não é apenas aprender Javalin, Thymeleaf, HTML ou CSS?
2. O que significa desenvolver um sistema modular e reutilizável?
3. Qual problema ocorreu no exemplo do novo módulo criado com auxílio de IA?
4. Por que copiar e colar código entre telas ou módulos pode gerar problemas futuros?
5. O que significa componentizar uma interface?
6. Qual foi a principal lição do exemplo de um aluno que criou componentes reutilizáveis em uma empresa?
7. Por que mudanças simples de cor e marca podem se tornar difíceis em sistemas mal estruturados?
8. Quais cores básicas o professor sugeriu parametrizar no front-end?
9. O que é estado em uma aplicação web?
10. Qual é a diferença entre uma aplicação stateful e uma aplicação stateless?
11. Por que uma aplicação com `JSESSIONID` e `sessionAttribute` ainda mantém estado no servidor?
12. Por que guardar estado no servidor consome recursos?
13. Como uma cesta de compras exemplifica controle de estado?
14. O que é performance?
15. O que é escalabilidade?
16. Qual é a diferença entre performance e escalabilidade?
17. Por que a capacidade de um sistema não deve ser medida apenas pelo ponto em que ele cai?
18. O que é tempo de resposta?
19. Quais são os quatro recursos computacionais destacados pelo professor?
20. Por que upload de imagem pode consumir rede, disco, memória e processamento?
21. Como um teste de performance ajuda a descobrir a capacidade de um sistema?
22. Qual ferramenta o professor citou para testes de performance?
23. Por que testar o servidor e gerar carga na mesma máquina pode distorcer o resultado?
24. O que é swap e por que ele prejudica a performance?
25. Por que reduzir estado no servidor pode ajudar a aumentar a escala?
26. Quais cuidados devem ser tomados ao guardar estado no cliente?
27. Qual é o papel do cliente e do servidor em uma arquitetura web?
28. Por que o HTTP é considerado stateless?
29. O que é um cookie?
30. Quais atributos de segurança podem ser usados em cookies?
31. Como um cookie pode ser usado para manter o usuário autenticado?
32. Por que não se deve guardar informações sensíveis diretamente no navegador?
33. O que acontece quando o cookie `JSESSIONID` é apagado?
34. Qual é a diferença entre local storage e session storage?
35. Para que serve o `ctx` no Javalin?
36. Qual é a diferença entre `ctx.attribute` e `ctx.sessionAttribute`?
37. Qual é a diferença entre `ctx.cookie` e `ctx.sessionAttribute` no exemplo da aula?
38. Por que senhas devem ser armazenadas com hash, e não criptografadas para descriptografia posterior?
39. Qual é o papel do BCrypt?
40. O que é JWT?
41. Por que JWT não deve ser entendido simplesmente como um cookie?
42. Qual é a diferença entre autenticação e autorização?
43. Por que o professor pediu para evitar repetir o mesmo código de verificação de login em todos os endpoints?
44. Quais são os principais requisitos do projeto da disciplina?
45. Por que o projeto deve usar banco de dados?
46. Quais operações básicas de banco de dados serão necessárias no projeto?
47. Qual é o papel dos testes unitários no projeto?
48. Qual é o papel dos testes de integração com endpoints?
49. Como duas equipes poderiam se comunicar em um projeto maior usando REST?
50. Dê exemplos de endpoints REST para um recurso de produtos.
51. Por que CDN não resolve qualquer problema de lentidão?
52. Segundo o professor, qual deve ser o papel do aluno/profissional em um contexto de desenvolvimento com IA?
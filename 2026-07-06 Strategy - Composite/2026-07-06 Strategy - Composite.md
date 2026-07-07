
[2026-07-06 Strategy - Composite 2026-07-06 08.38.48.excalidraw](attachments/2026-07-06%20Strategy%20-%20Composite%202026-07-06%2008.38.48.excalidraw.md)

[Seção ampliada — Strategy](Seção%20ampliada%20—%20Strategy.md)
# Fichamento — Aula APS 2026.1: Strategy e Composite

## 1. Orientações específicas sobre o projeto, requisitos e atividades

### Requisitos da primeira entrega do projeto

Foi reforçado que os projetos da disciplina devem atender aos requisitos definidos anteriormente para a primeira entrega:

- Uso de **Docker**.
- Front-end usando **Thymeleaf** com **Bootstrap**.
- Back-end usando **Javalin**.
- Banco de dados **PostgreSQL**.
- Projeto em **produção**.
- Uso de **log**.
- Presença de **testes automatizados**.
- Implementação de **autenticação**.
- Implementação de **autorização**.
- Organização modular do código.

### Script de avaliação e feedback

Foi informado que será executado um **script de avaliação** nos projetos da turma.

Esse script irá verificar automaticamente se os projetos estão atendendo aos requisitos solicitados. O resultado será gerado na raiz de cada projeto em um arquivo de texto no formato **Markdown**, contendo o feedback da avaliação.

Caso algum feedback esteja incorreto, os alunos devem entrar em contato com o professor e explicar o problema. O professor analisará o projeto especificamente. Foi reforçado que a avaliação só será considerada fechada quando professor e grupo estiverem de acordo sobre o resultado.

### Atividades sobre Strategy e Composite

A aula introduziu dois padrões de projeto:

- **Strategy**
- **Composite**

Serão disponibilizadas duas atividades, uma sobre cada padrão.

Essas atividades não serão obrigatórias para nota, mas foram recomendadas como prática importante para aprendizagem. A orientação foi que os alunos façam as atividades em casa para consolidar o entendimento.

### Aplicação dos padrões no projeto da disciplina

Os alunos foram orientados a pensar, com apoio de ferramentas de IA, em situações do próprio projeto nas quais poderiam aplicar os padrões **Strategy** e **Composite**.

A recomendação foi perguntar à IA algo como:

> Acabei de aprender o padrão Strategy. Este é um projeto de disciplina e eu quero aplicar o padrão Strategy neste projeto. Em que situações eu poderia usar o Strategy?

E também fazer uma pergunta semelhante para o padrão **Composite**.

Foi destacado que essa abordagem é pedagógica. Na prática profissional, o ideal é primeiro identificar uma necessidade real de projeto e só depois aplicar um padrão.

Caso a IA force demais a aplicação de um padrão, ou caso o grupo não encontre uma situação adequada, os alunos devem procurar o professor para discutir.

### Comunicação sobre problemas no projeto

Foi reforçado que os alunos devem enviar mensagem pelo **Discord** caso estejam com problemas no projeto, especialmente problemas relacionados ao servidor ou à implantação.

A orientação foi não esperar apenas pela aula para resolver essas pendências.

---

## 2. Introdução aos padrões de projeto

### O que são padrões de projeto

Padrões de projeto são **soluções reutilizáveis para problemas recorrentes de design de software**.

Na aula, o foco foi nos padrões aplicados à **orientação a objetos**, embora tenha sido esclarecido que nem todo padrão de projeto precisa necessariamente ser orientado a objetos.

A ideia central é que, ao longo do desenvolvimento de muitos sistemas, certos problemas aparecem repetidamente. Desenvolvedores experientes perceberam que esses problemas recorrentes podiam ser resolvidos com soluções semelhantes. Essas soluções passaram a ser organizadas como padrões.

### Padrão de projeto como ferramenta de design

Um padrão de projeto funciona como uma ferramenta de **design de software**.

Ele não deve ser visto como algo que se usa apenas porque é “bonito” ou “avançado”, mas como uma solução para um problema concreto de organização, manutenção, extensão ou desacoplamento do código.

Padrões de projeto geralmente ajudam a:

- melhorar a manutenibilidade;
- reduzir acoplamento;
- aumentar coesão;
- encapsular variações;
- organizar responsabilidades;
- facilitar extensões futuras;
- melhorar a comunicação entre desenvolvedores.

Apesar disso, padrões também podem aumentar a complexidade quando usados sem necessidade.

### Não é necessário decorar muitos padrões

Foi enfatizado que não é necessário saber vários padrões de projeto de cabeça.

A competência mais importante é saber que:

- existem bibliotecas e catálogos de padrões;
- problemas de projeto podem ter soluções conhecidas;
- é possível procurar um padrão quando se identifica um problema recorrente;
- o desenvolvedor deve entender o problema antes de aplicar a solução.

Na disciplina, os padrões serão usados principalmente para aprofundar o uso da orientação a objetos.

---

## 3. Uso pedagógico dos padrões na disciplina

A aplicação dos padrões no projeto da disciplina terá um caráter pedagógico.

Isso significa que, em alguns casos, a turma será incentivada a aplicar padrões mesmo que a necessidade no projeto não seja tão forte quanto seria em um projeto profissional real.

O objetivo é dar aos alunos a oportunidade de implementar os padrões em um projeto concreto.

### Diferença entre uso pedagógico e uso profissional

No uso profissional, um padrão só deveria ser aplicado quando existe uma necessidade real.

Na aula, foi reforçado:

- Desenvolvedores de software não são adivinhos.
- Não se deve prever funcionalidades futuras sem base em requisitos.
- Não se deve adicionar complexidade sem motivo.
- Se o requisito atual não exige uma solução extensível, talvez não seja necessário aplicar um padrão.

### Padrões aumentam a complexidade

Foi destacado que padrões de projeto são uma “faca de dois gumes”.

Eles podem melhorar a manutenibilidade, mas também aumentam a complexidade do código.

Ao aplicar um padrão, o sistema pode passar a exigir que quem for manter o código entenda:

- o padrão usado;
- o motivo de ele estar ali;
- a estrutura adicional criada;
- a relação entre interfaces, classes concretas e objetos.

Esse custo foi chamado de **overhead cognitivo** ou carga cognitiva adicional.

### Exemplo de uso exagerado de padrões

Foi contado um exemplo em que, durante a graduação, um sistema simples acabou recebendo muitos padrões de projeto sem necessidade real.

A motivação era aprender, mas o resultado foi um sistema excessivamente modular e difícil de entender.

A lição extraída foi:

- aplicar padrões ajuda a aprender;
- aplicar padrões sem necessidade real pode tornar o sistema difícil de manter;
- modularidade excessiva também pode prejudicar a simplicidade;
- simplicidade também é uma qualidade de projeto.

---

## 4. Overhead cognitivo e manutenibilidade

### O que é overhead cognitivo

Overhead cognitivo é o conjunto de conceitos que uma pessoa precisa entender antes de conseguir trabalhar em um sistema.

No caso dos projetos da disciplina, já existe uma carga cognitiva associada a:

- Java;
- HTML;
- Thymeleaf;
- Bootstrap;
- Javalin;
- PostgreSQL;
- Docker;
- arquitetura MVC;
- controllers;
- services;
- models;
- persistência;
- autenticação;
- autorização;
- logs;
- testes.

Quando se adiciona um padrão de projeto, mais uma camada conceitual é introduzida.

### Exemplo: MVC

O padrão arquitetural **MVC** foi usado como exemplo.

Em um projeto MVC, quem for ler o código precisa entender conceitos como:

- Model;
- View;
- Controller;
- Service.

Esses conceitos ajudam a organizar o sistema, mas também exigem que o desenvolvedor entenda a estrutura antes de alterar o código.

### Equilíbrio entre simplicidade e manutenção

A aula reforçou que uma solução de projeto precisa equilibrar:

- simplicidade;
- clareza;
- flexibilidade;
- manutenibilidade;
- custo cognitivo.

Um padrão deve ser usado quando a complexidade adicional vale a pena.

---

## 5. Orientação a objetos como base dos padrões

Foi reforçado que os padrões estudados na disciplina não exigirão recursos avançados de Java.

Os principais recursos utilizados serão:

- classes;
- objetos;
- interfaces;
- herança;
- polimorfismo.

O ponto central não é aprender uma sintaxe nova, mas aprender a usar os recursos básicos da orientação a objetos de maneira mais elegante e adequada ao projeto.

---

## 6. Modelos, classes e requisitos

### Classe como modelo

Uma classe foi definida como um **modelo**.

Um modelo é uma representação simplificada de alguma coisa.

No contexto de orientação a objetos, uma classe representa uma entidade ou conceito relevante para o sistema.

Exemplo usado na aula:

- Classe `Estudante`
- Atributos:
  - `nome`
  - `matricula`

A classe `Estudante` representa, para aquele sistema, aquilo que é necessário saber sobre um estudante.

### Um modelo deve conter apenas o necessário

Foi enfatizado que um modelo não deve conter informações sem necessidade.

Por exemplo, ao pensar em uma classe `Estudante`, alguém poderia sugerir atributos como:

- e-mail;
- curso;
- período;
- disciplinas matriculadas.

Mas esses atributos só devem ser adicionados se houver um requisito do sistema que justifique sua presença.

A regra apresentada foi:

> O modelo deve representar a informação necessária para que o sistema tome decisões.

Um modelo com informação demais pode ser ruim, porque aumenta a complexidade sem necessidade.

### Não adicionar informações sem validar com o cliente

Foi reforçado que o desenvolvedor não deve adicionar informações nas classes apenas porque acha que conhece o negócio.

Mesmo que o desenvolvedor entenda bem o domínio, os dados necessários devem estar ligados aos requisitos e precisam ser validados com o cliente.

### Desenvolvedor precisa entender o negócio

Apesar disso, foi comentado que profissionais de computação frequentemente acabam entendendo muito sobre o negócio do cliente.

Isso acontece porque, para desenvolver um sistema, é necessário compreender:

- entidades;
- relacionamentos;
- regras de negócio;
- processos;
- exceções;
- integrações entre áreas.

Muitas vezes, o conhecimento sobre o negócio está espalhado em diferentes setores da organização. O desenvolvedor precisa reunir essas informações para construir um sistema coerente.

---

## 7. Objetos, instâncias e referências em memória

Antes de avançar para o padrão Strategy, a aula fez uma revisão importante sobre objetos, instâncias e referências.

### Instanciar uma classe

Quando se faz:

```java
Estudante e = new Estudante();
```

está sendo criada uma instância da classe `Estudante`.

Na prática, isso significa que um espaço na memória é reservado para armazenar os dados daquele objeto.

A variável `e` não é o objeto em si. Ela é uma referência para a posição de memória onde o objeto está armazenado.

### Variáveis como referências

Uma variável de objeto não deve ser imaginada como uma “caixa” que contém o objeto.

Ela deve ser entendida como uma **referência**, uma “seta” ou um “apontador” para uma posição de memória.

Exemplo:

```java
Estudante e = new Estudante();
e.setNome("Joao");

Estudante e2 = e;
```

Nesse caso:

- `e` aponta para um objeto `Estudante`;
- `e2` passa a apontar para o mesmo objeto;
- não foi criada uma cópia do estudante;
- as duas variáveis referenciam a mesma instância.

Se for chamado:

```java
e.getNome();
e2.getNome();
```

ambos retornam o mesmo nome, porque acessam o mesmo objeto.

### Referência nula

Se for feito:

```java
e = null;
```

a variável `e` deixa de apontar para o objeto.

Mas, se `e2` ainda aponta para aquele objeto, ele continua acessível:

```java
e2.getNome();
```

Esse código ainda funciona porque `e2` mantém a referência.

Já o seguinte código não funciona:

```java
e.getNome();
```

porque `e` está apontando para `null`.

### Listas também armazenam referências

A aula também revisou o funcionamento de listas.

Quando se adiciona um objeto a uma lista, a lista não cria uma cópia completa do objeto. Ela armazena uma referência para o objeto.

Exemplo:

```java
ArrayList<Estudante> lista = new ArrayList<>();
lista.add(e2);
```

A lista passa a ter uma referência para o mesmo objeto apontado por `e2`.

Se existirem três objetos `Estudante` diferentes, todos com o nome “Maria”, eles são três instâncias distintas, mesmo que tenham o mesmo valor no atributo `nome`.

### Espaço de memória em listas

Se três objetos estudantes forem adicionados a uma lista, o espaço ocupado não será o dobro.

A memória terá:

- o espaço ocupado pelos três objetos;
- mais o espaço ocupado pela estrutura da lista;
- mais as referências dentro da lista.

A lista não duplica os objetos.

### ArrayList e capacidade interna

Foi mencionado em aula que um `ArrayList`, ao ser instanciado, trabalha com uma estrutura interna semelhante a um array com capacidade inicial.

Como simplificação didática, foi citado o tamanho 10.

Para evitar confusão, é importante entender que esse detalhe depende da implementação e da versão do Java. Em versões modernas, o `ArrayList` pode começar com um array interno vazio e alocar capacidade padrão quando os primeiros elementos são adicionados.

O ponto essencial da aula é:

> A lista armazena referências para objetos, não cópias completas desses objetos.

### Alteração de elementos em lista

Foi comentado que, em Java, não se pode atribuir diretamente a uma chamada de `get`.

A forma correta de substituir um elemento da lista é usar `set`.

Exemplo:

```java
lista.set(0, null);
```

---

## 8. Classe, instância e o uso de `this`

### Programar na classe, executar na instância

Uma das mensagens centrais da aula foi:

> Eu programo na classe, mas executo na instância.

A classe especifica o comportamento. A execução acontece nos objetos instanciados a partir daquela classe.

Se existem duas instâncias de uma mesma classe, o mesmo método pode ser executado em cada uma delas, mas usando os dados de cada objeto.

### O que é `this`

O `this` representa a própria instância que está executando o método.

Quando um objeto executa um método e passa `this` como parâmetro, ele está passando uma referência para si mesmo.

Exemplo conceitual:

```java
gravador.salvar(this);
```

Nesse caso, o objeto atual está dizendo ao gravador:

> Salve este objeto que está executando o método agora.

Essa explicação foi importante para entender o exemplo do padrão Strategy.

### Observação sobre String e memória

Durante a explicação de referências, foi usado o exemplo de uma `String` associada a uma sequência de caracteres.

Essa explicação deve ser entendida de forma didática. A implementação interna de `String` pode variar conforme a versão do Java.

O ponto importante para a aula é:

> Objetos podem referenciar outros objetos ou estruturas internas, e variáveis de objeto trabalham com referências.

---

## 9. Padrão Strategy

### Problema inicial

O problema usado para introduzir o padrão Strategy foi o seguinte:

Existe uma classe `Estudante`, com atributos como:

- `nome`;
- `matricula`.

Essa classe precisa ter um método para salvar o estudante.

A questão proposta foi:

> Como permitir que o estudante seja salvo de diferentes formas, por exemplo em CSV ou em JSON?

### Observação sobre o exemplo `Estudante.salvar()`

O exemplo de `Estudante.salvar()` foi usado de forma pedagógica para explicar o padrão Strategy.

Em sistemas organizados em camadas, como os projetos da disciplina, a persistência normalmente não fica dentro da entidade de domínio. Em muitos casos, a gravação de dados fica em classes como:

- DAO;
- Repository;
- Service;
- classe de persistência;
- classe exportadora.

Portanto, a ideia principal do exemplo não é dizer que toda entidade deve saber salvar a si mesma.

A ideia é mostrar que:

> Quando uma ação pode ser realizada de diferentes formas, essas formas podem ser separadas em estratégias diferentes.

### Primeira solução: colocar tudo dentro de `Estudante`

Uma primeira possibilidade seria colocar o código de gravação diretamente dentro da classe `Estudante`.

Por exemplo, o método `salvar` poderia abrir um arquivo, usar `BufferedWriter`, montar uma linha CSV e gravar os dados.

Mas essa solução mistura responsabilidades:

- a classe `Estudante` representa o modelo do estudante;
- o código de gravação em arquivo representa uma preocupação de persistência.

Isso aumenta o acoplamento e reduz a separação de responsabilidades.

### Separando a gravação em outra classe

A solução inicial proposta foi criar uma classe responsável por gravar o estudante em CSV.

Exemplo conceitual:

```java
class GravadorCSV {
    void salvar(Estudante estudante) {
        // Código com BufferedWriter, FileWriter etc.
    }
}
```

Nesse caso, a classe `GravadorCSV` fica responsável pelos detalhes de Java IO e escrita em arquivo.

A classe `Estudante` deixa de conhecer os detalhes de gravação em CSV.

### Benefício parcial: separação de responsabilidades

Com essa separação:

- `Estudante` não precisa importar classes de `java.io`;
- `GravadorCSV` fica acoplado aos detalhes de gravação;
- o modelo fica mais limpo;
- a persistência fica em uma classe específica.

Isso já é uma melhoria, porque reduz o acoplamento entre o modelo e os detalhes técnicos da gravação.

### Problema restante: acoplamento com uma implementação específica

Mesmo separando a gravação em outra classe, ainda existe um problema.

Se `Estudante` tiver um atributo do tipo `GravadorCSV`, ele continua acoplado a uma implementação específica.

Exemplo conceitual:

```java
class Estudante {
    private GravadorCSV gravador;

    void salvar() {
        gravador.salvar(this);
    }
}
```

Nesse caso, se for necessário mudar de CSV para JSON, a classe `Estudante` precisará ser alterada.

Isso não é ideal.

### Solução: usar uma interface

Para quebrar o acoplamento entre `Estudante` e as formas concretas de gravação, foi criada uma interface.

Exemplo conceitual:

```java
interface GravadorEstudante {
    void salvar(Estudante estudante);
}
```

A partir dela, diferentes estratégias podem ser implementadas:

```java
class GravadorCSV implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Salva em CSV
    }
}

class GravadorJSON implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Salva em JSON
    }
}
```

Agora, a classe `Estudante` depende da interface, e não das classes concretas:

```java
class Estudante {
    private String nome;
    private String matricula;
    private GravadorEstudante gravador;

    public void setGravador(GravadorEstudante gravador) {
        this.gravador = gravador;
    }

    public void salvar() {
        gravador.salvar(this);
    }
}
```

### Observação sobre o gravador receber ou armazenar o estudante

Durante a explicação, apareceu a ideia de o gravador ter uma referência para o estudante.

No exemplo final do Strategy, a forma mais simples é o gravador **não armazenar** o estudante como atributo.

Ele recebe o estudante no momento da chamada:

```java
gravador.salvar(this);
```

Assim, o gravador executa a ação usando o objeto recebido como parâmetro.

### Cuidado: estratégia não configurada

No exemplo anterior, se `gravador` estiver `null`, a chamada a `gravador.salvar(this)` causará erro.

Em uma implementação real, é necessário garantir que a estratégia foi configurada antes de chamar `salvar`.

Uma forma simples de tratar isso é validar antes de executar:

```java
public void salvar() {
    if (gravador == null) {
        throw new IllegalStateException("Gravador não configurado");
    }

    gravador.salvar(this);
}
```

Também seria possível definir uma estratégia padrão.

### Uso do Strategy

No código cliente, é possível escolher a estratégia de gravação:

```java
Estudante e = new Estudante();
e.setNome("Joao");

e.setGravador(new GravadorCSV());
e.salvar();
```

Se quiser trocar a estratégia:

```java
e.setGravador(new GravadorJSON());
e.salvar();
```

A classe `Estudante` não precisa ser modificada para isso.

### Definição didática de Strategy

O padrão **Strategy** é usado quando uma classe precisa executar uma operação cujo comportamento pode variar.

Cada variação é encapsulada em uma classe diferente, permitindo trocar o comportamento sem alterar a classe principal.

Em outras palavras:

> O Strategy encapsula algoritmos ou comportamentos intercambiáveis.

No exemplo da aula:

- a ação é salvar um estudante;
- as estratégias são salvar em CSV, salvar em JSON, salvar em banco de dados etc.

A quebra de acoplamento é uma consequência importante do Strategy, mas o problema principal é a existência de **diferentes formas de executar uma mesma ação**.

### Strategy como ponto de extensibilidade

O Strategy cria um ponto de extensibilidade no código.

Se no futuro for necessário salvar o estudante em outro formato, basta criar uma nova classe que implemente a interface.

Exemplo:

```java
class GravadorBancoDeDados implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Salva no banco de dados
    }
}
```

A classe `Estudante` continua igual.

### Exemplos de uso do Strategy

A aula apresentou outros exemplos de situações em que o Strategy pode ser aplicado.

#### Cálculo de imposto

Um produto pode ter diferentes formas de calcular imposto:

- imposto estadual;
- imposto federal;
- IPI;
- outras regras fiscais.

Nesse caso, poderia haver uma interface de cálculo de imposto e diferentes estratégias concretas.

#### Notificação

Um sistema pode precisar notificar uma pessoa de diferentes formas:

- e-mail;
- SMS;
- WhatsApp;
- alerta na interface.

Cada forma de notificação pode ser uma estratégia diferente.

#### Cálculo de salário

Um sistema pode calcular salário de formas diferentes dependendo do tipo de funcionário:

- funcionário comum;
- vendedor com comissão;
- trabalhador com adicional de insalubridade;
- funcionário com horas extras.

Cada regra de cálculo pode ser implementada como uma estratégia.

### Quando usar Strategy

Use Strategy quando:

- uma classe tem um método cuja implementação pode variar;
- existem diferentes formas de executar a mesma ação;
- você quer trocar o comportamento sem alterar a classe principal;
- você quer reduzir acoplamento entre a entidade e suas variações de comportamento;
- você quer permitir extensão futura por meio de novas classes;
- você quer encapsular algoritmos ou comportamentos intercambiáveis.

### Quando não usar Strategy

Não use Strategy apenas porque o padrão é elegante.

Evite aplicar Strategy quando:

- existe apenas uma forma real de executar a ação;
- não há requisito de variação;
- a solução simples já atende;
- a criação da interface e das classes extras só aumentaria a complexidade.

### Papéis do Strategy

O padrão Strategy costuma ter três papéis principais:

- **Contexto**: classe que usa a estratégia. No exemplo, `Estudante`.
- **Strategy**: interface comum das estratégias. No exemplo, `GravadorEstudante`.
- **ConcreteStrategy**: implementações concretas. No exemplo, `GravadorCSV`, `GravadorJSON` e `GravadorBancoDeDados`.

---

## 10. Desenvolvimento com IA e design de software

Durante a explicação sobre o exemplo do estudante, foi feita uma observação importante sobre desenvolvimento usando IA.

Foi destacado que, ao programar com IA, o desenvolvedor não deve atuar apenas no nível da sintaxe.

O ideal é atuar em um nível de design.

Ou seja, em vez de se preocupar apenas com detalhes como abrir um `BufferedWriter` ou escolher uma biblioteca de CSV, o desenvolvedor deve orientar a IA sobre a estrutura desejada do sistema.

Exemplo de orientação conceitual:

> Implemente a classe Estudante separando o modelo da forma de persistência. Quero que haja quebra de acoplamento entre Estudante e as estratégias de gravação.

Também foi sugerido que o aluno pode pedir à IA para aplicar um padrão específico:

> Aplique o padrão Strategy para separar a entidade Estudante das diferentes formas de salvá-la.

A mensagem central foi:

- o desenvolvedor precisa entender o design;
- a IA pode ajudar na implementação;
- mas o desenvolvedor deve direcionar como o sistema será estruturado;
- quem não entende o projeto fica dependente da IA em um nível superficial.

---

## 11. Padrão Composite

### Problema apresentado

O padrão **Composite** foi introduzido a partir de um exemplo de rede de computadores.

A situação imaginada foi uma rede com diferentes equipamentos:

- roteador;
- switch;
- servidor;
- access point;
- computador;
- celular;
- outros dispositivos.

Alguns desses equipamentos podem conter ou conectar outros equipamentos.

Por exemplo:

- um roteador pode conectar switches, computadores, servidores e access points;
- um switch pode conectar computadores, servidores, roteadores e access points;
- um access point pode conectar celulares e outros dispositivos.

### Métodos comuns dos equipamentos de rede

Foi considerado que todos os equipamentos de rede poderiam ter métodos como:

- `getIP`;
- `getMAC`;
- `up`.

O método `getIP` retornaria o endereço IP.

O método `getMAC` retornaria o endereço físico da placa de rede.

O método `up` indicaria se o equipamento está ativo ou inativo na rede.

### Observação sobre a modelagem de rede

O exemplo da rede foi usado com objetivo didático.

Em uma modelagem real de redes, alguns equipamentos podem ter múltiplos IPs ou múltiplos MACs. Um roteador, por exemplo, pode ter várias interfaces de rede. Um switch pode ou não ter IP de gerenciamento.

Portanto, os métodos `getIP()` e `getMAC()` foram usados para simplificar a ideia de uma interface comum entre equipamentos.

O ponto principal do exemplo é entender o problema de composição de objetos, e não construir uma modelagem completa de redes.

### Endereço MAC e endereço IP

Foi explicado que:

- o endereço MAC é o endereço físico associado à interface de rede;
- o endereço IP é o endereço lógico atribuído na rede.

Um computador pode mudar de endereço IP ao ser conectado em outra rede, mas o endereço MAC da placa permanece o mesmo.

Por exemplo:

- em um laboratório, um computador pode receber um IP da rede `10.0.1.x`;
- em outro laboratório, pode receber um IP da rede `10.0.2.x`;
- o endereço MAC continua sendo o mesmo.

O endereço MAC é projetado para ser único, mas pode ser alterado ou duplicado em algumas situações. Para o funcionamento adequado de uma rede local, o importante é que não haja conflito de MACs no mesmo domínio de rede.

### Problema de acoplamento

Se a classe `Roteador` precisar ter um método específico para adicionar cada tipo de equipamento, ela ficará muito acoplada.

Exemplo conceitual do problema:

```java
class Roteador {
    void addSwitch(Switch s) { }
    void addComputador(Computador c) { }
    void addServidor(Servidor s) { }
    void addAccessPoint(AccessPoint ap) { }
}
```

O problema é que, a cada novo tipo de equipamento, a classe `Roteador` precisaria ser alterada.

Exemplo:

- se for adicionada uma geladeira inteligente à rede;
- se for adicionado um novo tipo de sensor;
- se for adicionado outro equipamento qualquer.

A classe `Roteador` precisaria conhecer todos esses tipos.

Isso gera alto acoplamento entre classes compostas e seus componentes.

### Componentes simples e componentes compostos

A aula propôs classificar os objetos em duas categorias.

#### Componentes simples

São objetos que não contêm outros componentes.

Exemplos:

- computador;
- celular;
- servidor, dependendo da modelagem.

#### Componentes compostos

São objetos que podem conter ou conectar outros componentes.

Exemplos:

- roteador;
- switch;
- access point.

A ideia do Composite é permitir tratar objetos simples e compostos de forma uniforme.

### Interface comum: ComponenteDeRede

Para resolver o problema, foi criada uma interface comum.

Exemplo conceitual:

```java
interface ComponenteDeRede {
    String getIP();
    String getMAC();
    boolean up();
}
```

Todos os equipamentos da rede devem implementar essa interface direta ou indiretamente.

### Classe composta

Foi criada uma classe para representar componentes compostos de rede.

Essa classe também implementa a interface `ComponenteDeRede`, mas contém uma lista de outros componentes.

Exemplo conceitual:

```java
class ComponenteDeRedeComposto implements ComponenteDeRede {
    private List<ComponenteDeRede> componentes = new ArrayList<>();

    public void addComponente(ComponenteDeRede componente) {
        componentes.add(componente);
    }

    public boolean up() {
        for (ComponenteDeRede c : componentes) {
            if (!c.up()) {
                return false;
            }
        }
        return true;
    }

    public String getIP() {
        // Retorna o IP do componente composto
    }

    public String getMAC() {
        // Retorna o MAC do componente composto
    }
}
```

### Implementação dos equipamentos compostos

No exemplo da aula, equipamentos compostos podem herdar de `ComponenteDeRedeComposto`.

Exemplo:

```java
class Roteador extends ComponenteDeRedeComposto {
}

class Switch extends ComponenteDeRedeComposto {
}

class AccessPoint extends ComponenteDeRedeComposto {
}
```

Com isso, essas classes já passam a ter a capacidade de adicionar componentes de rede sem precisar conhecer o tipo concreto de cada componente.

Essa é uma forma possível de implementar Composite, mas não é a única. Uma classe composta também poderia implementar a interface diretamente e gerenciar sua própria lista de componentes.

### Implementação dos equipamentos simples

Equipamentos simples implementam diretamente a interface `ComponenteDeRede`.

Exemplo:

```java
class Computador implements ComponenteDeRede {
    public String getIP() {
        // Retorna IP
    }

    public String getMAC() {
        // Retorna MAC
    }

    public boolean up() {
        // Retorna se está ativo
    }
}

class Celular implements ComponenteDeRede {
    public String getIP() {
        // Retorna IP
    }

    public String getMAC() {
        // Retorna MAC
    }

    public boolean up() {
        // Retorna se está ativo
    }
}
```

Os elementos simples **implementam** a interface `ComponenteDeRede`.

### Uso do Composite

Com essa estrutura, o roteador não precisa ter métodos específicos como:

- `addSwitch`;
- `addComputador`;
- `addServidor`;
- `addAccessPoint`.

Ele pode ter apenas:

```java
addComponente(ComponenteDeRede componente)
```

Assim, qualquer objeto que implemente `ComponenteDeRede` pode ser adicionado.

Exemplo conceitual:

```java
Roteador roteador = new Roteador();
Switch sw = new Switch();
Computador computador = new Computador();
Celular celular = new Celular();

roteador.addComponente(sw);
roteador.addComponente(computador);
sw.addComponente(celular);
```

O roteador não precisa saber se o componente adicionado é um switch, computador, servidor ou celular.

Ele sabe apenas que é um `ComponenteDeRede`.

### Implementação do método `up`

Foi proposta uma regra simplificada para o método `up`.

A ideia foi:

- se todos os componentes internos estão ativos, o componente composto está ativo;
- se qualquer componente interno estiver inativo, o componente composto retorna `false`.

Exemplo conceitual:

```java
public boolean up() {
    for (ComponenteDeRede c : componentes) {
        if (!c.up()) {
            return false;
        }
    }
    return true;
}
```

Essa regra booleana é uma simplificação.

Em um sistema real, talvez fosse melhor representar o estado por categorias como:

- verde;
- amarelo;
- vermelho.

Ou por um `enum`, por exemplo:

```java
enum StatusRede {
    VERDE,
    AMARELO,
    VERMELHO
}
```

Mas, para simplificar a aula, foi usada uma regra com `true` e `false`.

### Definição didática de Composite

O padrão **Composite** é usado quando há objetos compostos por outros objetos e se deseja tratar objetos simples e compostos por meio de uma interface comum.

Na aula, a definição prática foi:

> O Composite resolve o problema de acoplamento entre classes compostas e seus componentes.

De forma mais precisa:

> O Composite reduz o acoplamento com classes concretas. O objeto composto deixa de depender de `Computador`, `Celular`, `Switch` etc. e passa a depender apenas da interface comum.

O acoplamento não desaparece completamente. Ele passa a existir com a interface comum, e não com cada classe concreta.

### Principal benefício

O principal benefício do Composite é que o objeto composto não precisa conhecer os tipos concretos dos objetos que contém.

Ele só conhece a interface comum.

Isso reduz o acoplamento e facilita a extensão do sistema.

### Analogia da mesa

Foi usada a analogia de uma mesa com vários objetos em cima.

A mesa pode ter:

- notebook;
- celular;
- outros objetos.

Para a mesa, todos são simplesmente objetos sobre ela. Ela não precisa conhecer os detalhes de cada um.

Da mesma forma, no Composite, o objeto composto trata os componentes de maneira uniforme, sem conhecer suas classes concretas.

### Composite não é apenas herança

No exemplo, a herança aparece para reaproveitar o comportamento da classe `ComponenteDeRedeComposto`.

Mas o ponto central do Composite não é a herança.

O ponto central é combinar:

- polimorfismo;
- interface comum;
- composição de objetos;
- uma estrutura em que objetos compostos podem conter outros componentes.

A herança pode ser usada como apoio, mas o padrão está mais ligado à composição recursiva e ao tratamento uniforme de objetos simples e compostos.

### Papéis do Composite

O padrão Composite costuma ter três papéis principais:

- **Component**: interface comum. No exemplo, `ComponenteDeRede`.
- **Leaf**: componente simples, sem filhos. No exemplo, `Computador` e `Celular`.
- **Composite**: componente composto, capaz de conter outros componentes. No exemplo, `Roteador`, `Switch` e `AccessPoint`.

---

## 12. Comparação entre Strategy e Composite

### Strategy

O Strategy resolve o problema de variação de comportamento.

Use quando:

- o mesmo método pode ter diferentes implementações;
- existem diferentes estratégias para realizar uma ação;
- você quer trocar o comportamento sem alterar a classe principal;
- você quer encapsular algoritmos ou comportamentos intercambiáveis.

Exemplos:

- salvar em CSV, JSON ou banco;
- calcular imposto de formas diferentes;
- notificar por e-mail, SMS ou WhatsApp;
- calcular salário por regras diferentes.

### Composite

O Composite resolve o problema de composição de objetos.

Use quando:

- objetos podem conter outros objetos;
- objetos simples e compostos devem ser tratados de forma uniforme;
- uma classe composta não deve conhecer todos os tipos concretos dos seus componentes;
- você quer reduzir o acoplamento entre objetos compostos e classes concretas.

Exemplos:

- rede de computadores;
- estruturas de pastas e arquivos;
- menus com submenus;
- árvores de componentes;
- hierarquias de elementos.

### Interfaces em Strategy e Composite

Os dois padrões usam interface e polimorfismo, mas por motivos diferentes.

No **Strategy**:

- a interface representa uma família de algoritmos ou comportamentos substituíveis;
- a classe principal escolhe ou recebe uma estratégia concreta.

No **Composite**:

- a interface representa um tipo comum para objetos simples e compostos;
- o objeto composto armazena uma coleção de objetos dessa interface.

### Frases de memorização

Para lembrar do Strategy:

> Mesmo método, diferentes estratégias.

Uma formulação mais precisa:

> Um comportamento variável é extraído para objetos separados, permitindo escolher ou trocar a estratégia usada.

Para lembrar do Composite:

> Objetos simples e compostos são tratados por meio de uma interface comum.

Ou ainda:

> Objeto composto sem acoplamento aos tipos concretos dos seus componentes.

---

## 13. Exemplo resumido de Strategy

```java
interface GravadorEstudante {
    void salvar(Estudante estudante);
}

class GravadorCSV implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Salvar em CSV
    }
}

class GravadorJSON implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Salvar em JSON
    }
}

class Estudante {
    private String nome;
    private String matricula;
    private GravadorEstudante gravador;

    public void setGravador(GravadorEstudante gravador) {
        this.gravador = gravador;
    }

    public void salvar() {
        if (gravador == null) {
            throw new IllegalStateException("Gravador não configurado");
        }

        gravador.salvar(this);
    }
}
```

Uso:

```java
Estudante estudante = new Estudante();

estudante.setGravador(new GravadorCSV());
estudante.salvar();

estudante.setGravador(new GravadorJSON());
estudante.salvar();
```

Observação:

> Esse exemplo é pedagógico. Em uma arquitetura em camadas, a persistência poderia estar em um DAO, Repository ou Service. O objetivo aqui é mostrar a troca de estratégias.

---

## 14. Exemplo resumido de Composite

```java
interface ComponenteDeRede {
    String getIP();
    String getMAC();
    boolean up();
}

class ComponenteDeRedeComposto implements ComponenteDeRede {
    private List<ComponenteDeRede> componentes = new ArrayList<>();

    public void addComponente(ComponenteDeRede componente) {
        componentes.add(componente);
    }

    public boolean up() {
        for (ComponenteDeRede c : componentes) {
            if (!c.up()) {
                return false;
            }
        }
        return true;
    }

    public String getIP() {
        // Retorna IP do componente composto
        return "";
    }

    public String getMAC() {
        // Retorna MAC do componente composto
        return "";
    }
}

class Roteador extends ComponenteDeRedeComposto {
}

class Switch extends ComponenteDeRedeComposto {
}

class AccessPoint extends ComponenteDeRedeComposto {
}

class Computador implements ComponenteDeRede {
    public String getIP() {
        return "";
    }

    public String getMAC() {
        return "";
    }

    public boolean up() {
        return true;
    }
}

class Celular implements ComponenteDeRede {
    public String getIP() {
        return "";
    }

    public String getMAC() {
        return "";
    }

    public boolean up() {
        return true;
    }
}
```

Uso:

```java
Roteador roteador = new Roteador();
Switch sw = new Switch();
Computador computador = new Computador();
Celular celular = new Celular();

roteador.addComponente(sw);
roteador.addComponente(computador);
sw.addComponente(celular);

boolean redeAtiva = roteador.up();
```

Observação:

> Esse exemplo simplifica a modelagem de redes. Em sistemas reais, equipamentos podem ter múltiplas interfaces, múltiplos IPs e regras de disponibilidade mais complexas.

---

## 15. Cuidados ao aplicar padrões de projeto

### Não aplicar padrão sem necessidade

Foi reforçado que aplicar padrão sem necessidade pode tornar o sistema mais complexo do que deveria.

Antes de aplicar um padrão, pergunte:

- Existe uma variação real de comportamento?
- Existe necessidade de extensão?
- Existe acoplamento excessivo?
- O sistema ficará mais fácil de manter?
- A complexidade adicional vale a pena?

### Aprender justifica experimentar

No contexto da disciplina, experimentar padrões no projeto pode ser útil mesmo que a necessidade não seja perfeita.

O objetivo é aprender.

Mas é importante sair da disciplina entendendo que, na vida profissional, padrões devem ser aplicados por necessidade de projeto.

### Evitar “macarronada de padrões”

Foi usado o exemplo de um sistema com muitos padrões aplicados sem necessidade, o que deixou o código difícil de entender e modificar.

A lição foi:

- padrões ajudam quando resolvem um problema real;
- padrões atrapalham quando são usados apenas para mostrar conhecimento;
- simplicidade também é uma qualidade de projeto.

---

## 16. Orientações do Professor

- Todos os projetos devem usar Docker.
- O front-end deve usar Thymeleaf com Bootstrap.
- O back-end deve usar Javalin.
- O banco de dados deve ser PostgreSQL.
- O projeto deve estar em produção.
- O projeto deve ter uso de log.
- O projeto deve ter testes automatizados.
- O projeto deve ter autenticação.
- O projeto deve ter autorização.
- O projeto deve ter organização modular do código.
- Será executado um script para avaliar os projetos.
- O feedback do script será gerado em um arquivo Markdown na raiz de cada projeto.
- Caso o feedback automático esteja errado, o aluno deve avisar o professor para análise específica.
- A avaliação só será fechada quando professor e grupo estiverem de acordo.
- Os alunos devem estudar o padrão Strategy.
- Os alunos devem implementar alguma coisa usando Strategy.
- Os alunos devem estudar o padrão Composite.
- Os alunos devem implementar alguma coisa usando Composite.
- As atividades de Strategy e Composite serão disponibilizadas.
- As atividades não serão obrigatórias para nota.
- Mesmo não valendo ponto na disciplina, as atividades foram recomendadas como importantes para a aprendizagem.
- Os alunos podem usar IA para identificar oportunidades de aplicar Strategy e Composite no projeto.
- Ao usar IA, os alunos devem pedir sugestões no plural, buscando diferentes possibilidades de aplicação.
- Se a IA estiver forçando demais a aplicação de um padrão, os alunos devem procurar o professor.
- Pode ser que não exista uma aplicação natural de algum padrão em determinado projeto.
- Caso não exista aplicação natural, é possível discutir com o professor alguma alternativa pedagógica.
- Não se espera que todos os padrões estudados sejam implementados no projeto.
- Os alunos devem implementar o máximo que puderem para aprender, sem transformar o projeto em algo excessivamente complexo.
- Quem tiver problema no projeto, especialmente relacionado ao servidor, deve mandar mensagem pelo Discord.
- Os alunos não devem esperar apenas pela aula para resolver problemas do projeto.
- Os alunos devem aproveitar o dia para quitar pendências com o servidor antes da execução do script de avaliação.

---

## 17. Conceitos para se Aprofundar

- Padrões de projeto.
- Catálogos de padrões de projeto.
- Design orientado a objetos.
- Manutenibilidade.
- Acoplamento.
- Baixo acoplamento.
- Coesão.
- Separação de responsabilidades.
- Overhead cognitivo.
- MVC.
- Controller.
- Service.
- Model.
- DAO.
- Repository.
- Interface.
- Polimorfismo.
- Herança.
- Composição.
- Classe.
- Objeto.
- Instância.
- Referência de memória.
- `null`.
- `this`.
- `ArrayList`.
- Diferença entre objeto e referência.
- Diferença entre classe e instância.
- Strategy.
- Contexto no Strategy.
- Strategy como interface de comportamento.
- ConcreteStrategy.
- Composite.
- Component.
- Leaf.
- Composite como componente composto.
- Componentes simples.
- Componentes compostos.
- Interface comum.
- Extensibilidade.
- Java IO.
- `BufferedWriter`.
- `FileWriter`.
- CSV.
- JSON.
- Endereço IP.
- Endereço MAC.
- Estado de disponibilidade de componentes.
- Desenvolvimento de software com apoio de IA.
- Uso de IA em nível de design, não apenas em nível de sintaxe.

---

## 18. Questões para Revisão

1. O que são padrões de projeto?
2. Qual é o principal objetivo de usar um padrão de projeto?
3. Por que padrões de projeto podem aumentar a complexidade do sistema?
4. O que significa overhead cognitivo?
5. Por que não devemos aplicar padrões de projeto sem necessidade?
6. Qual é a diferença entre uso pedagógico e uso profissional de padrões de projeto?
7. O que significa dizer que uma classe é um modelo?
8. Por que uma classe não deve conter atributos que não estão ligados a requisitos do sistema?
9. O que acontece na memória quando usamos `new` em Java?
10. Uma variável de objeto guarda o objeto ou uma referência para o objeto?
11. O que acontece quando duas variáveis apontam para o mesmo objeto?
12. Se uma variável for definida como `null`, o objeto necessariamente deixa de existir?
13. Quando um objeto é adicionado a uma lista, a lista cria uma cópia do objeto?
14. Por que é importante entender referências para evitar problemas com `NullPointerException`?
15. O que significa a frase “programamos na classe, mas executamos na instância”?
16. O que representa o `this` em Java?
17. Qual problema inicial foi usado para explicar o padrão Strategy?
18. Por que não é ideal colocar o código de gravação em CSV diretamente dentro da classe `Estudante`?
19. Por que o exemplo `Estudante.salvar()` deve ser entendido como pedagógico?
20. Em uma arquitetura em camadas, que tipos de classe poderiam ficar responsáveis pela persistência?
21. Como uma interface ajuda a reduzir o acoplamento no Strategy?
22. No exemplo da aula, quais foram as estratégias de gravação mencionadas?
23. Qual é a definição didática do padrão Strategy?
24. Por que dizer que Strategy é apenas “quebra de acoplamento” é incompleto?
25. O que pode acontecer se a estratégia não for configurada antes da chamada do método?
26. Em que situações o Strategy deve ser usado?
27. Cite um exemplo de uso de Strategy diferente do exemplo de gravação de estudante.
28. Quais são os papéis principais no padrão Strategy?
29. Qual problema inicial foi usado para explicar o padrão Composite?
30. Por que uma classe `Roteador` com métodos como `addSwitch`, `addComputador` e `addServidor` fica muito acoplada?
31. Qual é a diferença entre componente simples e componente composto?
32. Qual interface foi proposta no exemplo de rede de computadores?
33. Por que `getIP()` e `getMAC()` são simplificações no exemplo da rede?
34. Por que o objeto composto deve armazenar uma lista de componentes pela interface comum?
35. Como o Composite reduz o acoplamento entre objetos compostos e seus componentes?
36. O acoplamento desaparece completamente no Composite?
37. Qual é a diferença entre depender de classes concretas e depender de uma interface?
38. Qual é a diferença principal entre Strategy e Composite?
39. Qual é o papel da interface no Strategy?
40. Qual é o papel da interface no Composite?
41. Quais são os papéis principais no padrão Composite?
42. Como a IA pode ajudar na aplicação de padrões de projeto?
43. Por que o aluno precisa entender design de software mesmo usando IA para programar?


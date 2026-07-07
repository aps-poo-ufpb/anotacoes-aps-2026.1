## Seção ampliada — Strategy

## Padrão Strategy

### Ideia central do Strategy

O padrão **Strategy** é usado quando uma classe precisa executar uma ação, mas essa ação pode ser realizada de formas diferentes.

A palavra “strategy” significa **estratégia**. Ou seja, para uma mesma operação, o sistema pode escolher entre diferentes estratégias de execução.

A ideia principal é:

> Separar o comportamento variável em classes próprias, permitindo trocar esse comportamento sem alterar a classe principal.

Em vez de colocar vários `if`, `else if` ou `switch` dentro de uma classe para decidir como uma operação será feita, o Strategy permite criar uma interface comum e várias classes concretas, cada uma com uma implementação diferente.

---

### Problema que o Strategy resolve

Imagine uma classe que precisa executar uma ação, mas essa ação pode variar.

Exemplo:

- salvar em CSV;
- salvar em JSON;
- salvar em banco de dados;
- salvar em arquivo texto.

Uma solução simples, mas ruim para manutenção, seria colocar tudo dentro de um único método:

```java
class Estudante {
    private String nome;
    private String matricula;

    public void salvar(String tipo) {
        if (tipo.equals("CSV")) {
            // Código para salvar em CSV
        } else if (tipo.equals("JSON")) {
            // Código para salvar em JSON
        } else if (tipo.equals("BANCO")) {
            // Código para salvar no banco
        }
    }
}
```

Esse código funciona, mas tem problemas:

- a classe `Estudante` passa a conhecer várias formas de persistência;
- o método `salvar` cresce a cada nova forma de gravação;
- para adicionar uma nova forma de salvar, é preciso alterar `Estudante`;
- a classe fica com baixa coesão, porque mistura dados do estudante com lógica de persistência;
- o código fica mais difícil de testar e manter.

O Strategy resolve isso extraindo cada forma de salvar para uma classe separada.

---

### Estrutura básica do Strategy

O Strategy normalmente envolve três papéis:

- **Contexto**: classe que usa uma estratégia.
- **Strategy**: interface comum para as estratégias.
- **ConcreteStrategy**: classes concretas que implementam as diferentes estratégias.

No exemplo da aula:

- Contexto: `Estudante`;
- Strategy: `GravadorEstudante`;
- ConcreteStrategy: `GravadorCSV`, `GravadorJSON`, `GravadorBancoDeDados`.

---

### Exemplo 1 — Salvando estudante em formatos diferentes

#### Interface da estratégia

```java
interface GravadorEstudante {
    void salvar(Estudante estudante);
}
```

#### Estratégia para CSV

```java
class GravadorCSV implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Código para salvar estudante em CSV
        System.out.println("Salvando estudante em CSV");
    }
}
```

#### Estratégia para JSON

```java
class GravadorJSON implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Código para salvar estudante em JSON
        System.out.println("Salvando estudante em JSON");
    }
}
```

#### Estratégia para banco de dados

```java
class GravadorBancoDeDados implements GravadorEstudante {
    public void salvar(Estudante estudante) {
        // Código para salvar estudante no banco de dados
        System.out.println("Salvando estudante no banco de dados");
    }
}
```

#### Classe que usa a estratégia

```java
class Estudante {
    private String nome;
    private String matricula;
    private GravadorEstudante gravador;

    public Estudante(String nome, String matricula) {
        this.nome = nome;
        this.matricula = matricula;
    }

    public String getNome() {
        return nome;
    }

    public String getMatricula() {
        return matricula;
    }

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

#### Uso

```java
class Exemplo {
    public static void main(String[] args) {
        Estudante estudante = new Estudante("Joao", "20260001");

        estudante.setGravador(new GravadorCSV());
        estudante.salvar();

        estudante.setGravador(new GravadorJSON());
        estudante.salvar();

        estudante.setGravador(new GravadorBancoDeDados());
        estudante.salvar();
    }
}
```

Nesse exemplo, a classe `Estudante` não precisa saber como salvar em CSV, JSON ou banco de dados. Ela apenas delega essa responsabilidade para uma estratégia.

---

### Observação importante sobre esse exemplo

O exemplo `Estudante.salvar()` é pedagógico.

Em uma arquitetura em camadas, como nos projetos da disciplina, talvez fosse mais adequado que a persistência estivesse em outra classe, como:

- `EstudanteDAO`;
- `EstudanteRepository`;
- `EstudanteService`;
- `ExportadorEstudante`;
- `GravadorEstudante`.

O objetivo do exemplo não é dizer que toda entidade deve salvar a si mesma.

O objetivo é mostrar que uma operação variável pode ser separada em estratégias diferentes.

---

### Exemplo 2 — Cálculo de frete

Imagine um sistema de vendas que precisa calcular o frete de um pedido.

O frete pode variar conforme a forma de entrega:

- entrega comum;
- entrega expressa;
- retirada na loja;
- entrega por transportadora.

Uma solução ruim seria colocar todos os cálculos em um único método com vários `if`.

Com Strategy, cada tipo de frete vira uma estratégia.

#### Interface

```java
interface CalculadoraFrete {
    double calcular(double valorPedido);
}
```

#### Estratégia de frete comum

```java
class FreteComum implements CalculadoraFrete {
    public double calcular(double valorPedido) {
        return 15.0;
    }
}
```

#### Estratégia de frete expresso

```java
class FreteExpresso implements CalculadoraFrete {
    public double calcular(double valorPedido) {
        return 30.0;
    }
}
```

#### Estratégia de retirada na loja

```java
class RetiradaNaLoja implements CalculadoraFrete {
    public double calcular(double valorPedido) {
        return 0.0;
    }
}
```

#### Classe Pedido

```java
class Pedido {
    private double valor;
    private CalculadoraFrete calculadoraFrete;

    public Pedido(double valor) {
        this.valor = valor;
    }

    public void setCalculadoraFrete(CalculadoraFrete calculadoraFrete) {
        this.calculadoraFrete = calculadoraFrete;
    }

    public double calcularValorTotal() {
        if (calculadoraFrete == null) {
            throw new IllegalStateException("Calculadora de frete não configurada");
        }

        return valor + calculadoraFrete.calcular(valor);
    }
}
```

#### Uso

```java
Pedido pedido = new Pedido(100.0);

pedido.setCalculadoraFrete(new FreteComum());
System.out.println(pedido.calcularValorTotal());

pedido.setCalculadoraFrete(new FreteExpresso());
System.out.println(pedido.calcularValorTotal());

pedido.setCalculadoraFrete(new RetiradaNaLoja());
System.out.println(pedido.calcularValorTotal());
```

Esse exemplo mostra bem o Strategy porque o método “calcular frete” tem diferentes estratégias.

---

### Exemplo 3 — Notificações

Um sistema pode precisar notificar usuários de várias formas:

- e-mail;
- SMS;
- WhatsApp;
- notificação interna no sistema.

Cada canal de notificação pode ser uma estratégia.

#### Interface

```java
interface Notificador {
    void notificar(String destinatario, String mensagem);
}
```

#### Estratégia de e-mail

```java
class NotificadorEmail implements Notificador {
    public void notificar(String destinatario, String mensagem) {
        System.out.println("Enviando e-mail para " + destinatario);
    }
}
```

#### Estratégia de SMS

```java
class NotificadorSMS implements Notificador {
    public void notificar(String destinatario, String mensagem) {
        System.out.println("Enviando SMS para " + destinatario);
    }
}
```

#### Estratégia de WhatsApp

```java
class NotificadorWhatsApp implements Notificador {
    public void notificar(String destinatario, String mensagem) {
        System.out.println("Enviando WhatsApp para " + destinatario);
    }
}
```

#### Classe que usa a estratégia

```java
class ServicoDeAviso {
    private Notificador notificador;

    public ServicoDeAviso(Notificador notificador) {
        this.notificador = notificador;
    }

    public void enviarAviso(String destinatario, String mensagem) {
        notificador.notificar(destinatario, mensagem);
    }
}
```

#### Uso

```java
ServicoDeAviso avisoPorEmail = new ServicoDeAviso(new NotificadorEmail());
avisoPorEmail.enviarAviso("aluno@email.com", "Sua atividade foi corrigida.");

ServicoDeAviso avisoPorSMS = new ServicoDeAviso(new NotificadorSMS());
avisoPorSMS.enviarAviso("83999999999", "Sua atividade foi corrigida.");
```

O serviço de aviso não precisa conhecer os detalhes de envio por e-mail, SMS ou WhatsApp. Ele depende apenas da interface `Notificador`.

---

### Exemplo 4 — Cálculo de salário

Um sistema de folha de pagamento pode calcular salários de formas diferentes:

- funcionário mensalista;
- vendedor com comissão;
- funcionário horista;
- funcionário com adicional de insalubridade.

Cada regra pode ser uma estratégia.

#### Interface

```java
interface CalculadoraSalario {
    double calcular(Funcionario funcionario);
}
```

#### Funcionário

```java
class Funcionario {
    private String nome;
    private double salarioBase;
    private double vendas;
    private int horasTrabalhadas;

    public Funcionario(String nome, double salarioBase) {
        this.nome = nome;
        this.salarioBase = salarioBase;
    }

    public double getSalarioBase() {
        return salarioBase;
    }

    public double getVendas() {
        return vendas;
    }

    public int getHorasTrabalhadas() {
        return horasTrabalhadas;
    }
}
```

#### Estratégia para mensalista

```java
class SalarioMensalista implements CalculadoraSalario {
    public double calcular(Funcionario funcionario) {
        return funcionario.getSalarioBase();
    }
}
```

#### Estratégia para vendedor

```java
class SalarioVendedor implements CalculadoraSalario {
    public double calcular(Funcionario funcionario) {
        return funcionario.getSalarioBase() + funcionario.getVendas() * 0.10;
    }
}
```

#### Estratégia com adicional

```java
class SalarioComInsalubridade implements CalculadoraSalario {
    public double calcular(Funcionario funcionario) {
        return funcionario.getSalarioBase() * 1.20;
    }
}
```

Nesse caso, o cálculo do salário varia. O Strategy permite isolar cada regra em uma classe própria.

---

### Exemplo 5 — Ordenação de dados

Um sistema pode exibir uma lista de produtos com diferentes critérios de ordenação:

- menor preço;
- maior preço;
- nome em ordem alfabética;
- produtos mais recentes.

Cada forma de ordenação pode ser uma estratégia.

#### Interface

```java
interface OrdenadorProduto {
    void ordenar(List<Produto> produtos);
}
```

#### Estratégia por menor preço

```java
class OrdenarPorMenorPreco implements OrdenadorProduto {
    public void ordenar(List<Produto> produtos) {
        produtos.sort((p1, p2) -> Double.compare(p1.getPreco(), p2.getPreco()));
    }
}
```

#### Estratégia por nome

```java
class OrdenarPorNome implements OrdenadorProduto {
    public void ordenar(List<Produto> produtos) {
        produtos.sort((p1, p2) -> p1.getNome().compareTo(p2.getNome()));
    }
}
```

Esse exemplo mostra que Strategy não serve apenas para persistência. Ele serve para qualquer comportamento que possa variar.

---

### Exemplo 6 — Autorização em um sistema

Nos projetos da disciplina, há requisito de autenticação e autorização.

Um exemplo possível de Strategy seria a verificação de permissão de usuários.

Imagine que diferentes perfis tenham regras diferentes:

- aluno;
- professor;
- administrador.

Cada regra de autorização pode ser uma estratégia.

#### Interface

```java
interface RegraAutorizacao {
    boolean podeAcessar(Usuario usuario, String recurso);
}
```

#### Estratégia para aluno

```java
class AutorizacaoAluno implements RegraAutorizacao {
    public boolean podeAcessar(Usuario usuario, String recurso) {
        return recurso.equals("visualizar_proprios_dados");
    }
}
```

#### Estratégia para professor

```java
class AutorizacaoProfessor implements RegraAutorizacao {
    public boolean podeAcessar(Usuario usuario, String recurso) {
        return recurso.equals("visualizar_turma") || recurso.equals("lancar_nota");
    }
}
```

#### Estratégia para administrador

```java
class AutorizacaoAdministrador implements RegraAutorizacao {
    public boolean podeAcessar(Usuario usuario, String recurso) {
        return true;
    }
}
```

Aqui, o comportamento variável é a regra de autorização.

---

### Como identificar oportunidade de usar Strategy

Uma boa pergunta para identificar Strategy é:

> Existe uma ação no sistema que pode ser feita de várias formas diferentes?

Outra pergunta útil:

> Estou usando vários `if`, `else if` ou `switch` para escolher uma forma de executar um comportamento?

Sinais de que Strategy pode ser útil:

- muitos condicionais escolhendo algoritmo;
- comportamento que muda conforme tipo, perfil ou configuração;
- necessidade de trocar uma regra em tempo de execução;
- possibilidade de adicionar novas regras no futuro;
- classe principal ficando grande demais por conter várias variações de uma mesma ação.

---

### Quando Strategy pode ser exagero

Strategy pode ser exagero quando:

- só existe uma implementação;
- não há previsão real de variação;
- a lógica é muito pequena e não tende a crescer;
- a criação de várias classes deixa o código mais difícil de entender;
- o padrão é usado apenas para “parecer avançado”.

No projeto da disciplina, a aplicação pode ser pedagógica. Mas, em projetos reais, o uso deve ser justificado por uma necessidade de manutenção, extensão ou organização.

---

## Seção ampliada — Composite

## Padrão Composite

### Ideia central do Composite

O padrão **Composite** é usado quando precisamos representar objetos que podem ser formados por outros objetos.

A palavra “composite” remete a algo **composto**, isto é, algo formado por partes.

A ideia central é:

> Tratar objetos simples e objetos compostos de maneira uniforme por meio de uma interface comum.

Em outras palavras, o código cliente não precisa saber se está lidando com um objeto individual ou com um conjunto de objetos.

---

### Problema que o Composite resolve

Imagine uma estrutura em que um objeto pode conter outros objetos.

Exemplos:

- uma pasta contém arquivos e outras pastas;
- um menu contém itens e submenus;
- uma rede contém roteadores, switches, computadores e outros dispositivos;
- uma organização contém setores, equipes e pessoas;
- uma tela contém painéis, botões, campos e outros componentes.

Sem Composite, uma classe composta pode acabar conhecendo todos os tipos concretos que ela pode conter.

Exemplo ruim:

```java
class Pasta {
    void adicionarArquivo(Arquivo arquivo) { }
    void adicionarImagem(Imagem imagem) { }
    void adicionarVideo(Video video) { }
    void adicionarOutraPasta(Pasta pasta) { }
}
```

Esse projeto tem um problema:

- a classe `Pasta` conhece vários tipos concretos;
- a cada novo tipo de item, `Pasta` precisa mudar;
- o código fica muito acoplado;
- fica difícil tratar arquivos e pastas de forma uniforme.

O Composite resolve isso criando uma interface comum para todos os elementos.

---

### Estrutura básica do Composite

O Composite normalmente envolve três papéis:

- **Component**: interface comum para objetos simples e compostos.
- **Leaf**: objeto simples, que não possui filhos.
- **Composite**: objeto composto, que possui uma coleção de componentes.

No exemplo de rede da aula:

- Component: `ComponenteDeRede`;
- Leaf: `Computador`, `Celular`;
- Composite: `Roteador`, `Switch`, `AccessPoint`.

---

### Exemplo 1 — Rede de computadores

No exemplo da aula, uma rede possui vários componentes:

- roteador;
- switch;
- access point;
- computador;
- celular;
- servidor.

Alguns componentes podem conter outros:

- roteador pode conter switch, computador, access point;
- switch pode conter computador, servidor, access point;
- access point pode conter celular.

A solução com Composite cria uma interface comum.

#### Interface Component

```java
interface ComponenteDeRede {
    String getIP();
    String getMAC();
    boolean up();
}
```

#### Classe Composite

```java
class ComponenteDeRedeComposto implements ComponenteDeRede {
    private List<ComponenteDeRede> componentes = new ArrayList<>();

    public void addComponente(ComponenteDeRede componente) {
        componentes.add(componente);
    }

    public void removerComponente(ComponenteDeRede componente) {
        componentes.remove(componente);
    }

    public boolean up() {
        for (ComponenteDeRede componente : componentes) {
            if (!componente.up()) {
                return false;
            }
        }

        return true;
    }

    public String getIP() {
        return "";
    }

    public String getMAC() {
        return "";
    }
}
```

#### Objetos compostos

```java
class Roteador extends ComponenteDeRedeComposto {
}

class Switch extends ComponenteDeRedeComposto {
}

class AccessPoint extends ComponenteDeRedeComposto {
}
```

#### Objetos simples

```java
class Computador implements ComponenteDeRede {
    public String getIP() {
        return "10.0.1.10";
    }

    public String getMAC() {
        return "AA-BB-CC-DD-EE-01";
    }

    public boolean up() {
        return true;
    }
}

class Celular implements ComponenteDeRede {
    public String getIP() {
        return "10.0.1.20";
    }

    public String getMAC() {
        return "AA-BB-CC-DD-EE-02";
    }

    public boolean up() {
        return true;
    }
}
```

#### Uso

```java
Roteador roteador = new Roteador();
Switch sw = new Switch();
AccessPoint ap = new AccessPoint();

Computador computador = new Computador();
Celular celular = new Celular();

roteador.addComponente(sw);
roteador.addComponente(ap);
sw.addComponente(computador);
ap.addComponente(celular);

System.out.println(roteador.up());
```

O roteador não precisa saber se recebeu um switch, computador, celular ou access point.

Ele sabe apenas que recebeu um `ComponenteDeRede`.

---

### Exemplo 2 — Pastas e arquivos

Esse é um dos exemplos mais comuns de Composite.

Uma pasta pode conter:

- arquivos;
- outras pastas.

Um arquivo é um componente simples.

Uma pasta é um componente composto.

#### Interface Component

```java
interface ItemSistemaArquivos {
    String getNome();
    int getTamanho();
    void exibir();
}
```

#### Leaf: Arquivo

```java
class Arquivo implements ItemSistemaArquivos {
    private String nome;
    private int tamanho;

    public Arquivo(String nome, int tamanho) {
        this.nome = nome;
        this.tamanho = tamanho;
    }

    public String getNome() {
        return nome;
    }

    public int getTamanho() {
        return tamanho;
    }

    public void exibir() {
        System.out.println("Arquivo: " + nome);
    }
}
```

#### Composite: Pasta

```java
class Pasta implements ItemSistemaArquivos {
    private String nome;
    private List<ItemSistemaArquivos> itens = new ArrayList<>();

    public Pasta(String nome) {
        this.nome = nome;
    }

    public void adicionar(ItemSistemaArquivos item) {
        itens.add(item);
    }

    public String getNome() {
        return nome;
    }

    public int getTamanho() {
        int total = 0;

        for (ItemSistemaArquivos item : itens) {
            total += item.getTamanho();
        }

        return total;
    }

    public void exibir() {
        System.out.println("Pasta: " + nome);

        for (ItemSistemaArquivos item : itens) {
            item.exibir();
        }
    }
}
```

#### Uso

```java
Pasta raiz = new Pasta("raiz");
Pasta documentos = new Pasta("documentos");

Arquivo a1 = new Arquivo("aula.txt", 10);
Arquivo a2 = new Arquivo("projeto.pdf", 50);

documentos.adicionar(a1);
documentos.adicionar(a2);

raiz.adicionar(documentos);
raiz.adicionar(new Arquivo("README.md", 5));

System.out.println(raiz.getTamanho());
raiz.exibir();
```

Nesse exemplo:

- `Arquivo` é simples;
- `Pasta` é composta;
- tanto `Arquivo` quanto `Pasta` são tratados como `ItemSistemaArquivos`.

A chamada `getTamanho()` funciona tanto para arquivo quanto para pasta.

No arquivo, retorna o tamanho do arquivo.

Na pasta, soma o tamanho de todos os itens internos.

---

### Exemplo 3 — Menu com submenus

Um sistema web pode ter menus e submenus.

Um item de menu simples executa uma ação.

Um submenu contém outros itens.

#### Interface

```java
interface ItemMenu {
    void exibir();
}
```

#### Leaf: item simples

```java
class LinkMenu implements ItemMenu {
    private String titulo;
    private String url;

    public LinkMenu(String titulo, String url) {
        this.titulo = titulo;
        this.url = url;
    }

    public void exibir() {
        System.out.println(titulo + " -> " + url);
    }
}
```

#### Composite: submenu

```java
class Submenu implements ItemMenu {
    private String titulo;
    private List<ItemMenu> itens = new ArrayList<>();

    public Submenu(String titulo) {
        this.titulo = titulo;
    }

    public void adicionar(ItemMenu item) {
        itens.add(item);
    }

    public void exibir() {
        System.out.println("Submenu: " + titulo);

        for (ItemMenu item : itens) {
            item.exibir();
        }
    }
}
```

#### Uso

```java
Submenu menuPrincipal = new Submenu("Principal");

menuPrincipal.adicionar(new LinkMenu("Início", "/"));
menuPrincipal.adicionar(new LinkMenu("Login", "/login"));

Submenu menuAdmin = new Submenu("Administração");
menuAdmin.adicionar(new LinkMenu("Usuários", "/usuarios"));
menuAdmin.adicionar(new LinkMenu("Relatórios", "/relatorios"));

menuPrincipal.adicionar(menuAdmin);

menuPrincipal.exibir();
```

Nesse caso, o menu principal trata links simples e submenus da mesma forma.

---

### Exemplo 4 — Organização com setores, equipes e pessoas

Uma organização pode ter:

- empresa;
- setores;
- equipes;
- pessoas.

Uma pessoa é um componente simples.

Um setor ou equipe pode ser composto por várias pessoas ou outras equipes.

#### Interface

```java
interface UnidadeOrganizacional {
    String getNome();
    int getQuantidadePessoas();
}
```

#### Leaf: pessoa

```java
class Pessoa implements UnidadeOrganizacional {
    private String nome;

    public Pessoa(String nome) {
        this.nome = nome;
    }

    public String getNome() {
        return nome;
    }

    public int getQuantidadePessoas() {
        return 1;
    }
}
```

#### Composite: setor

```java
class Setor implements UnidadeOrganizacional {
    private String nome;
    private List<UnidadeOrganizacional> unidades = new ArrayList<>();

    public Setor(String nome) {
        this.nome = nome;
    }

    public void adicionar(UnidadeOrganizacional unidade) {
        unidades.add(unidade);
    }

    public String getNome() {
        return nome;
    }

    public int getQuantidadePessoas() {
        int total = 0;

        for (UnidadeOrganizacional unidade : unidades) {
            total += unidade.getQuantidadePessoas();
        }

        return total;
    }
}
```

#### Uso

```java
Setor empresa = new Setor("Empresa");
Setor desenvolvimento = new Setor("Desenvolvimento");
Setor suporte = new Setor("Suporte");

desenvolvimento.adicionar(new Pessoa("Pessoa 1"));
desenvolvimento.adicionar(new Pessoa("Pessoa 2"));

suporte.adicionar(new Pessoa("Pessoa 3"));

empresa.adicionar(desenvolvimento);
empresa.adicionar(suporte);

System.out.println(empresa.getQuantidadePessoas());
```

Esse exemplo mostra a ideia de árvore:

- empresa contém setores;
- setores contêm pessoas;
- setores também poderiam conter equipes;
- tudo é tratado como `UnidadeOrganizacional`.

---

### Exemplo 5 — Interface gráfica

Em interfaces gráficas, uma tela pode conter vários componentes:

- painel;
- botão;
- campo de texto;
- tabela;
- outro painel.

Um botão é simples.

Um painel é composto, porque pode conter outros componentes.

#### Interface

```java
interface ComponenteVisual {
    void desenhar();
}
```

#### Leaf: botão

```java
class Botao implements ComponenteVisual {
    private String texto;

    public Botao(String texto) {
        this.texto = texto;
    }

    public void desenhar() {
        System.out.println("Desenhando botão: " + texto);
    }
}
```

#### Leaf: campo de texto

```java
class CampoTexto implements ComponenteVisual {
    private String nome;

    public CampoTexto(String nome) {
        this.nome = nome;
    }

    public void desenhar() {
        System.out.println("Desenhando campo de texto: " + nome);
    }
}
```

#### Composite: painel

```java
class Painel implements ComponenteVisual {
    private List<ComponenteVisual> componentes = new ArrayList<>();

    public void adicionar(ComponenteVisual componente) {
        componentes.add(componente);
    }

    public void desenhar() {
        System.out.println("Desenhando painel");

        for (ComponenteVisual componente : componentes) {
            componente.desenhar();
        }
    }
}
```

#### Uso

```java
Painel tela = new Painel();

tela.adicionar(new CampoTexto("email"));
tela.adicionar(new CampoTexto("senha"));
tela.adicionar(new Botao("Entrar"));

Painel painelInterno = new Painel();
painelInterno.adicionar(new Botao("Ajuda"));
painelInterno.adicionar(new Botao("Cancelar"));

tela.adicionar(painelInterno);

tela.desenhar();
```

Esse exemplo mostra que o Composite é muito útil para estruturas hierárquicas.

Uma tela pode conter painéis, que contêm outros componentes, que podem conter outros painéis, e assim por diante.

---

### Exemplo 6 — Tarefas e subtarefas

Em um sistema de gerenciamento de projetos, uma tarefa pode ser simples ou composta por subtarefas.

Exemplos:

- “Implementar login” pode ter subtarefas:
  - criar tela de login;
  - validar usuário;
  - criar sessão;
  - testar autenticação.

Uma subtarefa também poderia ter outras subtarefas.

#### Interface

```java
interface ItemTrabalho {
    String getDescricao();
    int getHorasEstimadas();
}
```

#### Leaf: tarefa simples

```java
class TarefaSimples implements ItemTrabalho {
    private String descricao;
    private int horasEstimadas;

    public TarefaSimples(String descricao, int horasEstimadas) {
        this.descricao = descricao;
        this.horasEstimadas = horasEstimadas;
    }

    public String getDescricao() {
        return descricao;
    }

    public int getHorasEstimadas() {
        return horasEstimadas;
    }
}
```

#### Composite: tarefa composta

```java
class TarefaComposta implements ItemTrabalho {
    private String descricao;
    private List<ItemTrabalho> itens = new ArrayList<>();

    public TarefaComposta(String descricao) {
        this.descricao = descricao;
    }

    public void adicionar(ItemTrabalho item) {
        itens.add(item);
    }

    public String getDescricao() {
        return descricao;
    }

    public int getHorasEstimadas() {
        int total = 0;

        for (ItemTrabalho item : itens) {
            total += item.getHorasEstimadas();
        }

        return total;
    }
}
```

#### Uso

```java
TarefaComposta login = new TarefaComposta("Implementar login");

login.adicionar(new TarefaSimples("Criar tela de login", 2));
login.adicionar(new TarefaSimples("Validar usuário", 3));
login.adicionar(new TarefaSimples("Criar sessão", 2));
login.adicionar(new TarefaSimples("Testar autenticação", 2));

System.out.println(login.getHorasEstimadas());
```

Nesse exemplo, a tarefa composta calcula suas horas somando as horas das subtarefas.

---

### Como identificar oportunidade de usar Composite

Uma boa pergunta para identificar Composite é:

> Tenho objetos que podem conter outros objetos do mesmo tipo abstrato?

Outra pergunta:

> Preciso tratar um item individual e um grupo de itens da mesma forma?

Sinais de que Composite pode ser útil:

- estrutura em árvore;
- objetos contendo outros objetos;
- necessidade de somar, listar, exibir ou validar recursivamente;
- muitos métodos específicos para adicionar tipos diferentes;
- classes compostas acopladas a várias classes concretas;
- necessidade de tratar parte e todo de maneira uniforme.

---

### Composite e estruturas em árvore

O Composite é muito comum em estruturas parecidas com árvores.

Exemplo de árvore de arquivos:

- Pasta raiz
  - Arquivo A
  - Pasta documentos
    - Arquivo B
    - Arquivo C
  - Pasta imagens
    - Arquivo D

A pasta raiz contém arquivos e outras pastas.

Cada pasta pode conter arquivos e outras pastas.

Isso forma uma estrutura recursiva.

O Composite permite representar essa estrutura porque o composto armazena uma lista de componentes da própria interface comum.

Exemplo:

```java
private List<ItemSistemaArquivos> itens;
```

A lista pode conter tanto arquivos quanto pastas, porque ambos implementam `ItemSistemaArquivos`.

---

### Cuidado: nem toda relação “tem um” precisa de Composite

Composite não deve ser usado em qualquer relação de composição.

Por exemplo:

```java
class Pedido {
    private Cliente cliente;
    private Endereco enderecoEntrega;
}
```

Esse é um caso em que `Pedido` tem um `Cliente` e um `Endereco`, mas isso não significa que devemos usar Composite.

Composite é mais adequado quando:

- os elementos têm uma interface comum;
- objetos simples e compostos precisam ser tratados da mesma forma;
- há uma estrutura hierárquica ou recursiva;
- um objeto composto contém uma coleção de componentes.

No exemplo do pedido, `Cliente` e `Endereco` não são tratados como o mesmo tipo abstrato de `Pedido`.

Portanto, não é um caso típico de Composite.

---

### Composite e recursão

Composite frequentemente leva a operações recursivas.

No exemplo da pasta:

```java
public int getTamanho() {
    int total = 0;

    for (ItemSistemaArquivos item : itens) {
        total += item.getTamanho();
    }

    return total;
}
```

Se o item for um arquivo, retorna o tamanho do arquivo.

Se o item for uma pasta, ela também calcula o tamanho de seus itens internos.

Assim, a chamada pode se repetir por vários níveis da árvore.

---

### Quando Composite pode ser exagero

Composite pode ser exagero quando:

- não há estrutura hierárquica;
- o objeto não precisa conter outros objetos do mesmo tipo abstrato;
- os objetos simples e compostos não precisam ser tratados da mesma forma;
- a solução com uma lista simples já resolve;
- a abstração criada torna o código mais difícil de entender.

No projeto da disciplina, pode ser usado pedagogicamente. Mas, em sistemas reais, deve ser usado quando há uma necessidade clara de representar estruturas compostas.

---

## Comparação ampliada entre Strategy e Composite

### Diferença principal

O **Strategy** trata variação de comportamento.

O **Composite** trata composição de objetos.

Em forma simples:

| Padrão | Problema principal | Ideia central |
|---|---|---|
| Strategy | Uma ação pode ser feita de várias formas | Encapsular cada forma em uma estratégia |
| Composite | Um objeto pode ser composto por outros objetos | Tratar objetos simples e compostos de forma uniforme |

---

### Exemplo comparativo

Imagine um sistema acadêmico.

#### Possível uso de Strategy

O sistema precisa calcular a situação final de um aluno.

A regra pode variar:

- média simples;
- média ponderada;
- regra com prova final;
- regra com recuperação.

Isso é Strategy, porque há diferentes formas de executar o mesmo comportamento: calcular resultado.

#### Possível uso de Composite

O sistema precisa representar a estrutura curricular:

- curso;
- períodos;
- disciplinas;
- módulos;
- atividades.

Se alguns elementos podem conter outros elementos e todos precisam ser tratados como componentes da estrutura curricular, pode haver uma oportunidade de Composite.

---

### Outro exemplo comparativo

Imagine um sistema de loja virtual.

#### Possível uso de Strategy

Calcular desconto:

- desconto por cupom;
- desconto por fidelidade;
- desconto por campanha;
- desconto progressivo.

Isso é Strategy.

#### Possível uso de Composite

Representar categorias de produtos:

- categoria principal;
- subcategoria;
- produto.

Se categorias podem conter subcategorias e produtos, e o sistema precisa percorrer essa estrutura, pode haver Composite.

---

### Mais um exemplo comparativo

Imagine um sistema de tarefas.

#### Possível uso de Strategy

Ordenar tarefas:

- por prazo;
- por prioridade;
- por responsável;
- por status.

Isso é Strategy.

#### Possível uso de Composite

Representar tarefas e subtarefas:

- tarefa principal;
- subtarefas;
- subtarefas das subtarefas.

Isso é Composite.

---

## Perguntas práticas para escolher entre Strategy e Composite

### Perguntas que indicam Strategy

- Tenho uma ação que pode ser executada de formas diferentes?
- Estou escolhendo comportamento com `if`, `else` ou `switch`?
- Posso trocar a regra sem alterar a classe principal?
- Cada variação da regra poderia virar uma classe separada?
- O problema é variação de algoritmo ou comportamento?

### Perguntas que indicam Composite

- Tenho objetos que contêm outros objetos?
- Tenho uma estrutura de árvore?
- Preciso tratar um item individual e um grupo da mesma forma?
- O objeto composto deveria depender apenas de uma interface comum?
- O problema é representar uma relação parte-todo?

---

## Exemplos possíveis nos projetos da disciplina

### Possíveis aplicações de Strategy

Em projetos da disciplina, o Strategy pode aparecer em situações como:

- diferentes formas de validar um cadastro;
- diferentes formas de calcular uma pontuação;
- diferentes formas de gerar relatório;
- diferentes formas de exportar dados;
- diferentes formas de notificar usuários;
- diferentes formas de autenticar usuários;
- diferentes regras de autorização por perfil;
- diferentes formas de ordenar ou filtrar resultados;
- diferentes formas de calcular status de uma entidade.

Exemplo:

> Se um sistema possui usuários com perfis diferentes e cada perfil tem uma regra diferente para acessar funcionalidades, pode-se modelar cada regra como uma estratégia de autorização.

---

### Possíveis aplicações de Composite

Em projetos da disciplina, o Composite pode aparecer em situações como:

- categorias e subcategorias;
- comentários e respostas a comentários;
- tarefas e subtarefas;
- módulos e aulas;
- menus e submenus;
- pastas e arquivos;
- grupos e subgrupos;
- estruturas de permissões hierárquicas;
- componentes de interface organizados em árvore;
- projetos compostos por etapas, que contêm atividades.

Exemplo:

> Se um sistema possui tarefas que podem conter subtarefas, e subtarefas também podem conter outras subtarefas, o Composite pode ser usado para tratar tarefa simples e tarefa composta de forma uniforme.

---

## Síntese final

O Strategy e o Composite usam interfaces e polimorfismo, mas resolvem problemas diferentes.

O **Strategy** deve ser lembrado como o padrão das **variações de comportamento**.

O **Composite** deve ser lembrado como o padrão das **estruturas compostas**, especialmente estruturas em árvore.

Em ambos os casos, a interface reduz o acoplamento com classes concretas.

Mas o papel da interface é diferente:

- no Strategy, a interface representa uma família de estratégias;
- no Composite, a interface representa um componente comum para objetos simples e compostos.

A principal competência não é decorar o código dos padrões, mas reconhecer o tipo de problema que cada padrão resolve.
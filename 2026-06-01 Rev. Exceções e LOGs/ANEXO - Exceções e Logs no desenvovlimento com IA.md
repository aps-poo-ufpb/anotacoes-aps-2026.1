Por prof. Rodrigo Rebouças (https://rodrigor.com)
## Erros, Exceções e Desenvolvimento Utilizando IA

Ferramentas de programação com IA, como assistentes de código e agentes de desenvolvimento, podem acelerar bastante a implementação de sistemas. Porém, elas tendem a gerar soluções que funcionam bem no **caminho feliz**, isto é, quando tudo acontece como esperado.

Por isso, ao usar IA no desenvolvimento, é importante orientar explicitamente a ferramenta sobre:

- validações;
- regras de negócio;
- falhas técnicas;
- exceções;
- logs;
- testes de erro;
- mensagens para o usuário;
- respostas HTTP;
- segurança dos dados.

O tratamento de erros se torna uma parte essencial da comunicação com a IA.

---

### O Que é o Caminho Feliz?

O caminho feliz é o fluxo em que tudo dá certo.

Exemplo:

1. usuário preenche os dados corretamente;
2. front-end envia a requisição;
3. controller recebe os dados;
4. service executa a regra de negócio;
5. repository salva no banco;
6. sistema retorna sucesso.

Exemplo de resposta:

```http
HTTP/1.1 201 Created
```

O problema é que sistemas reais também precisam lidar com caminhos alternativos:

- usuário envia dados inválidos;
- regra de negócio impede a operação;
- banco de dados está indisponível;
- arquivo não pode ser gravado;
- serviço externo falha;
- objeto chega nulo;
- exceção inesperada ocorre.

Ao pedir código para uma IA, é necessário solicitar também esses cenários.

---

### A IA Precisa Ser Orientada Sobre os Caminhos de Erro

Um pedido genérico como:

```text
Implemente o cadastro de usuário.
```

pode gerar uma solução incompleta.

Um pedido melhor seria:

```text
Implemente o cadastro de usuário considerando:
- validação de entrada no back-end;
- erro de e-mail já cadastrado;
- falha de persistência;
- logs adequados;
- mensagens amigáveis para o usuário;
- respostas HTTP adequadas;
- preservação da causa original das exceções;
- testes para os cenários de erro.
```

Esse tipo de prompt reduz a chance de a IA gerar apenas o fluxo principal.

---

### Separar Tipos de Erro Antes de Pedir Código

Antes de pedir uma implementação, é útil classificar os erros possíveis.

| Tipo de situação | Exemplo | Tratamento esperado |
|---|---|---|
| Entrada inválida | campo obrigatório ausente, idade negativa | retornar 400 ou 422 |
| Regra de negócio violada | aluno sem pré-requisito | retornar 409 ou 422 |
| Falha técnica | banco caiu, arquivo inacessível | registrar log e retornar 500 |
| Bug interno | objeto nulo, índice inválido | registrar log, retornar 500 e corrigir a causa |

Essa classificação ajuda a IA a produzir código mais organizado.

---

### Exemplo de Prompt Para Classificar Erros

```text
Analise este caso de uso e classifique os possíveis erros em:
1. erros de validação;
2. violações de regra de negócio;
3. falhas técnicas;
4. bugs internos.

Para cada erro, indique:
- onde ele deve ser tratado;
- qual exceção pode representar o problema;
- qual status HTTP deve ser retornado;
- qual mensagem pode ser exibida ao usuário;
- qual informação deve ir para o log.
```

Esse prompt pode ser usado antes da implementação.

---

### Definir um Contrato de Erros Para a IA

Ao implementar endpoints, é importante especificar o contrato de respostas.

Exemplo para um endpoint de matrícula:

```text
Para o endpoint POST /matriculas, use o seguinte contrato:

- 201: matrícula criada com sucesso;
- 400: JSON inválido ou campos obrigatórios ausentes;
- 409: aluno já matriculado na turma;
- 422: aluno não cumpriu os pré-requisitos;
- 500: falha interna inesperada.

Implemente controller, service e repository respeitando esse contrato.
Não exponha mensagens técnicas ao usuário.
Registre logs nos erros técnicos.
Preserve a causa original das exceções.
```

Com isso, a IA recebe limites claros e tende a gerar uma solução mais consistente.

---

### Evitar Que a IA Esconda Bugs

Um risco comum é a IA gerar código que captura exceções e não faz nada.

Exemplo ruim:

```java
try {
    usuarioRepository.salvar(usuario);
} catch (Exception e) {
    return false;
}
```

Exemplo ainda pior:

```python
try:
    processar()
except Exception:
    pass
```

Esse tipo de código esconde o problema. A operação falha, mas o sistema não registra o erro adequadamente e não deixa claro o que aconteceu.

Prompt recomendado:

```text
Não engula exceções.
Se uma exceção for capturada:
- registre log adequado;
- preserve a causa original;
- retorne uma resposta coerente; ou
- relance uma exceção mais específica.
Nunca use catch vazio ou except pass.
```

---

### Não Mascarar Sintomas

Outro risco é a IA corrigir apenas o sintoma do erro.

Exemplo: ocorre uma `NullPointerException`, e a IA sugere apenas:

```java
if (usuario != null) {
    usuario.atualizar();
}
```

Esse código pode evitar a exceção naquele ponto, mas não responde à pergunta principal:

> Por que `usuario` chegou nulo?

Em muitos casos, o correto é investigar a origem do problema.

Prompt recomendado:

```text
Não apenas evite a exceção com um if defensivo.
Investigue por que o objeto chegou nulo.
Explique a causa provável e proponha uma correção na origem do problema.
```

---

### Pedir Exceções Específicas Por Camada

A IA pode gerar exceções genéricas demais, como `RuntimeException`, `Exception` ou `Error`.

É melhor orientar a criação de exceções compatíveis com a arquitetura.

Exemplo de prompt:

```text
Crie exceções específicas para as camadas da aplicação:

- RepositoryException para falhas de persistência;
- ServiceException para falhas técnicas da camada de serviço;
- exceções de domínio para regras de negócio violadas.

Não propague IOException, SQLException ou exceções específicas de infraestrutura diretamente para o controller.
Encapsule exceções de baixo nível em exceções adequadas à camada.
```

Esse cuidado reduz acoplamento entre as camadas.

---

### Preservar a Causa Original da Exceção

Ao encapsular exceções, a causa original não deve ser perdida.

Em Java:

```java
try {
    repository.salvar(usuario);
} catch (IOException e) {
    throw new UsuarioRepositoryException("Erro ao salvar usuário", e);
}
```

Em Python:

```python
try:
    repository.salvar(usuario)
except OSError as error:
    raise UsuarioRepositoryError("Erro ao salvar usuário") from error
```

A IA deve ser orientada a preservar essa cadeia de erros.

Prompt recomendado:

```text
Ao encapsular exceções, preserve sempre a causa original.
Em Java, passe a exceção original como causa no construtor.
Em Python, use raise NovaExcecao(...) from error.
```

---

### Separar Mensagem Técnica de Mensagem Para Usuário

A IA pode gerar código que retorna a mensagem técnica diretamente ao usuário.

Exemplo ruim:

```java
ctx.status(500).result(exception.getMessage());
```

Isso pode expor detalhes internos.

Exemplo melhor:

```java
logger.error("Erro ao cadastrar usuário", exception);

ctx.status(500).result("Não foi possível concluir a operação. Tente novamente mais tarde.");
```

Prompt recomendado:

```text
Não retorne exception.getMessage() diretamente ao usuário.
Use mensagens técnicas apenas no log.
Para o usuário, retorne mensagens amigáveis, seguras e adequadas ao contexto.
```

---

### Orientar a IA Sobre Logging

Ao gerar código, a IA deve ser instruída a usar logs adequadamente.

Prompt recomendado:

```text
Implemente logging seguindo estas regras:

- use debug para informações úteis durante desenvolvimento;
- use info para eventos relevantes do fluxo normal;
- use warn para situações suspeitas, mas recuperáveis;
- use error para falhas que impedem a operação;
- não registre senhas, tokens, chaves de API ou dados sensíveis;
- inclua contexto suficiente para investigação;
- preserve o stack trace nas falhas técnicas.
```

Isso ajuda a evitar tanto a ausência de logs quanto o excesso de logs inúteis.

---

### Evitar Vazamento de Dados Sensíveis

A IA pode sugerir logs perigosos.

Exemplo ruim:

```java
logger.debug("Senha recebida: {}", senha);
```

Exemplo ruim em Python:

```python
logger.info(f"Token do usuário: {token}")
```

Exemplo melhor:

```java
logger.debug("Senha foi preenchida: {}", senha != null && !senha.isBlank());
```

Prompt recomendado:

```text
Não registre dados sensíveis em logs.
Evite senhas, tokens, chaves de API, documentos pessoais, cartões, dados financeiros ou informações sigilosas.
Quando necessário, use dados mascarados ou apenas identificadores técnicos.
```

---

### Pedir Testes Para Caminhos de Erro

A IA costuma gerar testes apenas para o caminho feliz.

É importante pedir testes para falhas.

Prompt recomendado:

```text
Gere testes automatizados cobrindo:
- operação realizada com sucesso;
- campos obrigatórios ausentes;
- dados em formato inválido;
- violação de regra de negócio;
- repository lançando exceção;
- resposta HTTP 500;
- preservação da causa original da exceção;
- ausência de vazamento de mensagem técnica ao usuário.
```

Os testes ajudam a verificar se o tratamento de erros realmente funciona.

---

### Usar Logs e Stack Traces Como Insumo Para a IA

Quando um erro acontece, o log e o stack trace podem ser enviados à IA para análise.

Prompt recomendado:

```text
Analise este stack trace e este trecho de log.

Identifique:
1. a exceção de alto nível;
2. a causa raiz;
3. a camada onde o erro nasceu;
4. a camada onde o erro deveria ser tratado;
5. se a exceção foi encapsulada corretamente;
6. se há vazamento de detalhe técnico;
7. uma proposta de correção.
```

Esse uso da IA é especialmente útil para depuração e revisão de código.

---

### Revisar Código Gerado Pela IA

O tratamento de erros deve fazer parte da revisão do código gerado.

Checklist de revisão:

- Há validação no back-end?
- Há tratamento para violação de regra de negócio?
- Há tratamento para falhas técnicas?
- Há `catch` ou `except` vazio?
- Exceções genéricas estão sendo usadas sem necessidade?
- A causa original da exceção foi preservada?
- O sistema registra log adequado?
- O usuário recebe mensagem amigável?
- O status HTTP está correto?
- Algum dado sensível está sendo registrado?
- O código está escondendo bug?
- Há testes para os cenários de erro?

Prompt recomendado:

```text
Revise este código com foco em tratamento de erros.

Procure:
- exceções genéricas demais;
- catch vazio;
- perda da causa original;
- falta de log;
- log com dados sensíveis;
- mensagens técnicas expostas ao usuário;
- status HTTP inadequado;
- ausência de testes para erros;
- código que mascara bugs em vez de corrigir a causa.
```

---

### Usar Tratamento de Erros Para Orientar Refatorações

Quando a IA refatora código, ela pode alterar acidentalmente o comportamento dos erros.

Prompt recomendado:

```text
Refatore este código sem alterar o comportamento dos erros.

Preserve:
- exceções lançadas;
- códigos HTTP;
- mensagens de usuário;
- mensagens de log;
- causa original das exceções;
- testes de erro existentes.
```

Esse cuidado é importante porque agentes de IA podem modificar vários arquivos rapidamente.

---

### Definir uma Política de Falhas

Projetos que usam IA se beneficiam de uma política explícita de falhas.

Exemplo:

```text
Política de falhas da aplicação:

- Erro de validação:
  retornar 400 ou 422 com mensagem clara.

- Regra de negócio violada:
  retornar 409 ou 422 com mensagem amigável.

- Falha técnica recuperável:
  registrar warn e tentar novamente quando fizer sentido.

- Falha técnica não recuperável:
  registrar error e retornar 500.

- Bug inesperado:
  registrar stack trace completo, retornar mensagem genérica e corrigir a causa.

- Logs:
  não registrar dados sensíveis.
```

Essa política pode ser incluída no prompt inicial do projeto ou em documentos de orientação para a IA.

---

### Exemplo de Prompt Completo Para IA

```text
Implemente o caso de uso de matrícula de aluno em disciplina.

Arquitetura:
- Controller recebe a requisição HTTP.
- Service aplica regras de negócio.
- Repository acessa a persistência.

Regras:
- O aluno deve existir.
- A disciplina deve existir.
- A turma deve existir.
- O aluno deve ter cumprido os pré-requisitos.
- O aluno não pode estar matriculado duas vezes na mesma turma.

Contrato de erros:
- 201: matrícula criada com sucesso.
- 400: JSON inválido ou campos obrigatórios ausentes.
- 404: aluno, disciplina ou turma não encontrado.
- 409: aluno já matriculado na turma.
- 422: aluno não cumpriu pré-requisito.
- 500: falha interna inesperada.

Tratamento de exceções:
- Não propague exceções de infraestrutura diretamente para o controller.
- Encapsule falhas do repository em RepositoryException.
- Encapsule falhas técnicas do service em ServiceException.
- Use exceções de domínio para regras de negócio.
- Preserve a causa original das exceções.
- Não use catch vazio.

Logging:
- Use info para eventos relevantes.
- Use warn para situações suspeitas.
- Use error para falhas técnicas.
- Não registre senhas, tokens ou dados sensíveis.
- Inclua contexto útil, como alunoId, disciplinaId e turmaId.

Resposta ao usuário:
- Não exponha mensagens técnicas.
- Não retorne stack trace.
- Use mensagens amigáveis.

Testes:
- Gere testes para sucesso, validação, regras de negócio e falhas técnicas.
```

---

### Ideia Central

Ao desenvolver com IA, o tratamento de erros precisa ser especificado, revisado e testado.

A IA pode ajudar muito, mas não deve ser usada apenas para gerar o caminho feliz.

A qualidade de uma aplicação aparece principalmente quando algo dá errado.

Por isso, ao usar IA, é importante perguntar:

- O que acontece se o usuário enviar dados inválidos?
- O que acontece se a regra de negócio impedir a operação?
- O que acontece se o banco cair?
- O que acontece se o arquivo não puder ser gravado?
- O que acontece se uma exceção inesperada ocorrer?
- O erro será registrado?
- O usuário verá uma mensagem segura?
- A equipe conseguirá investigar o problema depois?

Em desenvolvimento com IA, saber programar também significa saber orientar a IA sobre como o sistema deve falhar.
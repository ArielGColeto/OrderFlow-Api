# Diário de Estudos — OrderFlow API

## Aula 01 — Introdução ao Spring Boot

**Objetivo:** criar e executar a estrutura inicial de uma API REST com Java e Spring Boot.

### 1. O que é Spring Boot?

Spring Boot é uma ferramenta do ecossistema Spring que facilita a criação e configuração de aplicações Java.

Com ele podemos desenvolver APIs REST e executar uma aplicação web utilizando um servidor incorporado, como o Tomcat.

### 2. O que é Maven?


Maven é uma ferramenta utilizada para gerenciar dependências, compilar, testar e empacotar projetos Java.

O arquivo `pom.xml` contém informações e configurações importantes do projeto

### 3. Estrutura inicial

- `pom.xml`: configuração do Maven e dependências.
- `src/main/java`: código-fonte Java da aplicação.
- `src/main/resources`: arquivos de configuração e recursos.
- `src/test/java`: testes automatizados.
- `application.properties`: configurações da aplicação.

### 4. Classe principal do Spring Boot

- `@SpringBootApplication`: identifica a classe principal e reúne configurações necessárias à inicialização do Spring Boot.
- `main()`: ponto de entrada da aplicação Java.
- `SpringApplication.run()`: inicializa a aplicação Spring.

### 5. O que é uma API REST?

Uma API permite que diferentes aplicações se comuniquem. Em uma API REST, trabalhamos com recursos identificados por URLs e utilizamos os métodos HTTP para interagir com eles.

Exemplos:

- `GET /produtos`: consultar produtos.
- `POST /produtos`: cadastrar um produto.
- `PUT /produtos/1`: substituir os dados de um produto.
- `PATCH /produtos/1`: atualizar parcialmente um produto.
- `DELETE /produtos/1`: solicitar a exclusão de um produto.

**Importante:** HTTP GET não é a mesma coisa que um getter de uma classe Java.

### 6. O que é Controller?

Controller é um componente que recebe requisições HTTP e define quais métodos da aplicação atendem determinadas rotas.

Organização típica:

- Controller: recebe requisições e produz respostas HTTP.
- Service: concentra regras de negócio.
- Repository: realiza operações de persistência e consulta de dados.

### 7. O que aprendi na prática?

- Criei o projeto OrderFlow com Spring Initializr.
- Configurei Java 21, Maven, Spring Web e Validation.
- Consegui executar a aplicação.
- Acessei `localhost:8080` e recebi HTTP 404, porque ainda não existe uma rota para `/`.

### 8. Perguntas para revisar

1. Para que serve o Maven?
2. Qual a função do arquivo `pom.xml`?
3. O que faz `@SpringBootApplication`?
4. Qual a diferença entre GET e POST?
5. Qual é a responsabilidade de um Controller?
6. Por que a aplicação retornou HTTP 404?

### Próximo conteúdo

- `@RestController`
- `@GetMapping`
- Criação do primeiro endpoint GET.

**Fonte de estudo:** https://spring.io/guides/gs/rest-service

## Aula 02 — Criando o primeiro Controller

### Objetivo
Criar um endpoint HTTP GET que retorne uma mensagem de texto, compreendendo como uma requisição é direcionada para um método Java.

### Classe criada
- Nome: ProdutoController.java
- Pacote: com.orderflow.api.controller
- Responsabilidade: atender requisições HTTP relacionadas a produtos.

### Conceitos utilizados
- @RestController: identifica a classe como um controlador REST gerenciado pelo Spring.
- @GetMapping: associa um método Java a uma requisição HTTP GET em uma rota específica.
- String: tipo de retorno utilizado no nosso primeiro endpoint.
- return: devolve o valor produzido pelo método.

### Endpoint
- Método HTTP: GET
- Rota: /produtos
- Resposta esperada: Bem-vindo ao catálogo do OrderFlow!

### @RequestMapping x @GetMapping

@RequestMapping é uma anotação geral de mapeamento HTTP.

@GetMapping é especializada em requisições GET.

Exemplo:
@GetMapping("/produtos")

### @RequestParam

Permite receber parâmetros de uma requisição HTTP,
como valores informados na URL.

Exemplo:
/produtos?nome=Maria

@RequestParam(value = "nome", required = false)

- value: nome do parâmetro esperado.
- required = false: parâmetro opcional.

Não é necessário um formulário HTML para testar.
Podemos utilizar navegador ou Postman.

### O que entendi com minhas palavras
Serve para que se receba parametros de uma requisição HTTP, sendo em alguns casos valores informados na URL

### Pergunta para revisão
Por que precisamos utilizar @RestController em vez de uma classe Java comum?

### String x Objeto na resposta HTTP

Um Controller pode retornar diferentes tipos de dados.

- String: retorna uma mensagem de texto.
- Objeto Java ou record: pode ser convertido em JSON
  pelo Spring usando a infraestrutura de serialização.

Exemplo de record:
public record Greeting(long id, String content) {}

No primeiro exercício do OrderFlow, utilizamos String
para entender o funcionamento das rotas HTTP.

Posteriormente, aprenderemos a retornar objetos
estruturados em JSON.

### Primeira implementação e revisão

Classe: ProdutoController.java

O que consegui implementar:
- Controller REST.
- Método HTTP GET.
- Retorno de uma String.
- Resposta personalizada usando um parâmetro.

O que precisei corrigir:
- Definir a rota em @GetMapping("/produtos").
- Aprender a usar @RequestParam.
- Remover imports não utilizados.

Novo conceito:
Query parameters permitem enviar informações
pela URL, como /produtos?nome=Maria.

### Desafio prático concluído

Implementei o ProdutoController, utilizando:

- @RestController para identificar o Controller REST.
- @GetMapping para mapear requisições GET.
- @RequestParam para receber parâmetros da URL.
- required = false para tornar um parâmetro opcional.
- if para tratar a ausência de um nome.

Aprendi que um parâmetro opcional pode ser null
e deve ser tratado antes de utilizar seus métodos.

Também aprendi que, após um return, não é
necessário utilizar else para continuar a lógica.

### Testes manuais
- GET /produtos?nome=Maria
- GET /produtos

Resultado: 

Ao utilizar as URLS obtive os seguintes retornos:

http://localhost:8080/produtos?nome=Maria → Olá Maria

http://localhost:8080/produtos → Bem-vindo ao catálogo do OrderFlow!
### Fonte
https://spring.io/guides/gs/rest-service
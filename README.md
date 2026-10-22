🛒 OrderFlow API
API REST em Java e Spring Boot, em desenvolvimento como projeto de estudos e portfólio backend. O objetivo é construir gradualmente um sistema para gerenciamento de clientes, catálogo e pedidos, com foco em boas práticas, banco de dados relacional e testes.
Estado atual: fase inicial de aprendizado. O código publicado implementa apenas um controller com um endpoint GET demonstrativo. Cadastro, persistência em banco de dados, fluxo de pedidos, autenticação e frontend ainda não estão implementados.

Tecnologias presentes no repositório
- Java 21
- Spring Boot 4.1.1
- Spring Web MVC
- Spring Validation (dependência adicionada, ainda sem uso em formulários reais)
- Maven Wrapper
- Git e GitHub
Endpoint implementado
Método	Rota	Comportamento
GET	/produtos	Retorna Bem-vindo ao catálogo do OrderFlow!
GET	/produtos?nome=Maria	Retorna Olá Maria


A resposta ainda é texto simples, não uma listagem de produtos em JSON.
Como executar
Pré-requisito: JDK 21 ou versão compatível com o projeto.
git clone https://github.com/ArielGColeto/OrderFlow-Api.git
cd OrderFlow-Api
No Windows:
.\mvnw.cmd spring-boot:run
No Linux ou macOS:
./mvnw spring-boot:run
Com a aplicação em execução, acesse http://localhost:8080/produtos no navegador ou em um cliente HTTP. Caso a porta 8080 esteja ocupada, configure outra porta para a aplicação.
Estrutura atual
src/
├── main/
│   ├── java/com/orderflow/api/
│   │   ├── OrderflowApiApplication.java
│   │   └── controller/ProdutoController.java
│   └── resources/application.properties
└── test/
    └── java/com/orderflow/api/OrderflowApiApplicationTests.java
docs/
├── estudos.md
└── erros-e-solucoes.md
Roadmap de desenvolvimento
- [x] Criar o projeto Spring Boot e a aplicação inicial.
- [x] Implementar um endpoint GET com parâmetro opcional.
- [ ] Criar modelos de produto e cliente.
- [ ] Implementar CRUD real com DTOs e validações.
- [ ] Adicionar persistência relacional com JPA e MySQL.
- [ ] Implementar pedidos, itens e regras de negócio.
- [ ] Escrever testes para regras e endpoints.
- [ ] Padronizar tratamento de erros e documentar a API.
- [ ] Avaliar autenticação e autorização.
- [ ] Desenvolver uma interface React integrada à API.
- [ ] Avaliar módulos de serviços, leads e orçamentos do futuro FreelaFlow.
Escopo planejado: o OrderFlow poderá apoiar operações com produtos e serviços, mas esses módulos serão modelados conforme o projeto evoluir. Nenhum deles deve ser considerado implementado neste estágio.
Diário de aprendizado
Registro das etapas e problemas encontrados:
- [Diário de estudos](docs/estudos.md)
- [Erros e soluções](docs/erros-e-solucoes.md)
Autor
Desenvolvido por Ariel Grassi Coleto, estudante de Análise e Desenvolvimento de Sistemas, com foco em backend Java.

# Erros e Soluções — OrderFlow API

## Problema 01 — Erro ao carregar o Maven

**Erro:** `Guice/MissingImplementation: ArtifactHandlerManager`

**Situação:** o IntelliJ apresentou um erro durante o carregamento do projeto Maven.

**Solução aplicada:**
1. Acessar Settings → Build Tools → Maven.
2. Alterar o Maven home path para Bundled (Maven 3).
3. Recarregar o projeto Maven.

**Resultado:** erro resolvido.

**Aprendizado:** um erro de inicialização pode estar relacionado à configuração do ambiente, e não necessariamente ao código da aplicação.

## Problema 02 — Whitelabel Error Page (404)

**Situação:** ao acessar `http://localhost:8080`, foi exibida uma página Whitelabel com status HTTP 404.

**Causa:** ainda não existe um endpoint configurado para a rota `/`.

**Resultado:** comportamento esperado nesta etapa. Nenhuma correção necessária.

**Aprendizado:** o servidor pode estar funcionando mesmo que uma URL solicitada não tenha uma rota correspondente.
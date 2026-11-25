# Sistema de Gestão de Tarefas — Forge Growth

Projeto Integrador: Sistema Web — Engenharia de Software  
Centro Universitário SATC — Prof. Hyan Dias Tavares — 2026

## Descrição

Aplicação web para a agência de marketing Forge Growth, que trabalha com lançamentos digitais.

O sistema é um gestor de tarefas inspirado no ClickUp, em versão simplificada. Ele organiza a
execução dos lançamentos em um quadro Kanban, com responsável e prazo em cada tarefa, e trabalha
com três entidades principais: cliente, projeto e tarefa.

Cada projeto é criado a partir de um modelo de lançamento, que já traz as tarefas padrão divididas
em quatro divisões fixas: Produto, Conteúdo, Tráfego e Disparos.

## Níveis de acesso

| Nível | O que pode fazer |
|---|---|
| Administrador | Cadastra clientes, cria projetos, atribui tarefas e enxerga todo o sistema |
| Colaborador | Vê apenas as tarefas atribuídas a ele e as que ele mesmo criou |

## Equipe

| Integrante | Função |
|---|---|
| Mateus Salles Melo | Back-end e Banco de Dados |
| Gabriel Dalmolin | Front-end |
| Yuri Ribeiro Nesi | UI/UX Design |
| Henrique Lucio Coral | Scrum Master e gestão do Kanban |

## Tecnologias

- **Front-end:** React, Vite, Bootstrap e React-Bootstrap para a interface, React Router para navegação e Axios para chamadas à API.
- **Back-end:** Node.js e Express para a API REST, Zod para validação de dados e dotenv para configuração por variáveis de ambiente.
- **Banco de dados:** PostgreSQL, acessado pela API com o driver `pg` (node-postgres).
- **Autenticação e segurança:** JWT (`jsonwebtoken`) para autenticação, scrypt para hash de senhas, Helmet para cabeçalhos de segurança e `express-rate-limit` para limitar tentativas de login.
- **Testes e qualidade de código:** `node:test` para testes unitários e de ponta a ponta da API e ESLint no front-end e no back-end.
- **Infraestrutura e documentação:** Docker e Docker Compose para execução local da API e do banco, Cloudflare Pages e Render para hospedagem e OpenAPI para documentação da API.

## Estrutura do repositório

- [`/frontend`](frontend/README.md) — aplicação React. Consulte o guia para rodar e publicar o front-end.
- [`/backend`](backend/README.md) — API REST em Node.js. Consulte o guia para executar a API e configurar o banco de dados.
- `/docs` — contrato da API (OpenAPI).

## Sistema publicado

| Parte | Endereço | Hospedagem |
| --- | --- | --- |
| Front-end | https://sistema-gestao-de-tarefas.pages.dev | Cloudflare Pages |
| API | https://api-forge-growth.onrender.com | Render |
| Banco de Dados | -- | Neon |

A API está hospedada no plano gratuito do Render e pode adormecer após um período de inatividade, fazendo com que as primeiras requisições demorem mais enquanto ela volta a responder.

O front-end e a API são publicados automaticamente a cada push na branch `main`.

## Gestão do projeto

Quadro Kanban da equipe: https://trello.com/b/7yreWVfz

## Status

Banco de dados, API e telas implementados e publicados. Em fase de testes e ajustes finais.

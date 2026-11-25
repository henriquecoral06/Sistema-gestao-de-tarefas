# Front-end — Forge Growth

Front-end do sistema de gestão de tarefas, feito com React, Vite e React-Bootstrap. As chamadas à API são feitas com Axios e as rotas das telas com React Router.

Sistema publicado: https://sistema-gestao-de-tarefas.pages.dev

## Como rodar

Use Node.js 22 ou superior. Antes, deixe a API rodando (veja o [README do back-end](../backend/README.md)).

```bash
cd frontend
npm install
cp .env.example .env
npm run dev
```

O sistema abre em http://localhost:5173.

No arquivo `.env`, a variável `VITE_API_URL` guarda o endereço da API. O padrão é `http://localhost:3000/v1`.

## Comandos

| Comando | O que faz |
| --- | --- |
| `npm run dev` | Roda o sistema em modo de desenvolvimento |
| `npm run build` | Gera a versão de produção na pasta `dist` |
| `npm run preview` | Abre localmente a versão gerada pelo build |
| `npm run lint` | Verifica o código com o ESLint |

## Telas

| Tela | Endereço | Quem acessa |
| --- | --- | --- |
| Login | `/` | Todos |
| Dashboard | `/dashboard` | Todos |
| Kanban | `/tarefas` | Todos. O administrador vê por projeto, por colaborador e as tarefas que criou. O colaborador vê as tarefas atribuídas a ele e as que ele criou |
| Projetos | `/projetos` | Todos. Só o administrador cria, edita e muda o status |
| Clientes | `/clientes` | Administrador |
| Modelos de lançamento | `/modelos` | Administrador |
| Usuários | `/usuarios` | Administrador |
| Alterar senha | `/senha` | Todos |

Não tem cadastro público. Os usuários são criados pelo administrador na tela de Usuários.

No primeiro acesso do administrador inicial, a tela de login pede um novo nome, e-mail e senha antes de entrar no sistema.

## Pastas

```
src/
  components/  menu (Layout) e proteção das rotas
  pages/       uma tela por arquivo
  services/    api.js (chamadas à API) e sessao.js (usuário logado e token)
  utils/       nomes das divisões, status e formatação de datas
```

## Publicação no Cloudflare Pages

O Cloudflare Pages publica o front automaticamente a cada push na branch `main`.

| Configuração | Valor |
| --- | --- |
| Diretório raiz | `frontend` |
| Comando de build | `npm run build` |
| Diretório de saída | `dist` |
| Variáveis de ambiente | `VITE_API_URL` com o endereço da API publicada e `NODE_VERSION=22` |

O arquivo `public/_redirects` faz o Cloudflare abrir o `index.html` em qualquer endereço, para que recarregar a página em `/tarefas`, por exemplo, não dê erro 404.

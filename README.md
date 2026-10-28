# Acme Dashboard — primeiro treinamento de Next.js

Registro do primeiro treinamento com o [curso Learn do Next.js](https://nextjs.org/learn), feito em cima do starter do App Router. O app é um painel de faturas (Acme) com Postgres na Neon, Tailwind e autenticação.

## O que foi feito

- Página inicial com logo, fonte Lusitana, CSS Modules e imagens para desktop e mobile.
- Layout raiz com CSS global, fonte Inter e metadata (`title` com template `%s | Acme Dashboard`).
- Dashboard com menu lateral, página de visão geral, clientes e faturas.
- Banco Postgres na Neon. Tabelas e dados de exemplo entram pela rota `/seed`, a partir de `app/lib/placeholder-data.ts`.
- Leitura dos dados em `app/lib/data.ts` e teste da conexão em `/query`.
- Visão geral em partes: cards, gráfico de receita e últimas faturas, cada um com `Suspense` e skeleton. O loading da rota `/dashboard` fica em `app/dashboard/(overview)/loading.tsx`. Os quatro cards carregam juntos dentro de `CardWrapper`.
- Faturas: busca, tabela, paginação, criar, editar e excluir. Criar e editar usam Server Actions em `app/lib/actions.ts`, com validação Zod. A mensagem geral ("Missing Fields") aparece no formulário de criação.
- Erros de render da lista de faturas caem em `app/dashboard/invoices/error.tsx`. Uma fatura inexistente na edição cai em `not-found.tsx`.
- Login com Auth.js (`next-auth`): `auth.ts`, `auth.config.ts` e `proxy.ts` protegem `/dashboard`. O botão Sign Out está no menu lateral.
- ESLint com `eslint` e `eslint-config-next`. O script `pnpm lint` roda `eslint .`.


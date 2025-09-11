# ts-template

Template mínimo em TypeScript para projetos Node.js (ESM) focado em produtividade e convenções modernas.

Este repositório fornece uma base simples com configuração pronta para desenvolvimento, build e testes:

- TypeScript com `tsc` (target Node 22+)
- Execução rápida em desenvolvimento com `tsx`
- Alias de compilação com `tsc-alias`
- Testes com `vitest`
- Linter/format via `biome` (configurada nos scripts)
- Suporte a variáveis de ambiente via `dotenv-flow`
- Fluxo de releases com `release-it` e convenção de commits (Commitizen + commitlint)

## Requisitos

- Node.js >= 22
- npm / yarn / pnpm (qualquer gerenciador de pacotes que preferir)

## Instalação

Instale dependências:

```bash
npm install
```

## Estrutura do projeto

Principais arquivos e pastas:

- `package.json` — scripts e dependências
- `tsconfig.json` — configuração do compilador TypeScript
- `src/` — código fonte (ex.: `src/index.ts`)
- `dist/` — saída de build (gerada)

## Scripts úteis

Os scripts definidos em `package.json`:

- `npm run dev` — executa `src/index.ts` em modo desenvolvimento com `tsx` e `dotenv-flow`.
- `npm run build` — compila TypeScript (`tsc`) e aplica `tsc-alias` para resolver paths.
- `npm run start` — executa a build (`dist/index.js`) com suporte a `dotenv-flow`.
- `npm run check` — executa `biome check` (lint/static analysis).
- `npm run check:fix` — tenta corrigir problemas automaticamente (`biome check --fix`).
- `npm run test` — roda testes com `vitest` (pasta `src`).
- `npm run test:coverage` — roda testes com cobertura.
- `npm run verify` — roda `check`, `test` e `build` (fluxo de verificação).
- `npm run release` — inicia fluxo de release via `release-it` (configurar antes de usar).

Exemplo rápido (desenvolvimento):

```bash
npm run dev
```

Build e execução em produção local:

```bash
npm run build
npm run start
```

## Variáveis de ambiente

Este template inclui `dotenv-flow` para carregar variáveis de ambiente em `dev` e `start`. Crie arquivos `.env`, `.env.development`, `.env.test` conforme necessário.

## Convenções e contribuições

- Commits: a base já traz `commitizen` e `cz-conventional-changelog` para gerar mensagens de commit no formato Conventional Commits.
- `commitlint` e `husky` são usados para reforçar políticas de commit (hooks) — é recomendável ativar `husky` localmente (`npm run prepare` já está presente no `package.json`).

Se quiser contribuir:

1. Fork e branch feature/bugfix.
2. Siga o padrão de commits convencionais (p.ex. `git cz` para criar commits).
3. Rode `npm run check` e `npm run test` antes de abrir PR.

## Publicação / Releases

O projeto inclui `release-it` para automatizar releases. Configure `release-it` (token de publicação e parâmetros) antes de usar `npm run release`.

## Exemplos e ponto de partida

O arquivo `src/index.ts` contém um exemplo mínimo:

```ts
// exemplo rápido
console.log('Hello, world!')
```

Use este repositório como ponto de partida para bibliotecas ou microserviços pequenos. Para projetos maiores, adicione ferramentas de CI, linters/formatters mais estritos, e uma suíte de testes mais completa.

## Licença

MIT — consulte `package.json`.

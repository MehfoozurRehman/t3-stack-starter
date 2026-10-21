# T3 Stack Starter

A Next.js, tRPC and Prisma starter with a single Post model and a create-and-read demo.

**Status:** Starter. The repo is the Create T3 App template, with one Post model and three tRPC procedures, and no features beyond that.

## The problem

Full-stack TypeScript apps need the server and client to share types, a database layer and data fetching without hand-written API contracts. This repo wires those pieces together with a small Post example so the pattern is visible end to end.

## What it does

- A tRPC router (`src/server/api/routers/post.ts`) with `hello`, `create` and `getLatest` procedures, with inputs validated by Zod.
- A home page (`src/app/page.tsx`) that calls the router on the server and prefetches the latest post.
- A client component (`src/app/_components/post.tsx`) that reads the latest post with a suspense query and creates new posts through a mutation.
- A Prisma `Post` model on PostgreSQL (`prisma/schema.prisma`) with an id, name and timestamps.
- Environment validation with `@t3-oss/env-nextjs` in `src/env.js`, so missing variables fail at startup.

## How it's built

- Next.js 15 App Router with Turbopack, tRPC v11 with SuperJSON, TanStack React Query v5, and Prisma 5.
- Shared types: the tRPC router is exposed through `src/app/api/trpc/[trpc]/route.ts`. The client helpers in `src/trpc/react.tsx` and the server helper in `src/trpc/server.ts` both use the same router type, so calls are type-checked on both sides.
- `postinstall` runs `prisma generate`, so the Prisma client exists after install.

## Running it locally

Requires Node.js 18 or 20, pnpm, and a PostgreSQL database.

```bash
pnpm install
cp .env.example .env     # then set DATABASE_URL
pnpm db:push             # sync the Prisma schema
pnpm dev                 # opens on http://localhost:3000
```

Other scripts from `package.json`: `build`, `start`, `check` (lint and typecheck), `db:studio`.

## What's left

- Starter only. The Post demo is the entire feature set.
- Every procedure is a `publicProcedure`, so anyone who can reach the app can create posts. There is no authentication.
- No tests in the repo.
- The package name is still `test`, and the README's earlier name was `t3-test`.

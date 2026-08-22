# T3 Stack Full-Stack Web App

A end-to-end type-safe full-stack web application built using the Create T3 App stack (Next.js 15, tRPC, Prisma, and React Query).

## Overview

`t3-test` demonstrates a type-safe full-stack development workflow featuring Next.js App Router, tRPC API routers for type safety between client and server, TanStack React Query for data fetching, and Prisma ORM for database migrations and queries.

## Tech Stack

- **Framework**: [Next.js](https://nextjs.org/) (v15, Turbopack)
- **API & RPC**: [tRPC](https://trpc.io/) (v11) & [SuperJSON](https://github.com/blitz-js/superjson)
- **Data Fetching**: [TanStack React Query](https://tanstack.com/query) (v5)
- **Database & ORM**: [Prisma](https://www.prisma.io/) (v5)
- **Validation & Environment**: [Zod](https://zod.dev/), `@t3-oss/env-nextjs`
- **Language**: TypeScript

## Prerequisites

- Node.js (v18 or v20 recommended)
- Package manager (`pnpm` recommended)
- PostgreSQL / SQLite database instance

## Getting Started

1. **Install dependencies**:
   ```bash
   pnpm install
   ```

2. **Configure Environment Variables**:
   Create a `.env` file from `.env.example`:
   ```bash
   cp .env.example .env
   ```
   Configure your database connection:
   ```env
   DATABASE_URL="postgresql://postgres:password@localhost:5432/t3_test"
   NODE_ENV="development"
   ```

3. **Initialize Database**:
   ```bash
   # Push schema to database
   pnpm db:push
   # Or run migrations
   pnpm db:generate
   ```

4. **Run the Development Server**:
   ```bash
   pnpm dev
   ```

5. **Access the Application**:
   Open `http://localhost:3000` in your web browser.

## Available Scripts

- `pnpm dev` - Starts the Next.js dev server with Turbopack.
- `pnpm build` - Builds the application for production.
- `pnpm start` - Starts the production server.
- `pnpm db:push` - Synchronizes Prisma schema directly with the database.
- `pnpm db:studio` - Opens Prisma Studio GUI in browser.
- `pnpm check` - Lints and runs TypeScript type checks.

## Author

Created by [Mehfooz-ur-Rehman](https://github.com/MehfoozurRehman).

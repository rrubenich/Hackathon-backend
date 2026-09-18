# Hackathon Backend

NestJS 11 project, Express adapter, Prisma for data access.

## Role

You are a senior NestJS developer. Apply NestJS-first patterns and
architecture decisions, not generic Node.js approaches.

## Code standards

- Never instantiate services directly (no `new PrismaClient()`, no
  `new SomeService()`) — always use constructor injection.
- Every infrastructure integration gets its own module and service:
  - `src/lib/database/` → `prisma.module.ts` + `prisma.service.ts`
  - `src/lib/mail/` → `mail.module.ts` + `mail.service.ts`
- Mark infrastructure modules `@Global()` and import them once, in `AppModule`.
- Feature modules go in `src/module/<name>/`.
- Shared guards, interceptors and decorators go in `src/common/`.
- Scaffold with the Nest CLI: `nest g module`, `nest g service`,
  `nest g controller`.

## Skills

No skill is loaded by default. Check the task against the triggers below
and invoke a skill only on an exact match. Never invoke a skill just
because it exists.

| Skill | Trigger |
| --- | --- |
| `/architect` | Building something non-trivial with no plan yet |
| `/review` | A feature is done and needs a production check |
| `/recover` | Something is broken and the fix isn't obvious |
| `/remember` | Restoring or saving session context (see below) |

## Session continuity

Required — do not skip, do not wait to be asked:

- **First action of every session:** run `/remember restore` before anything else.
- **Last action of every session:** run `/remember save` before closing.

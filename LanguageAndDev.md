ONLY ADD WHAT'S NECESSARY. FOLLOW RULE 1 HERE TOO.
# Python
## Libraries

FastAPI
pytest
Pydantic-settings    (env config)
SQLAlchemy + Alembic (if any DB — see Data Layer)
arq                  (if any background jobs)
httpx                (if calling external APIs)
logfire              (observability)
polars               (Data processing, better than pandas)
pytorch           (ML, probably the best one)

## dev tooling

ruff
uv
ty


# TypeScript

## Libraries

Vite
- pnpm create vite. Choose React with Tanstack Router preset. Select to add: Compiler, shadcn and anything else you may want.

Hono
React
Zod
Drizzle (ORM)
Tanstack Router
Tanstack Query
Zustand
Shadcn UI
- Better than Chakra UI
- extremely easy to stop using (rule 2)
BullMQ if docker, Inngest if edge
vitest

## dev tooling
Biome
pnpm (look out for bun when ecosystem gets mature enough)

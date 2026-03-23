## Start here: Postgres

Default to Postgres. It handles relational data, JSON documents, full-text search, and time-series (via TimescaleDB extension) — one system that grows with you. The switching cost of your database engine is extremely high (Rule 2), so choose something boring, proven, and with a huge ecosystem. Postgres is that.

**Hosting:**

- On a VPS (Dokploy, etc.)? Self-host Postgres on the same box. It's free, simple, and a single $10–20/month server handles serious traffic. Don't pay per read/write until you genuinely have to.
- Serverless (Cloud Run, etc.)? Use **Neon** — serverless Postgres, same SQL, just scales to zero.
- Already using Supabase? Use its built-in Postgres. Don't add another DB.

**ORM:**

- Python: SQLAlchemy + Alembic. Mature, async-ready, integrates well.
- TypeScript: Drizzle. Lightweight, SQL-first, no magic — you always know what query runs.

## When to deviate

**SQLite** — local scripts, CLIs, embedded apps, or early-stage projects with a single user. Promotes to Postgres later without pain.

**Cloudflare D1**: only if you
- are using Cloudflare stuff
- want to favor short-term DX instead of long-term boring tech (breaks Rule 2)

**NoSQL** — only if your data is genuinely document-structured with _no_ relational needs. MongoDB's flexible schema is a trap if you're just avoiding upfront schema design. Bad schemas don't disappear; they just become invisible and inconsistent.

## Add Redis when you need any of: caching, task queues, pub/sub, rate limiting

Redis does all of these. One service, not four. Add it when you have a concrete need — don't pre-provision it.

- On a VPS: run Redis on the same box as Postgres.
- Serverless: use **Upstash** (serverless Redis, generous free tier).

## File storage

- **On a VPS:** MinIO. Free, Docker-friendly, full S3 API. Runs alongside your app.
- **Managed:** Cloudflare R2. No egress fees, S3-compatible, best value for most projects.
- **Already on Supabase:** Supabase Storage. It's already there.
- Avoid S3 as a default; egress costs compound fast once you have real traffic.
Below each choice of tech, a brief explanation of why. 
Consider, IN ORDER, if each option satisfies your use case. This maximizes simplicity and minimizes price early-stage. Later options cover more use cases and offer more flexibility.

## **BaaS and/or Edge**
BaaS: Supabase
- Fastest time to market, simple mental model (rule 1)
- Can use edge functions and has many more features than edge (encompasses edge use case below)
- It's just something your frontend calls. if you need to add a backend later for something, you don't even need to remove supabase (Rule 2)
- Can generate types (Rule 3)
- If the app succeeds and costs spike, just self-host on best VPS provider with Dokploy (rule 6)

Edge: Hono
- Free tier of deploy providers covers most hobby/side-project traffic forever.
- If you need to move to Docker (below) to rid yourself of edge limitations, just change deployment, no code changes (Rule 2). BaaS doesn't have this option (at least not as easy)
- Allows flexibility for other frontend clients like mobile (unlike full stack meta frameworks)
- Hono RPC with frontend on monorepo allows e2e type safety, no codegen (Rules 3 and 4)
- Easier deploy/configuration/local setup than BaaS

Look out for Elysia JS and Tanstack Start: once mature, might be the best options

## **Docker**
FastAPI
- Python, if you need it: better access to ML, data science, etc.
- Very type safe, possible to use openapi.json to generate types for frontend, unfortunately with codegen (Rule 3)

Hono
- Benefits mentioned above
# Deployment

Best VPS provider = best performance/price
- Oracle Always Free Tier, if you have
- Hetzner CX22 (€3.29/mo, 2 vCPU, 4 GB RAM) or CAX21 (ARM, more RAM per euro).

Edge deployment
- Cloudflare workers, Deno Deploy, Vercel

Docker deployment (use terraform (with modules))
- GCP cloud run
- Render
- Railway
- Best VPS + dokploy
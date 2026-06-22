# Dev

## Claude Code

Maybe better than Cursor (Cursor is faster though). Pro plan suffices for me, personally, in my current levels of AI usage. Probably not enough if you work on big codebases or use multiple agents or use it the whole day.

Use plugins for everything you use: GitHub, Cloudflare, Supabase, etc. (For me on ubuntu github plugin just wouldn't work, so i set up a custom user MCP pointing to their official MCP server)
If something doesn't have a plugin but has skills (like shadcn), use `pnpx skills` (with -g flag to install globally) to install skills for all AI agents. Run pnpx skills update frequently to keep skills up to date (or add a cron job with `crontab -e`: `0 9 * * 1 pnpx skills update -y`. Maybe dangerous because of supply chain attacks?). If skills don't exist for a third-party thing, use an official MCP.

Add context7 plugin and add rules/instructions to make the agent always use context7 when using features of an external library that don't yet exist in the repo.

Add playwright plugin to test with playwright.

Enable/disable these per project so you don't spend more context with tools than is needed.

Use RTK. Reduces token consumption

# AI providers

Don't get bogged down by the "Need". These are ideas and you should pick the best option for your use case.
| Need | Pick |
| :--- | :--- |
| Speed | Groq or Cerebras |
| General purpose / broadest model selection | Fireworks AI or DeepInfra (very cheap) or Replicate (very flexible) |
| Custom code or niche models | Modal |
| Scale / long-running | RunPod |

# AI frameworks

- Vercel AI SDK. Use in serverless, like Cloudflare Workers

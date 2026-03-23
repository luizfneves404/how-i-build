This guide focuses on main choices that force you on different paths. As always, consider the options in the order they are shown. For libraries and stuff that you sprinkle on top, see [[Programming Language and dev Guide]].

# CLI

Typer (if Python)

# Python quick frontend
(especially for computational/data apps)
JUST USE `streamlit` (Rule 1). Deploy on Streamlit Community Cloud. if you hit some limitation (see https://docs.streamlit.io/deploy/streamlit-community-cloud/status and https://docs.streamlit.io/deploy/streamlit-community-cloud/manage-your-app#app-resources-and-limits), consider (in order)
- Render
- GCP cloud run and Terraform
- dokploy on best VPS provider.

# SPA and Meta framework
If you do need a stronger frontend, you have these 2 options.
## SPA
Choose **SPA** if
- You don't even need server-side code or will use BaaS (in these cases, meta framework is overkill)
- You value being able to switch to multiple frontends later (rule 2)
- you aren't squeezing maximum dev speed

Tech choice:
- Vite + React (the rest is sprinkled on top)
## Full stack Meta framework
Choose **meta framework** if you
- Need some server-side code
- Are building only for web frontend, will never switch
- want maximum dev speed
- want stack simplicity (rule 1)
- want more codebase integration (rule 4)

Tech choice:
- React Router v7 (nowadays not only router, it's a full stack framework)
	- keeps us in the amazing React ecosystem
	- avoids Next JS, which is too server-first. https://tanstack.com/start/latest/docs/framework/react/start-vs-nextjs

Look out for Remix v3 and Tanstack Start (when it gets to v1)

# Mobile app
- Vite exports to PWA (with plugin). If this is enough, go for it! Easier than app stores
- If you need true apps, think about React Native vs native languages

# Deployment
Streamlit
- Streamlit community cloud
- Other PaaS if hit limitations
SPA -> CDN
- Cloudflare Pages
Meta framework
- Vercel
- Netlify
- Self-host via VPS + dokploy if above gets expensive
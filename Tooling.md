# Editor and command line

**Cursor and Zed.** If you don't care about performance or your computer can handle it without any struggle, go with Cursor. I've been using Zed more because of how fast it is. On my laptop, opening one Cursor window and doing many other things is much slower than in Zed. Having many Cursor windows open is a much worse experience than having many windows in Zed.

## Config
- Enable code actions on save for everything that is reasonable.
- Have one vscode profile with your most broad/lightweight tools and enable/disable tools per project.
	- Having multiple profiles creates mental overhead ("what profile does this project belong to? what extensions should this profile have?").
	- The only use case for profiles is when you create projects so frequently that you hate spending time enabling/disabling extensions per project.
	- Enabling and disabling is necessary for good performance, otherwise starts lagging.
	- Configure settings.json to have the settings of all possible extensions, even if they aren't recognized because most are disabled in the default profile. Configure by enabling the extensions on a specific workspace without altering the Default profile



# Testing
 `playwright` if you need end-to-end tests. Add when the project isn't throwaway.


# CI/CD

**GitHub Actions** unless the repo isn't on GitHub. No reason to evaluate alternatives for a solo developer.


# Containers

**Docker + docker-compose for local dev** on anything that involves a database or Redis. Never run Postgres or Redis directly on your host machine for a project.

**Docker Buildx** when deploying to ARM (Oracle Always Free ARM instances). Build multi-arch images in CI with `docker buildx build --platform linux/amd64,linux/arm64`.


# Infrastructure as Code

Add Terraform (or OpenTofu) when you have:
- Provider that has Terraform integration
Why? We prefer to specify things in code always instead of UI.

Use Terraform modules! Simplifies even more.

# Monorepo tools

Add **Turborepo** only when you have an actual monorepo (multiple packages or apps in one repo). Don't add it speculatively — the config overhead isn't worth it for a single app.

Add **OpenAPI TypeScript**, if the frameworks doesn't provide end-to-end type safety (like a FastAPI + React setup)

# Other tools

Add **pre-commit** when:
- More than one contributor
- You want formatting enforced before commits reach CI
- For solo projects: optional, but prevents sloppy commits

Add **just** when:
- You have project commands (to run, build, dev, etc) that are kinda complex. Probably true for a project that's not throwaway
Serves as living documentation for the "terminal" part of the project. When you come back to the project months later, you immediately know the quirks of running it.

**Using a BaaS?** Use its auth. Supabase Auth with Supabase, Firebase Auth with Firebase. Don't layer a separate system on top — you lose DB-level security integration for nothing.

**Default pick: Clerk.** Free to 10k MAU (by which point you have revenue). Social login, magic links, MFA, orgs, and React UI components all included. Works with any backend via JWT. If you reach 10k MAU without revenue, auth pricing is not your problem.

**Self-hosting everything?** SuperTokens. works with any language.

**need IAM?** Zitadel. Skip Keycloak unless you have dedicated DevOps — it's powerful and demanding in equal measure.

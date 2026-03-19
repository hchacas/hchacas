# Personal Projects
 
## signal-engine — Agentic Writing CLI
*Node.js · TypeScript · Anthropic Claude Sonnet · Google Gemini · Vitest*
 
A CLI tool that turns weekly engineering notes into LinkedIn post drafts. Two sequential LLM calls: extract structured insights, then generate 5 drafts across distinct angles (technical decision, systems thinking, builder mindset, cost discipline). A feedback loop refines a persistent taste profile after each publish cycle.
 
**Context engineering decisions:**
- Prompt templates are `.md` files — content, not code; iterable without touching source
- Token budget is a design constraint: `extractInsights` at 1,000 tokens; `generatePosts` batches all 5 drafts in a single 4,000-token call instead of 5 separate calls
- Memory split across 6 human-readable YAML/JSON files — no database, version-control friendly, stable context window size across hundreds of runs
- Taste profile is **refined and replaced** each cycle, never accumulated — prevents context bloat
- No LangChain — raw `@anthropic-ai/sdk` typed function calls
- Full weekly cycle costs ~$0.01–0.02 at current Sonnet pricing
 
 
## HC Wedding — Full-Stack RSVP Platform
*Live at [sheilayhabib.com](https://sheilayhabib.com) · Astro SSR · Express · SQLite · Docker · DigitalOcean*
 
Wedding web app built as university final project (TFG). Guests get unique token-based invite links, authenticate via Google OAuth, and submit their RSVP. The couple manages everything through a custom admin panel.
 
- Monorepo with two services behind Nginx (SSL termination, reverse proxy, static caching)
- Migration-aware password hashing: SHA-256 → bcrypt upgrade on first login, zero downtime
- Persistent SQLite volume with Docker entrypoint `root → appuser` handoff via `su-exec`
- 4-image CI/CD pipeline built, pushed to GHCR, and deployed via SSH in a single GitHub Actions workflow
 
 
## Glow Head Spa — Marketing Website
*Live at [glowheadspa.es](https://glowheadspa.es) · Next.js 16 · TypeScript · Tailwind CSS v4 · Netlify*
 
Marketing site for a Japanese Head Spa salon in Priego de Córdoba. Designed and built end-to-end — brand identity, design token system, production deployment.
 
Before writing code, scoped two paths: managed CMS (~20€/mo, full client independence) vs. custom static build. One conversation made the trade-off clear — low-cost entry point, bookings via WhatsApp, edits can wait. That shaped every decision.
 
 
# Certifications
- **Certified Kubernetes Application Developer (CKAD)** — Nov 2024
- **Leadership Journey** — Mar 2025
 

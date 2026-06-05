# CLAUDE.md template

> ⚠️ AI-generated · Reviewed by Haojun Yong (OTG).

Save this as `CLAUDE.md` in your repo root. Claude Code reads it automatically every conversation in this project.

---

```markdown
# CLAUDE.md

## What this project is

[ONE PARAGRAPH: what the website is, who it's for, where it's going to live. Reference brand-brief.md for full voice and audience details.]

## Stack

- Next.js 16 (App Router)
- TypeScript 5, strict
- Tailwind CSS 4 + occasional custom CSS in globals.css
- MDX for blog posts (if used)
- Hosted on Vercel — that's the only host we ship to
- Domain at Namecheap, nameservers pointed at Vercel
- Resend for any email handlers (no DB)

## Files Claude should always read first

- brand-brief.md — voice, audience, anti-words
- src/content/* — the markdown / MDX sources of truth
- src/app/layout.tsx — global metadata and shell
- src/app/globals.css — design tokens

## Coding conventions

- App Router server components by default; mark client with "use client" only when needed.
- One css file (globals.css) plus Tailwind utility classes. No CSS-in-JS, no styled-components.
- Components in src/components/. Hooks-and-state components are client; everything else stays server.
- Content lives in src/content/, separate from src/components/.
- No comments unless they explain a non-obvious why.
- No emojis unless I explicitly ask for them.
- Don't suggest Cloudflare, Netlify, or other hosts. Vercel only.

## Design system

- Background: [your bg colour]
- Ink: [your foreground colour]
- Accent: [your single accent colour]
- Heading font: [Georgia / Inter / etc.]
- Body font: [Inter / system-ui / etc.]
- Spacing: 4/8/16/24/32/48/64/80 — stick to this scale.
- Buttons: 8px radius, 12–14px font, weight 600.

## Voice

[Direct lift from your brand-brief.md voice + anti-words. Three bullets each.]

## Things I don't want

- Don't refactor unrelated files.
- Don't add libraries without asking. We're staying minimal.
- Don't write defensive null checks for things that can't be null in this codebase.
- Don't add JSDoc / TypeDoc / inline docstrings unless I ask.

## Deploy

- `npm run dev` — local at :3000
- `npm run build` — production build
- `npm run lint` — ESLint
- Pushes to master auto-deploy on Vercel
- Preview deployments fire on every PR branch
```

---

**Generated with Claude. Reviewed by Haojun Yong (On The Ground).**
For tailored, hands-on guidance, see [ontheground.agency](https://www.ontheground.agency) or email [haojun@ontheground.agency](mailto:haojun@ontheground.agency).

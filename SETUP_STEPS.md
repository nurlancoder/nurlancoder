# GitHub Profile Setup — Checklist

Repo: github.com/nurlancoder/nurlancoder (create it first at github.com/new if it doesn't exist yet — public, same name as your username, "Add a README" checked)

## 1. Push these files to the repo root
`dark.svg`, `light.svg`, `README.md`, `.github/workflows/snake.yml`
(See WINDSURF_PROMPT.md — paste that into Windsurf's AI and it will do this step for you.)

## 2. GitHub token (for self-hosted stats)
Settings → Developer settings → Tokens (classic) → Generate new token (classic)
Note: readme-stats · Expiration: No expiration · Scope: tick `repo`
Copy it immediately — GitHub shows it once. Never share it or paste it anywhere public.

## 3. Self-host github-readme-stats
1. Fork https://github.com/anuraghazra/github-readme-stats
2. vercel.com → Sign up with GitHub → Hobby (free) plan
3. Add New… → Project → Import your fork → leave build settings alone
4. Environment Variables → name `PAT_1`, value = your token → Deploy
5. Wait ~2 min → copy your URL: `your-instance.vercel.app`
6. In README.md, replace every `github-readme-stats.vercel.app` with your instance URL

## 4. Enable Actions permissions (for the snake animation)
Repo's own Settings (not your account settings!) → Actions → General →
Workflow permissions → "Read and write permissions" → Save
URL should look like: github.com/nurlancoder/nurlancoder/settings/actions

## 5. Run the snake workflow
Once `.github/workflows/snake.yml` is pushed to `main`, check the Actions tab —
the run should go green in ~1 minute and create an `output` branch.
Until it's green, the snake image in the README will show broken — that's expected.

## 6. Verify
Open your profile, switch GitHub theme (avatar → Settings → Appearance) and reload —
both dark.svg and light.svg should render correctly.
If a change "isn't showing," it's almost always CDN cache:
open `raw.githubusercontent.com/.../file.svg?v=999`, Ctrl+F for the change, confirm it's
actually there before assuming something's broken.

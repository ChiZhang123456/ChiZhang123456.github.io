# Project Notes for Future Agents

This repository contains Chi Zhang's personal academic website. Use this file as the starting context before making future edits.

## Live Site and Repositories

- Public website: https://www.chizhang.org
- Apex domain also works: https://chizhang.org
- GitHub repository: https://github.com/ChiZhang123456/ChiZhang123456.github.io
- Git remote:
  - `origin https://github.com/ChiZhang123456/ChiZhang123456.github.io.git`
- GitHub Pages branch: `main`
- GitHub Pages folder: `/ (root)`
- Custom domain file: `CNAME`
  - Current content: `www.chizhang.org`

## Domain and DNS

The domain was purchased/managed in Cloudflare.

Cloudflare DNS should have:

- `CNAME`
  - Name: `www`
  - Target: `chizhang123456.github.io`
  - Proxy status: `DNS only`
- Apex domain `chizhang.org` A records:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
  - Proxy status: `DNS only`

Do not set the Cloudflare `www` CNAME target to the repository URL or repository name. It should point to `chizhang123456.github.io`.

## Site Structure

- `index.html`: homepage, horizontal page-based layout.
- `publications.html`: full publication list.
- `styles.css`: all layout and visual styling.
- `assets/`: deployed image assets used by the pages.
- `verify-render.cjs`: local Playwright render check, ignored by git.
- The local Chinese-named CV `.docx` file: source CV document used to verify publication titles, ignored by git.

Current homepage sections:

1. Home hero
2. Current Role / Research Focus
3. Research Highlights
4. CV

The previous personal/lifestyle "Beyond The Office" page was intentionally removed because the user wanted the site to stay research-focused.

## Deployed Assets

Only these image assets should be tracked and uploaded:

- `assets/aurora-sweden.jpg`
- `assets/portrait-library.jpg`
- `assets/paper-ion-drift.jpg`
- `assets/paper-anomalous-ion-escape.jpg`
- `assets/paper-global-energy.jpg`
- `assets/paper-3d-magnetic-field.jpg`
- `assets/paper-ulf-wave.png`
- `assets/paper-khi-ion-escape.png`

Other local `.jpg`/`.png` files are source material or previews and should not be uploaded. `.gitignore` is configured to allow only the deployed assets above.

## Key Content Decisions

- ResearchGate should appear before Google Scholar.
- Do not include BU Profile in the hero buttons.
- The email belongs on the first page: `zc199508@bu.edu`.
- The homepage should use horizontal arrow navigation, not mouse-wheel slide changes.
- The Publications nav item links to `publications.html`, not a separate homepage slide.
- Featured article DOI links should appear directly below paper titles.
- Full publication titles should match the local Chinese-named CV `.docx` file where possible.
- Do not include projects, reviewing, student advising, or unrelated service items on the website unless the user explicitly asks.

## Important External Profiles

- ResearchGate: https://www.researchgate.net/profile/Chi-Zhang-248?ev=hdr_xprf
- Google Scholar: https://scholar.google.com/citations?user=lSBqPlkAAAAJ&hl=zh-CN
- ORCID: https://orcid.org/0000-0001-9154-596X
- BU profile, outdated but referenced earlier: https://www.bu.edu/csp/profiles/chi-zhang/

## Featured Works

Featured papers currently shown on the homepage:

- Detection of magnetospheric ion drift patterns at Mars
  - DOI: https://doi.org/10.1038/s41467-023-42630-7
- Simultaneous Mars-orbit observations reveal Kelvin-Helmholtz-instability-driven bulk atmospheric ion escape
  - DOI: https://doi.org/10.1126/sciadv.aed9072
- Anomalous Transient Enhancement of Planetary Ion Escape at Mars
  - DOI: https://doi.org/10.1038/s41467-025-58351-y
- Global Energy Transport and Conversion in the Solar Wind-Mars Interaction: MAVEN Observations
  - DOI: https://doi.org/10.1029/2025JE009295
- Three-Dimensional Configuration of Induced Magnetic Fields Around Mars
  - DOI: https://doi.org/10.1029/2022JE007334
- Role of ULF Waves in Reforming the Martian Bow Shock
  - DOI: https://doi.org/10.1029/2025AV001654

Related story:

- Springer Nature Behind the Paper for the 2023 Nature Communications ion drift paper:
  - https://communities.springernature.com/posts/unveiling-the-dynamics-of-interaction-between-mars-magnetic-field-and-the-solar-wind

## Local Verification

Run the render check before pushing:

```powershell
$env:NODE_PATH='C:\Users\Win\.cache\codex-runtimes\codex-primary-runtime\dependencies\node\node_modules'
& 'C:\Users\Win\.cache\codex-runtimes\codex-primary-runtime\dependencies\node\bin\node.exe' verify-render.cjs
```

Expected result: no broken images, no horizontal overflow for `index.html` or `publications.html`.

Useful manual checks:

```powershell
git status --short --branch
git remote -v
```

After edits:

```powershell
git add index.html publications.html styles.css assets .gitignore CNAME AGENTS.md
git commit -m "Describe the website update"
git push
```

GitHub Pages can take a short time to refresh. If the live site looks stale, hard refresh the browser or wait a few minutes.

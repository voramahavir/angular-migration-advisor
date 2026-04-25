# ⚡ Angular Migration Advisor
 
> AI-powered tool that analyses your Angular project and generates a personalised migration path, breaking change report, and step-by-step action plan.
 
**[Try it live →](https://voramahavir.github.io/angular-migration-advisor)**
 
---
 
## What it does
 
Migrating between Angular major versions is non-trivial — especially across multiple version jumps. This tool takes your `package.json` (or a plain description of your app) and uses AI to give you:
 
- **A recommended migration path** — one major version at a time, with intermediate stops where needed
- **Breaking changes analysis** — specific to your versions and dependencies, with severity ratings and concrete fixes
- **A step-by-step action plan** — with time estimates for your team size
- **Expert prose analysis** — covering risks specific to your project, not generic advice
---
 
## Demo
 
![Angular Migration Advisor screenshot](./screenshot.png)
 
Try the live tool: **[voramahavir.github.io/angular-migration-advisor](https://voramahavir.github.io/angular-migration-advisor)**
 
Three example presets are built in — load one and hit Analyse to see a real result in seconds.
 
---
 
## Why I built this
 
I led an Angular modernization program at Encora Inc. — migrating a large-scale production codebase (retail application on Microsoft Surface devices) from a legacy Angular version to the latest LTS. The process taught me a lot about what engineers actually need when planning a migration:
 
- Which breaking changes are genuinely risky vs. easy to fix
- Whether to migrate one version at a time or jump directly
- How long it realistically takes for a team of a given size
- What to freeze (state layer, tests) before starting
This tool encodes that experience and surfaces it instantly for any Angular project.
 
---
 
## Tech stack
 
| Layer | Choice |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| AI | [Claude API](https://www.anthropic.com/api) (claude-sonnet) |
| Hosting | GitHub Pages |
| Fonts | Syne + Inter + JetBrains Mono (Google Fonts) |
 
No build step. No framework. No dependencies to install. Open the HTML file and it works.
 
---
 
## Running locally
 
```bash
git clone https://github.com/voramahavir/angular-migration-advisor.git
cd angular-migration-advisor
# Open index.html in your browser — that's it.
open index.html
```
 
The tool calls the Anthropic API directly from the browser. For local use, you may need to handle CORS depending on your browser environment. The live hosted version works without any configuration.
 
---
 
## How the AI prompt works
 
The tool sends a structured prompt to Claude that includes:
 
- Your current and target Angular versions
- Your full `package.json` (or app description)
- A strict JSON schema for the response
Claude returns a structured analysis covering migration path, breaking changes (with severity), action plan steps (with time estimates), and a prose expert analysis. The frontend parses and renders this as a clean, interactive UI.
 
The prompt is designed to be specific — it produces version-accurate breaking changes rather than generic Angular advice. You can view the full prompt in `index.html`.
 
---
 
## Supported version ranges
 
| From | To |
|---|---|
| Angular 12–18 | Angular 15–19 |
 
Versions 12 through 19 are currently supported. The AI analysis handles multi-hop migrations (e.g. v12 → v17) by recommending intermediate stops.
 
---
 
## Roadmap
 
- [ ] `angular.json` parsing for deeper project analysis
- [ ] Dependency-specific breaking change detection (NgRx, Angular Material, CDK)
- [ ] Export migration plan as PDF or Markdown
- [ ] Estimated bundle size impact per migration step
- [ ] GitHub Action: run migration check on PRs
PRs and issues welcome.
 
---
 
## About
 
Built by **[Mahavir Vora](https://voramahavir.github.io)** — Engineering Manager and Angular specialist with 10+ years of experience. I've led Angular modernization programs in production, managed teams of 7–10 engineers, and maintained 100% unit test coverage across major release cycles.
 
- Portfolio: [voramahavir.github.io](https://voramahavir.github.io)
- LinkedIn: [linkedin.com/in/mahavir-vora](https://linkedin.com/in/mahavir-vora)
- Email: voramahavir@gmail.com
---
 
## License
 
MIT — use it, fork it, improve it.

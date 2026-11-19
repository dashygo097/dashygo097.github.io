# dashygo097.github.io

Personal website built with Vue and TypeScript.

Run `bun run dev` to preview locally, or `bun run build` for a production build.

- `src/App.vue` is the application entry, currently rendering `HomePage`.
- `src/components/HomePage.vue` contains the introduction page and profile data. Add future page components alongside it; navigation or a router can be added when those pages exist.
- `src/components/TechGroup.vue` renders reusable tool and language groups.
- `src/components/TechIcon.vue` maps badge names to local SVG icons. Unknown technologies receive a generic code icon.
- `src/components/GitHubStats.vue` renders external statistics with fallbacks when images fail.
- `src/style.css` holds shared dark theme tokens and base styles. Layout styles are scoped to their components.

Technology artwork is stored in `src/assets/tech-icons/`. Brand icons are from [Simple Icons v16](https://github.com/simple-icons/simple-icons/tree/16.0.0) (CC0; license included there), with small custom editor, Windows, hardware, and code symbols. All icons use a muted color for the dark theme and load locally without external requests.

# Project Guidelines

## Project Goal

Build a presentation website for the French nonprofit "Génération Femmes".

Prioritize:

- French-first copy and UX labels.
- Clear nonprofit storytelling (mission, actions, impact, contact).
- Accessibility and fast loading on mobile and desktop.

## Code Style

- Follow existing Astro + TypeScript patterns.
- Keep components small and reusable in `src/components/`.
- Keep route-level pages in `src/pages/` and shared wrappers in `src/layouts/`.
- Preserve existing formatting style (tabs in `.astro` and config files).
- Reuse global tokens and typography from `src/styles/global.css` unless a task explicitly asks for a redesign.

## Architecture

- File-based routing lives in `src/pages/`.
- Shared page chrome and SEO are handled by:
  - `src/components/BaseHead.astro`
  - `src/components/Header.astro`
  - `src/components/Footer.astro`
- Site-level constants are in `src/consts.ts`.
- Content collections are configured in `src/content.config.ts`.
- Blog content currently lives in `src/content/blog/` and uses schema-validated frontmatter.

## Build and Validation

Run commands from repository root:

- `npm install`
- `npm run dev`
- `npm run build`
- `npm run preview`

Before finalizing substantial UI/content changes, run `npm run build` to catch Astro and content-schema issues.

## Conventions

- Prefer Astro native patterns over adding extra frameworks unless required.
- Use `astro:assets` (`Image`) for local optimized images when possible.
- Update `src/consts.ts` when changing site title/description to keep metadata consistent.
- Keep language attributes and copy aligned to French content goals (for example `lang="fr"` when pages are fully French).
- If changing content collection frontmatter, update schema in `src/content.config.ts` in the same task.

## Pitfalls

- Node version must satisfy `>=22.12.0` (see `package.json`).
- Image processing depends on `sharp`; environment issues often surface during `npm run build`.

## References

- Project setup and commands: `README.md`
- Astro documentation: https://docs.astro.build

# SecondBrain — Claude Instructions

## Git Workflow

- **Always create a new branch** before starting work on any issue.
  - Branch naming: `issue-<number>/<short-slug>` (e.g. `issue-1/nuxt-scaffold`)
  - Base the branch off `main`: `git checkout -b issue-N/slug origin/main`
- **Commit regularly** with clear messages referencing the issue (`refs #N`).
- **Open a pull request** to `main` when the issue is complete.
  - PR title should match the issue title.
  - PR body must include `Closes #N` so the issue auto-closes on merge.
  - Do **not** merge the PR — leave it for the user to review and merge.

## Creating GitHub Issues

Before starting any non-trivial piece of work, create a GitHub issue first.

**Every issue must include:**

1. **Title** — Short, imperative, specific. Describes *what* is being built, not *why*.
   - Good: `Notes: Add tag filtering to the notes list`
   - Bad: `Fix tags` or `Work on notes`

2. **User Story** — One sentence in the format:
   > As a [user], I want to [do something] so that [outcome].

3. **Acceptance Criteria** — A checklist of concrete, testable conditions that define "done".
   - Each item is a specific behaviour, not a vague goal.
   - Cover the happy path, edge cases, and any API routes that need to exist.
   - Example:
     - [ ] Clicking a tag chip in the notes list filters results to only notes with that tag
     - [ ] Selecting multiple tags narrows results (AND logic)
     - [ ] An "All" button clears the filter
     - [ ] Filter state is reflected in the URL query string

4. **Label** — Always apply one or more labels (`notes`, `tasks`, `journal`, `goals`, `ai`, `dashboard`, `setup`, `database`, `auth`, `deploy`).

**Rules:**
- One issue = one focused piece of work. Do not bundle unrelated changes.
- If a task is too large to estimate, break it into child issues.
- Do not create an issue for something already covered by an existing open issue.

## Stack
- Nuxt 3 + TypeScript + Vue
- Drizzle ORM + Turso (LibSQL/SQLite)
- TailwindCSS + shadcn-vue
- Tiptap (markdown editor)
- Claude API (Anthropic SDK) for AI features
- Deployed on Vercel

## Dev Commands
- `npm run dev` — start dev server
- `npm run build` — production build
- `npx drizzle-kit generate` — generate DB migrations
- `npx drizzle-kit migrate` — apply migrations

## Environment Variables
Required in `.env`:
- `TURSO_DATABASE_URL`
- `TURSO_AUTH_TOKEN`
- `ANTHROPIC_API_KEY`

<!-- BEGIN:nextjs-agent-rules -->

## This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

## Coding rules

All code in this project must follow these rules.

| Rule                               | Bad                               | Good                                      |
| ---------------------------------- | --------------------------------- | ----------------------------------------- |
| No `any`                           | `(data: any)`                     | `(data: Post)`                            |
| Names say what it is               | `d`, `flag`, `handle()`           | `posts`, `isLoading`, `savePost()`        |
| Return early                       | 3 nested `if`                     | `if (!user) return;` then the main code   |
| Small files                        | one 600-line page                 | one component per file, under 200 lines   |
| Check input on the server          | trust `req.body`                  | check it with `zod` first                 |
| Catch errors from outside services | app crashes when Pinecone is slow | `try/catch`, friendly message to the user |
| Never show raw errors              | "PostgresError: relation…"        | "Could not save. Try again."              |
| No leftover logs                   | `console.log(user)` in a commit   | delete it before commit                   |

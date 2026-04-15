# 🚨 AI Mistake Ledger

## Logged Mistakes

**Format:** `[DD-MM-YYYY] Mistake: <What went wrong> -> Fix: <How to do it correctly next time>`

- **[14-04-2026] Mistake:** Attempted to use server-side `redirect()` inside a Next.js Layout file, causing an infinite render loop. -> **Fix:** Always handle auth redirects in middleware or via client-side routing guards.
- **[14-04-2026] Mistake:** Instantiated `new PrismaClient()` directly in an API route, exhausting database connections. -> **Fix:** ALWAYS import the singleton instance from `src/lib/db.ts`.

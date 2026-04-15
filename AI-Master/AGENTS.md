# Agent Operating System & Coding Framework

## 1. Context & Token Management (Zero Bloat)
CRITICAL: Do not preemptively load files. To prevent token bloat and context collapse (max 200k tokens), use your Read tool ONLY on a need-to-know basis:
- `@.ai/mistakes.md`: Read before starting to avoid repeating errors. You may repeat a mistake a maximum of ONE time.
- `@.ai/commands.md`: Read for preferred short CLI commands (Good vs. Bad).
- `@.ai/index.md`: Read to locate the specific project workspace, docs, and plans.
- `@.ai/docs/`: Rely on these localized, committed docs before web searching.

## 2. Continuous Learning (Updating Memory)
You are responsible for actively maintaining your memory files to ensure one-shot efficiency:
- **Mistakes (`@.ai/mistakes.md`):** If you write failing code, cause a bug, or the human corrects you, immediately append a concise entry. 
  - *Format:* `[DD-MM-YYYY] Mistake: <what went wrong> | Fix: <how to do it right>`
- **Commands (`@.ai/commands.md`):** Append clean, efficient CLI commands to the "Good" list. If a command fails, append it to the "Bad" list.
  - *Format:* `✅ GOOD: <command>` OR `❌ BAD: <command>`

## 3. Core Constraints (The "Never" List)
- **Blindspots:** NEVER use, read, or modify the `dist/` folder.
- **Git & Build:** NEVER push code or build without explicit human say-so. 
- **Bash & Scripting:** NEVER write bash scripts or use brittle commands like `head`, `tail`, or `sed` to edit files.
- **CLI Testing:** NEVER ask the human to run non-destructive/reversible CLI commands. Run them yourself, test one by one, and report findings.
- **Database Rules:** NEVER guess destructive DB actions. Test on a single record/sub-schema first and get explicit approval. Resetting the whole DB is human-only (output the command for the human to copy and run at the end of the session).

## 4. The API-First, Zero-Human Pipeline
Achieve a one-shot solution module-by-module.
1. **Plan & Research:** Duplicate the templates from `.ai/projects/_templates/` into your specific project folder (e.g., `.ai/projects/auth/`). **You must explicitly prefix every file** (e.g., `auth_plan.md`, `auth_analysis.md`, `auth_context.md`).
2. **State Matrices:** Define user types, views, and states as a Markdown table with checkmarks (✅ / ❌) in your plan before writing UI or Auth code.
3. **API-First Implementation:** Build backend logic and API routes completely independent of the frontend.
4. **End-to-End Agent Testing:** Test features fully via CLI (create accounts, approve tokens, list data, verify codes via `console.log`) WITHOUT using the frontend.
5. **Living Documents:** Actively update `[project]_plan.md` and `[project]_analysis.md` as tasks evolve.
6. **Human Verification:** Instruct the human tester with simple, copy-pasteable commands and expected outputs.
7. **Frontend/UI:** Only build the UI after the API is human-verified. Implement strict caching rules for static vs. dynamic data to prevent re-renders and DB spam.

## 5. Branching & Finalization
- **Type Checking:** Always run code type check via the project's `bun` build script.
- **Strict Branch Naming:** ALWAYS push code to a separate branch: `{dev}/{mainfeature}-{subfeature}-{DD-MM-YYYY}-{follownooftheday}`.
- Focus ONLY on the current feature at hand.

## 6. Subagent Handoff (Bug Fixing)
If a bug arises outside the current context window, DO NOT fix it here. Log it, and instruct the human to kick off a subagent specifically for that bug using a fast model.
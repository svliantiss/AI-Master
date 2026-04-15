# 🧠 AI Context Architecture & Operating System

This directory is the centralized "brain" and operational memory for our AI coding agents (OpenCode, Claude Code, Cursor, etc.). 

It is designed to solve the biggest pain points of AI-assisted development: **token bloat, context collapse (AI amnesia), and repetitive mistakes.** By forcing the AI into a strict, isolated, API-first workflow, we guarantee efficient use of the 200K token window and achieve "one-shot" feature generation with minimal human intervention.

## 🏗️ Directory Structure

```text
.
├── AGENTS.md        # The Master Directives. OpenCode reads this automatically.
├── index.md         # The Master Map. Tracks all active, pending, and completed projects.
├── mistakes.md      # The AI's append-only ledger of past errors to never repeat.
├── commands.md      # Verified Good/Bad CLI commands for the AI to use.
├── docs/            # Localized, committed vendor docs (e.g., Prisma, Better Auth).
├── templates/       # Boilerplate files for new features.
│   ├── _analysis_template.md
│   ├── _context_template.md
│   └── _plan_template.md
└── projects/        # Isolated workspaces for active context windows.
    └── example/     # Every feature gets its own folder and explicitly named files.
        ├── example_plan.md
        ├── example_analysis.md
        └── example_context.md
```

---

## ⚙️ Core Philosophy

1. **Zero Bloat (Lazy Loading):** The AI is forbidden from doing wildcard searches across the codebase. It uses `index.md` as a map to load *only* the specific files and docs it needs for the current task.
2. **API-First & Zero-Human Testing:** The AI must build the backend, database models, and API routes first. It must test these entirely via CLI (using `console.log` to read tokens/OTPs) before it is allowed to write a single line of UI code.
3. **Continuous Learning:** When the AI makes a mistake or writes a great script, it must actively update `mistakes.md` and `commands.md`. 
4. **Isolated Workspaces:** Every feature is planned and executed inside its own `projects/<feature>/` folder. This keeps the 200K token window razor-sharp.

---

## 🚀 The Developer Workflow (How to use this)

Because `AGENTS.md` handles all the heavy lifting, kicking off complex features from your terminal or phone requires almost zero prompting.

### 1. Start a New Feature (Main Session)
Open a new chat and trigger the workflow:
> "Read `AGENTS.md`. We are building the `/auth` project. Duplicate the templates into `projects/auth/`, prefix the filenames with `auth_`, and fill them out. Stop so I can review the UI Matrix and plan."

### 2. The Execution Loop
Once you approve the plan, tell the AI to go:
> "Plan approved. Execute the API-First implementation. Run the CLI tests yourself and give me the copy-paste commands to verify when you are done."

### 3. Handle Bugs (Sub-Agent Detour)
**Never fix out-of-scope bugs in your main feature chat.** If you find a bug in an older component, preserve your token window by opening a *new* chat:
> "Read `AGENTS.md` and `mistakes.md`. Checkout branch `dev/dashboard-fix`. Fix the layout bug on the nav component, test it, and log the root cause in `mistakes.md`."

---

## 📝 The Project Files Explained

When a new feature is spun up, the AI duplicates the files in `templates/`. These become living documents for that specific feature:

* **`_plan.md`:** The living checklist. It contains a strict **UI State & Behavior Matrix** (mapping exact UI outcomes to backend conditions) and a status table tracking execution from API to UI.
* **`_analysis.md`:** The architectural blueprint. It holds the caching strategy (Static vs. Dynamic data) and the exact Acceptance Criteria the AI will use to test its own code.
* **`_context.md`:** The anti-hallucination vault. The AI stores real, working code snippets and direct documentation links here so it never has to guess or re-read massive files.

## ⚠️ Human Responsibilities
* **Destructive DB Actions:** The AI is instructed to halt and ask for your explicit permission before running destructive migrations or schema drops. 
* **Raw Docs:** When adding new libraries, convert their docs to markdown and drop them into the `docs/` folder, then link them in `index.md`.
* **Final Review:** The AI will build, test, and type-check the code, but the human must approve the final push to the `{dev}/...` branch.# AI-Master

# 🚀 AI Project Setup Prompt

Clone the `AI-Master` repository into your project root to set up the `.ai/` workflow and follow these steps:

## 📋 Quick Setup Commands

```bash
# 1. Copy the .ai folder to your project
git clone [https://github.com/svliantiss/AI-Master.git](https://github.com/svliantiss/AI-Master.git)

# 2. Put the agents.md in the root of this project
cp AI-Master/AGENTS.md ./agents.md

# 3. Rename the AI-Master folder to .ai
mv AI-Master .ai

# 4. Update index.md with your project details
# Edit: Project Goal, Tech Stack, File Locations

# 5. Clear the mistakes log (start fresh)
echo "# 🚫 Mistakes Log" > .ai/mistakes.md

# 6. For new projects, create a project folder
mkdir -p .ai/projects/my-feature
cp .ai/projects/_templates/* .ai/projects/my-feature/
# Rename files: my-feature_plan.md, my-feature_analysis.md, my-feature_context.md
```

## 🎯 Usage Instructions

**BEFORE starting work:**
1. Read `.ai/mistakes.md` - Don't repeat past errors
2. Read `.ai/commands.md` - Use approved CLI commands only
3. Read `.ai/index.md` - Understand project structure
4. Read your project's plan/analysis/context files

**DURING work:**
- Update `[project]_plan.md` as you complete tasks
- Add mistakes immediately to `mistakes.md`
- Add working commands to `commands.md`
- Never use sed/head/tail - use Read+Edit tools only

**AFTER work:**
- Mark tasks complete in plan.md
- Update status in index.md (🟢 Active → 🔵 Completed)
- Build passes: `npm run build` or `bun run tsc --noEmit`

## 📁 File Structure

```text
.ai/
├── AGENTS.md          # Agent rules & constraints (READ FIRST)
├── commands.md        # Approved CLI commands
├── index.md           # Project index & quick reference
├── mistakes.md        # Learning log (update as you go)
├── docs/              # Vendor docs (resend, prisma, etc)
└── projects/
    ├── _templates/    # Copy these for new projects
    └── [feature]/     # One folder per feature
        ├── [feature]_plan.md      # Scope & tracker
        ├── [feature]_analysis.md  # Architecture & tests
        └── [feature]_context.md   # Code snippets & docs
```

## ⚡ Critical Rules

1. **API-First:** Build backend before UI
2. **No CLI Editing:** Never use sed/head/tail on files
3. **Lazy Loading:** Only read files you need right now
4. **Lowercase Roles:** `role === "owner"` not `"Owner"`
5. **Update Memory:** Log mistakes immediately
6. **Test Before UI:** Verify APIs with curl/CLI first

## 🔗 Key References in index.md

- Core file locations (database, auth, API routes)
- Database models
- Workspace rules & permissions
- Recent changes log
- Quick reference tables

---

**Start by reading:** `agents.md` → `.ai/index.md` → Your project's `[feature]_plan.md`
# 🗺️ Global Project Index

## 1. Full Project Overview
- **Project Goal:** <DEFINE_ENTIRE_CODEBASE_PURPOSE> *(e.g., A SaaS platform for managing workspaces, automated billing, and user collaboration.)*
- **Core Tech Stack:** Next.js (App Router), TypeScript, Bun, Prisma, Better Auth, TailwindCSS.
- **Global Rules:** API-First architecture (test backend before UI), strict `DD-MM-YYYY HH:mm` date formatting, zero human bash execution.

---

## 2. Projects 
| Status | Project Name | Description | Plan | Analysis | Context |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **🟢 Active** | Auth (`/auth`) | Email/OTP login flow with workspace creation | `@.ai/projects/auth/auth_plan.md` | `@.ai/projects/auth/auth_analysis.md` | `@.ai/projects/auth/auth_context.md` |
| **🟡 To-Do** | Dashboard (`/dashboard`) | Main user workspace and metric overview | *Not started* | *Not started* | *Not started* |
| **🟡 To-Do** | Settings (`/settings`) | User profile and billing management | *Not started* | *Not started* | *Not started* |
| **🔵 Completed**| MVP Scaffolding | Initial Next.js setup, DB schema, and UI library | `@.ai/projects/mvp/mvp_plan.md` | `@.ai/projects/mvp/mvp_analysis.md` | `@.ai/projects/mvp/mvp_context.md` |

---

## 3. Global Documentation & Core Files
**Core Codebase Locations:**
- **Database:** `src/lib/db.ts` *(Prisma Singleton)*
- **Auth Config:** `src/lib/auth.ts` *(Better Auth init)*
- **API Routes:** `src/app/api/`
- **Middleware:** `src/middleware.ts`

**Vendor Documentation Vault (`.ai/docs/`):**
- `@.ai/docs/better-auth-core.md`
- `@.ai/docs/resend-api.md`
- `@.ai/docs/prisma-schema.md`

---

## 4. AI Maintenance Protocols
1. **Lazy Loading:** Never wildcard search. ONLY load the files explicitly linked in the table above for your assigned project.
2. **Project Initialization:** When starting a "To-Do" project, duplicate the files from `@.ai/projects/_templates/` into its new folder, name them explicitly with the project prefix, fill in the description, and update the table above to **🟢 Active**.
3. **Project Completion:** When a branch is merged and human-approved, change its table status from Active to **🔵 Completed**.
4. **Ingesting Docs:** When the human adds a new raw markdown file to `.ai/docs/`, add it to Section 3.
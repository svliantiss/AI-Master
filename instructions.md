# 🚀 The `AI` Engine: Developer Execution Workflow

Welcome to the team. We do not use AI as a generic chatbot. We use it as a highly disciplined, API-first execution engine operating within a strict 200K token context window. 

To prevent AI amnesia, hallucinated code, and token bloat, we follow a rigorous 10-step execution pipeline. You will spend most of your time reviewing Markdown files in Obsidian and testing CLI outputs, allowing the AI to handle the heavy coding logic seamlessly.

---

## Phase 1: Setup & Grounding

### 1. Initialize the AI
When adding the AI to a current or brand-new project, ensure the `ai/` folder architecture and `AGENTS.md` (in the root) are present. 

### 2. Reload the Session
Always reload your current window or IDE session to ensure the AI reads `AGENTS.md` natively and locks in its system instructions before you start typing.

### 3. Explore & Map Primitives
Instruct the AI to explore the codebase and fill out the primitive files (`ai/index.md`, basic `ai/commands.md`, etc.). 
* **Human Action:** Review the generated primitives in Obsidian. Optimize the global index and ensure the tech stack and architectural paths are 100% accurate before proceeding.

### 4. Load Vendor Documentation
Before starting any specific task, identify the third-party tools the AI will need (e.g., Mollie, Prisma, Better Auth). Download their documentation as raw Markdown files and place them in `ai/docs/`.
* *Why?* We never let the AI blindly browse the web during a coding task. It wastes tokens and pulls outdated info.

---

## Phase 2: Project Scoping & Planning

### 5. Scope the Project (The 200K Token Rule)
Instruct the AI to create a new project folder (e.g., `.ai/projects/auth/`). **You must limit the scope to a single topic or page.**
* **Scope tightly:** Do not group `/auth` and `/onboarding` together. If you finish `/auth` and have context window left, you can append onboarding. Otherwise, treat it as a second project.
* **The API-First Mandate:** The AI must *always* build the API route and test it via CLI itself before committing to any UI work. You will spend your time interacting with the plans in Obsidian and executing CLI tests. This completely eliminates frontend backtracking.
* *Note: With proper context loading and strict alignment to this rule, the AI can finish complex tasks into a working product in a single session.*

### 6. Define the End Goal (The Kickoff Prompt)
Your prompt dictates the plan. Provide a highly specific end goal with all main points included.
> **Example Prompt:** "Create the `/auth` page. The user signs in with an email and verification code, then signs up or goes straight to the verification code input. They are then redirected to their most recent workspace, or the system creates a new one for them as the owner on the `/home` route. We use Resend & Better Auth. Ensure login codes output to `console.log` for easy copy-pasting during testing."

### 7. Lock in the Analysis & Acceptance Criteria
Once the `_plan.md` tasks are agreed upon, move to the `_analysis.md` file. 
* This file acts as the automated test suite. It defines exactly how the backend will be verified before UI begins.
* **Living Document:** If you adjust or add new features during development, the AI must update this analysis file simultaneously.

---

## Phase 3: Context Loading & Execution

### 8. Isolate the Context
Before the AI writes any executable code, it must use the `_context.md` file to research the repo, existing codebase examples, and the docs you provided in Step 4. 
* The AI places exact copies of verified code snippets into `_context.md`.
* *Why?* If the AI searches the codebase *during* development, it will likely read half-finished or broken code. `_context.md` acts as a locked, pristine reference vault.

---

## Phase 4: Continuous Learning & Memory

### 9. Actively Manage Commands
While working, actively train the AI. 
* If the AI generates a brilliant, token-efficient command (e.g., a perfect `curl` loop piped into `jq`), tell it: *"Record that to the commands file as a good example."*
* If it tries to use a brittle script or fails, tell it: *"Record that as a bad command to avoid."*

### 10. Log Mistakes & Share Globally
When the AI makes a logic error or syntax mistake more than once (or across different sessions), explicitly instruct it to record the error and the fix in `.ai/mistakes.md`.
* **Team Alignment:** Periodically share your project's `.ai/mistakes.md` with the wider development team. This allows us to compile a master list of global mistakes to avoid across the entire company.

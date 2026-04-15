# 📋 Project Plan: <PROJECT_NAME>

## 1. Project Scope
- **End Goal:** <DEFINE_END_GOAL_IN_DETAIL>
- **Strict Out-of-Scope:** <DEFINE_WHAT_NOT_TO_BUILD_TO_PREVENT_BLOAT>
- **Target Branch:** `{dev}/<MAINFEATURE>-<SUBFEATURE>-<DD-MM-YYYY>-<NO>`

---

## 2. UI State & Behavior Matrix
| User Role | <CONDITION_1_E.G._HAS_PRO> | <CONDITION_2_E.G._VERIFIED> | UI Badge | UI Button | Tooltip |
| :--- | :--- | :--- | :--- | :--- | :--- |
| <ROLE> | <TRUE/FALSE> | <TRUE/FALSE> | "<TEXT_OR_STATE>" | "<TEXT_OR_ACTION>" | "<TEXT_OR_NA>" |
| <ROLE> | <TRUE/FALSE> | <TRUE/FALSE> | "<TEXT_OR_STATE>" | "<TEXT_OR_ACTION>" | "<TEXT_OR_NA>" |

---

## 3. Execution Tracker
| Status   | Phase           | Task Description                   | Verification / Expected Output             |
| :------- | :-------------- | :--------------------------------- | :----------------------------------------- |
| 🟡 To-Do | **API (DB)**    | <TASK_E.G._Create_Auth_Schema>     | Prisma push succeeds safely                |
| 🟡 To-Do | **API (Logic)** | <TASK_E.G._Build_OTP_Route>        | Route handles request logic                |
| 🟡 To-Do | **API (Test)**  | <TASK_E.G._Agent_Self_Test>        | Console outputs OTP, verifies successfully |
| 🟡 To-Do | **Human**       | Verify Backend via CLI             | Human confirms HTTP 200 / JSON             |
| 🟡 To-Do | **UI (Layout)** | <TASK_E.G._Build_Auth_Form>        | Matches UI Matrix perfectly                |
| 🟡 To-Do | **UI (Logic)**  | <TASK_E.G._Wire_to_API>            | End-to-end functionality working           |
| 🟡 To-Do | **UI (Cache)**  | <TASK_E.G._Implement_Static_Cache> | No unnecessary re-renders in dev tools     |
| 🟡 To-Do | **Finalize**    | `bun run typecheck` & Branch       | Clean build, code is pushed                |

---

## 4. Human Verification Command (Phase Handoff)
**Initiate Flow:**
```bash
<INSERT_EXACT_CURL_OR_CLI_COMMAND>
```

**Verify/Confirm Flow:**
```bash
<INSERT_EXACT_VERIFICATION_COMMAND>
```
**Expected Outcome:** `<EXACT_JSON_RESPONSE_OR_DB_STATE>`
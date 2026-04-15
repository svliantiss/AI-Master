# 🧪 Analysis & Testing Strategy: <PROJECT_NAME>

## 1. Architecture & Performance
- **Proposed Implementation:** <INSERT_BRIEF_PROPOSAL>
  *(Agent: Briefly describe the one-shot logic flow for this feature.)*
- **Data & Caching Rules:** <INSERT_CACHING_RULES>
  *(Agent: Explicitly state how static vs. dynamic data will be handled to prevent frontend re-renders and excessive DB requests.)*

## 2. Agent Acceptance Criteria (API/CLI Level)
### Task: <SPECIFIC_ROUTE_OR_FEATURE_NAME>
- **Pre-condition:** <STATE_BEFORE_ACTION_E.G._"New user with no workspace">
- **Action (Agent):** <EXACT_CLI_COMMAND_OR_API_CALL_YOU_WILL_RUN>
- **Expected Result:** <EXACT_EXPECTED_HTTP_STATUS_AND_DB_STATE>
- **Edge Cases to Check:** <LIST_EDGE_CASES_E.G._"Invalid OTP", "Missing Token">

### Task: <SPECIFIC_ROUTE_OR_FEATURE_NAME>
- **Pre-condition:** <STATE_BEFORE_ACTION>
- **Action (Agent):** <EXACT_CLI_COMMAND_OR_API_CALL_YOU_WILL_RUN>
- **Expected Result:** <EXACT_EXPECTED_HTTP_STATUS_AND_DB_STATE>
- **Edge Cases to Check:** <LIST_EDGE_CASES>

## 3. Destructive DB Action Protocol
- **Commands Planned:** <LIST_DESTRUCTIVE_COMMANDS_E.G._"Prisma DB Push">
- **Dummy Record/Sub-Schema Test:** (Yes / No / N/A)
- **Human Approval Status:** (Pending / Approved)

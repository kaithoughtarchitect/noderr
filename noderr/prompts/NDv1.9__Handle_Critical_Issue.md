# Noderr v1.9: Handle Critical Issue

## Critical Issue Report
**Affected Component:** [NodeID/Component/System]
**Severity:** [Blocking/High/Medium]
**Issue Description:** [Detailed description of what's broken]

---

## Your Mission
You have identified or been assigned a critical issue. Your task is to use this systematic protocol to triage the issue, perform a root cause analysis, and propose a clear resolution plan. Your actions are governed by the Noderr v1.9 methodology.

---

### Triage & Analysis Protocol

#### Step 1: Assess Impact & Contain
*   Analyze the immediate impact: Is data integrity at risk? Are users affected?
*   Determine if immediate containment is necessary (e.g., disabling a feature, restricting access).

#### Step 2: Document the Issue in `noderr/noderr_log.md`
*   Create a comprehensive `Issue` entry in `noderr/noderr_log.md`. The entry **MUST** use the following format and an environment-sourced timestamp:
    ```markdown
    ---
    **Type:** Issue
    **Timestamp:** [Generated Timestamp]
    **NodeID(s):** [Affected NodeID(s)]
    **Logged By:** AI-Agent
    **Severity:** [Blocking/High/Medium]
    **Details:**
    - **Issue Summary:** [One-line description of the problem].
    - **Discovery Context:** [How the issue was found].
    - **Symptoms & Impact:** [User-visible symptoms, features broken, data integrity risk].
    - **Technical Details / Logs:** [Any specific error messages, stack traces, or logs].
    - **Current Status:** Under Investigation
    ---
    ```

#### Step 3: Update `noderr_tracker.md` Status
*   For the primary affected `NodeID`, change its `Status` to `[ISSUE]`.
*   Add a note in the "Notes / Issues" column referencing the issue log timestamp.

#### Step 4: Root Cause Analysis
*   Gather all relevant information: error logs, recent code changes (from `git log` and `noderr/noderr_log.md`), database state, etc.
*   Systematically analyze the data to determine the root cause of the failure.

---

### Resolution Protocol

#### Step 5: Propose Resolution Approach
*   Based on your analysis, recommend one of the following resolution paths to the Orchestrator.

| Approach | Conditions | Noderr Protocol |
| :--- | :--- | :--- |
| **A. Micro-Fix** | Root cause is identified, fix is small, localized, and has no ripple effects. | Use the **`NDv1.9__Execute_Micro_Fix.txt`** protocol. This will result in a single `fix:` commit. |
| **B. Targeted Repair** | The issue is contained within one or more components and requires code changes. | Initiate the full **Noderr Loop** with a `PrimaryGoal` to resolve the issue. This will involve proposing a Change Set, updating specs, and will result in a `fix:` or `feat:` commit. |
| **C. Architectural Revision** | The issue is caused by a fundamental design flaw affecting multiple nodes. | Initiate the full **Noderr Loop** as with a Targeted Repair, but with a larger, more comprehensive Change Set that addresses the architectural flaw. |

#### Step 6: Present Resolution Plan
*   Present your findings and the recommended resolution approach to the Orchestrator.
*   If the full Noderr Loop is required, your next step after approval will be to use the `NDv1.9__[LOOP_1A]__Propose_Change_Set.txt` prompt.

#### Step 7: (Optional) Update Log with Resolution Plan
*   Once the plan is approved, you may be instructed to log an `IssueUpdate` entry in `noderr/noderr_log.md`:
    ```markdown
    ---
    **Type:** IssueUpdate
    **Timestamp:** [Generated Timestamp]
    **NodeID(s):** [Affected NodeIDs]
    **Logged By:** AI-Agent
    **Details:**
    - Root cause analysis complete for issue logged at [previous timestamp].
    - **Root Cause:** [Identified cause].
    - **Resolution Approach:** [Chosen approach: Micro-Fix / Noderr Loop].
    - **Next Action:** [e.g., "Awaiting Micro-Fix execution.", "Proceeding to LOOP_1A to propose Change Set."].
    ---
    ```

---

## After Resolution
*   A successful **Micro-Fix** will be logged and committed. The `[ISSUE]` status should then be cleared from the tracker.
*   A successful **Noderr Loop** will result in the affected nodes being moved to `[TESTED]`, with a full `ARC-Completion` log entry detailing the fix.

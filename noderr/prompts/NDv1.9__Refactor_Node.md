# Noderr v1.9: Refactor Node

**Target NodeID:** [The NodeID to be refactored, e.g., `API_UserSearch`]
**Refactoring Goal:** [The specific goal, e.g., "Improve performance by optimizing database queries"]

---

## Your Mission
You have been assigned a technical debt task to refactor the specified `TargetNodeID`. Your goal is to improve the internal quality of the code (e.g., performance, readability, simplicity) **without changing its external behavior or interfaces.**

**CRITICAL RULE: The functional contract of the node, as defined by its existing ARC Verification Criteria, MUST NOT change. All existing tests and criteria must still pass after the refactoring is complete.**

---

### Pre-Flight Check
Before proceeding, confirm the following:
*   The `TargetNodeID` is in a stable, `[VERIFIED]` state in `noderr/noderr_tracker.md`.
*   The goal is purely internal improvement, not adding features or fixing functional bugs. If this is not the case, **STOP** and inform the Orchestrator that a different protocol is required.

---

### Refactoring Protocol

#### Phase 1: Planning & Setup
1.  **Initiate Work:**
    *   In `noderr/noderr_tracker.md`, find the row for the `TargetNodeID`. Change its `Status` from `[VERIFIED]` to `[WIP]` and assign a new, unique `WorkGroupID` (e.g., `refactor-<timestamp>`).
2.  **Review & Plan:**
    *   Thoroughly review the existing code for the `TargetNodeID`.
    *   Review its spec at `noderr/specs/[TargetNodeID].md`, paying close attention to the `ARC Verification Criteria`. These are your success metrics.
    *   Develop a clear internal plan for the refactoring.

#### Phase 2: Implementation & Verification
1.  **Execute Refactoring:**
    *   Incrementally apply your planned improvements to the code.
    *   Ensure all existing functionality is preserved.
2.  **Full ARC-Based Verification:**
    *   After refactoring, conduct a **full verification** against the *existing* `noderr/specs/[TargetNodeID].md`.
    *   All original `ARC Verification Criteria` **must** pass. This proves there have been no functional regressions.
    *   Run all associated unit and integration tests.
    *   Iterate on your refactoring until the code is improved AND all verification checks pass.

#### Phase 3: Documentation & Final Commit
1.  **Update Specification (If Necessary):**
    *   If the internal "Core Logic" was significantly changed (e.g., a different algorithm is now used), update that section of the spec to reflect the new, cleaner approach.
    *   **Do not change the Interfaces or ARC Verification Criteria sections.**
2.  **Log Operation:**
    *   Prepend a `RefactorCompletion` entry to `noderr/noderr_log.md`. The entry **MUST** use the following format and an environment-sourced timestamp:
        ```markdown
        ---
        **Type:** RefactorCompletion
        **Timestamp:** [Generated Timestamp]
        **WorkGroupID:** [The WorkGroupID for this refactor]
        **NodeID(s):** [TargetNodeID]
        **Logged By:** AI-Agent
        **Details:**
        - **Goal:** [Original refactoring goal].
        - **Summary of Improvements:** [List of specific improvements made, e.g., "Replaced N+1 query with a single JOIN", "Extracted duplicated logic into a helper function"].
        - **Verification:** Confirmed that all original ARC Verification Criteria for the node still pass, ensuring no functional regressions.
        ---
        ```
3.  **Update Tracker & Finalize:**
    *   In `noderr/noderr_tracker.md`:
        *   Find the row for `TargetNodeID`, change its `Status` back to `[VERIFIED]`, and clear its `WorkGroupID`.
        *   If a `REFACTOR_[TargetNodeID]` task exists, **delete that entire row** from the tracker.
4.  **Final Commit:**
    *   Commit all changes (code, spec updates, log, tracker) with a descriptive `refactor:` message (e.g., `refactor(API_UserSearch): Optimize query performance`).

### Final Report
*   Once all steps are complete, provide a concise confirmation report.
> "✓ Refactoring of `[TargetNodeID]` is complete. The technical debt task has been resolved, logged, and committed. The tracker has been updated."

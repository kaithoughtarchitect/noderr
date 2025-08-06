# Noderr v1.9: Execute Micro-Fix

**Target:** [NodeID or specific file path]
**Issue:** [Brief, one-line description of the small change needed]

---

## Your Mission
You have been instructed to perform a "Micro-Fix." This protocol is for small, localized changes that do not alter system architecture or component interfaces.

**CRITICAL RULE: Before proceeding, confirm this task qualifies as a Micro-Fix.** It must be a small change (e.g., < 50 lines), have no ripple effects, and require no spec updates. If it does not qualify, **STOP** and inform the Orchestrator that the full Noderr loop is required.

**Reference:** Your actions are governed by the "Micro-Fix Protocol" in `noderr_loop.md`.

---

### Execution Protocol

1.  **Implement Fix:**
    *   Make the small, targeted change precisely as requested.

2.  **Quick Verification:**
    *   Perform a focused check to confirm the fix resolves the described issue and introduces no regressions in the immediate vicinity of the change.

3.  **Log Operation (Ref: `noderr_loop.md` - Step 4.3):**
    *   Prepend a `MicroFix` entry to `noderr_log.md`. The entry **MUST** use the following format and an environment-sourced timestamp:
        ```markdown
        ---
        **Type:** MicroFix
        **Timestamp:** [Generated Timestamp]
        **NodeID(s)/File:** [TargetNodeID or file_path]
        **Logged By:** AI-Agent
        **Details:**
        - **User Request:** [Orchestrator's brief issue description].
        - **Action Taken:** [Brief description of change made].
        - **Verification:** [Brief verification method/outcome].
        ---
        ```

4.  **Commit Fix (Ref: `noderr_loop.md` - Step 4.4):**
    *   Commit the change to version control with a descriptive `fix:` message (e.g., `fix: correct label on login button`). Use the `git` command specified in your `environment_context.md`.

### Final Report

*   Once all steps are complete, provide a concise confirmation report.

**Example Response:**
> "✓ Micro-Fix completed for `[Target]`.
> *   **Change:** Corrected the CSS padding on the main header.
> *   **Verification:** Visually confirmed the alignment is now correct.
> *   **Documentation:** Log entry added and a `fix:` commit has been made.
> 
> Awaiting next `PrimaryGoal`."

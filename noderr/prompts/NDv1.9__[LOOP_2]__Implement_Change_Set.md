# Noderr v1.9: [LOOP 2] Authorize Implementation

**WorkGroupID for Implementation:**
[Orchestrator: Re-state the `WorkGroupID` that you have reviewed and are now approving for implementation. This confirms all associated specs are approved.]

**WorkGroupID:** `[wip-timestamp-to-implement]`

---

## Your Mission
You are authorized to begin the core development phase for the specified `WorkGroupID`. All associated specifications are approved.

Your task is to autonomously execute the planning, committing, implementation, and verification cycle. Your work on this prompt begins at **Step 4** of the `noderr_loop.md` and is considered complete only after **Step 6** has passed successfully.

**Reference:** Your actions are governed by `noderr_loop.md`, executing the sequence from **Step 4 (ARC-Principle-Based Planning)** through to the completion of **Step 6 (ARC-Based Verification)**.

---

### Execution Protocol

1.  **Plan & Commit (Step 4):**
    *   Develop your internal implementation plan for the entire Change Set.
    *   **CRITICAL CHECKPOINT:** After developing your plan, evaluate its complexity. If the plan is exceptionally complex or high-risk, you **MUST PAUSE** now and present the plan for Orchestrator review as per Step 4.2 of the loop. If the plan is straightforward, proceed.
    *   Perform the **Pre-Implementation Commit** as per Step 4.3.

2.  **Implement (Step 5):**
    *   Execute your plan, creating and modifying all necessary code to fulfill the specs for the *entire* Change Set.

3.  **Verify (Step 6):**
    *   Conduct a full ARC-Based Verification of the *entire* Change Set, following the iterative "fix and re-verify" cycle as detailed in `noderr_loop.md`.

### Reporting

*   **On Success:** Once the entire Change Set has passed all verification steps defined in Step 6, report your success and readiness for finalization.
    *   **Success Report:**
    > "Implementation and ARC-Based Verification for `WorkGroupID: [ID]` (Steps 4-6) is complete. All code has been written, and all tests and ARC criteria have passed. The Change Set is now ready for the finalization phase. Awaiting the `NDv1.9__[LOOP_3]__Finalize_And_Commit.md` command."

*   **On Blocker:** If you pause at the planning checkpoint, or encounter an unresolvable issue, report the specific blocker.
    *   **Blocker Report:**
    > "Execution paused for `WorkGroupID: [ID]`. [Clearly describe the blocker...]"

### Final State & Next Prompt

*   Upon successful completion, you will **PAUSE**.
*   The next and final command from the Orchestrator for this `WorkGroupID` will be **`NDv1.9__[LOOP_3]__Finalize_And_Commit.md`**.

---

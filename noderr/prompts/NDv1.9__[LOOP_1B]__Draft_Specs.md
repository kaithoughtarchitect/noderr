# Noderr v1.9: [LOOP 1B] Authorize Change Set & Draft Specs

**Confirmed Change Set:**
[Orchestrator: Copy and paste the *exact* Change Set that the agent proposed and you are approving. This serves as the official, unambiguous authorization.]

*   **New Nodes to Create:**
    *   `[NodeID_A]`
    *   `[NodeID_B]`
*   **Existing Nodes to be Modified:**
    *   `[NodeID_C]` (Status: `[VERIFIED]`)
    *   `[NodeID_D]` (Status: `[TODO]`)

---

## Your Mission
The Change Set has been confirmed. Your first action is to **update the `noderr_tracker.md`** to reflect the start of this work. Then, proceed to draft or refine all required specifications directly in their respective files.

**CRITICAL RULE: Your work in this phase is strictly limited to updating Noderr's own project and specification files (`.md` files). You MUST NOT write or modify any application source code (e.g., `.js`, `.py`, `.html` files).**

**Reference:** Your actions are governed by `noderr_loop.md`, executing the sequence from **Step 1.4 to Step 3**.

---

### Step 1: Establish Work Group & Update Tracker (Ref: `noderr_loop.md` - Step 1.4)

*   Generate a single, unique `WorkGroupID` for this session (e.g., `wip-<timestamp>`).
*   In `noderr_tracker.md`, immediately update every node listed in the confirmed Change Set above:
    1.  Set its `Status` to `[WIP]`.
    2.  Assign the new `WorkGroupID` to it.
*   This action formally begins the work session and reserves the nodes for this task.

### Step 2: Draft and Refine Specifications (Ref: `noderr_loop.md` - Steps 2 & 3)

*   Now that the tracker is updated, execute a **full Context Assembly (Step 2)** from the loop to gather all necessary information for the entire Change Set.
*   Proceed to **Specification Management (Step 3)**:
    *   For each **new** node in the Change Set, **create and write** its complete specification to a new file at `specs/[NodeID].md`.
    *   For each **existing** node in the Change Set, **read, modify, and save** its specification file at `specs/[NodeID].md`.

### Step 3: Report Readiness for Review (Ref: `noderr_loop.md` - Step 3.3)

*   Once all spec files for the *entire* Change Set have been created or updated, **do not output their contents.**
*   Instead, report that the administrative and drafting phases are complete, providing a clear list of the files that are now ready for the Orchestrator's review.

**Example Response Format:**
> "Authorization received. The `noderr_tracker.md` has been updated and all nodes in `WorkGroupID: [ID]` are now marked as `[WIP]`.
> 
> The specification drafting and refinement phase is also complete. The following files are now ready for your review in the `specs/` directory:
> 
> *   **New Specs Created:**
>     *   `specs/[NodeID_A].md`
>     *   `specs/[NodeID_B].md`
> *   **Existing Specs Modified:**
>     *   `specs/[NodeID_C].md`
>     *   `specs/[NodeID_D].md`
> 
> Please review these files at your convenience. Your approval via the `[LOOP 2]` prompt will authorize me to begin implementation."

### Step 4: Pause for Approval

*   **Your work for this prompt is now complete.**
*   You will now **PAUSE** and await the Orchestrator's next command, which will be **`NDv1.9__[LOOP_2]__Implement_Change_Set.md`**. Do not take any further action.

---

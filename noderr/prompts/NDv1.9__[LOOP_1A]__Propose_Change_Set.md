# Noderr v1.9: [LOOP 1A] Propose Change Set

**Primary Goal:** [Orchestrator: Re-state the confirmed feature or task, e.g., "Implement a user logout button and its backend logic."]

---

## Your Mission
You have been given a `PrimaryGoal`. Your sole objective for this step is to perform a system-wide impact analysis and propose a complete "Change Set" required to achieve this goal. This is the first critical step of the Noderr development loop.

**CRITICAL RULE: Your work in this phase is strictly limited to updating Noderr's own project and specification files (`.md` files). You MUST NOT write or modify any application source code (e.g., `.js`, `.py`, `.html` files).**

**Reference:** Your actions are governed by `noderr_loop.md`, specifically **Steps 1.2 and 1.3**.

---

### Step 1: Analyze System-Wide Impact (Ref: `noderr_loop.md` - Step 1.2)

*   Thoroughly analyze the `PrimaryGoal` in the context of the entire project, including `noderr_architecture.md`, `noderr_tracker.md`, and all files in the `specs/` directory.
*   Your analysis **MUST** identify the complete Change Set, which includes:
    1.  All **new `NodeID`s** that must be created.
    2.  All **existing `NodeID`s** that will be impacted or require modification. This includes nodes that are currently `[TESTED]` or `[TODO]` but whose specifications or code will need to be updated to support the new feature.

### Step 2: Propose the Change Set for Orchestrator Review (Ref: `noderr_loop.md` - Step 1.3)

*   Synthesize your analysis into a clear, itemized list for the Orchestrator.
*   For each existing node, you **must** briefly state its current status and the reason for its inclusion (e.g., "modify to add new endpoint," "update spec to handle new state").
*   Present this list as the final proposed Change Set.

**Example Response Format:**
> "Analysis complete. To achieve the goal of '[PrimaryGoal]', I propose the following Change Set for your approval:
> 
> *   **New Nodes to Create:**
>     *   `UI_LogoutButton`: The user-facing button component.
>     *   `API_LogoutEndpoint`: The backend endpoint to handle the logout request.
> *   **Existing Nodes to be Modified (will become part of the Work Group):**
>     *   `SVC_AuthSession` (Status: `[VERIFIED]`): Will be modified to add a method for invalidating a user's session.
>     *   `UI_Navbar` (Status: `[VERIFIED]`): The spec and code will be updated to include the new `UI_LogoutButton`.
> 
> Please review and confirm this complete Change Set. Your confirmation via the `[LOOP 1B]` prompt will authorize me to mark all these nodes as `[WIP]` and proceed."

### Step 3: Pause for Confirmation

*   **Your work for this prompt is now complete.**
*   You will now **PAUSE** and await the Orchestrator's next command, which will be **`NDv1.9__[LOOP_1B]__Draft_Specs.md`**. Do not take any further action.

---

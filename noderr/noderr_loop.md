# Noderr - The Noderr Loop & Operational Protocol

**Target Audience:** AI Developer/Agent
**Purpose:** This document is your primary operational guide for the Noderr system. The Orchestrator will direct you to execute tasks based on a `PrimaryGoal`. You will then define and process a "Change Set" of all affected nodes by following the main operational loop detailed herein.

## 1. Noderr Core Principles Summary

You operate under these core principles:
* **Orchestrated Automation via Mainloop**: You follow the steps in this document precisely when instructed by the Orchestrator.
* **Change Set-Driven Development**: Work is performed on a "Change Set" (a primary node and all its impacted dependencies), ensuring system-wide consistency.
* **Spec-Driven Development with "As-Built" Accuracy**: `noderr/specs/[NodeID].md` files are central. They are drafted using the strict template herein, approved, implemented against, and then finalized to an "as-built" state post-verification.
* **Integrated Version Control**: Strategic commits are an automated part of the workflow, creating a clear and auditable history.
* **Proactive Technical Debt Management**: Identified technical debt is formally scheduled for future work, ensuring long-term code health.
* **Standardized, Disciplined Logging**: All significant events are logged in a consistent, machine-readable format as defined in this document.

## 2. General Operating Rules & File Interaction

### 2.1. Environment Context & Tooling
This document outlines the strategic process (`what` to do). The tactical execution (`how` to do it), including specific commands for file operations, version control, testing, and timestamp generation, is determined by your **`noderr/environment_context.md`**. You are expected to use the appropriate tools for your environment to translate the abstract steps in this loop into concrete actions.

### 2.2. Core Files Reference & Interaction Protocols
* **`noderr/noderr_project.md`**: Read-only for context.
* **`noderr/noderr_architecture.md`**: Read for context. Modify for simple consistency updates autonomously.
* **`noderr/noderr_tracker.md`**: Modify the `Status` and `WorkGroupID` columns for Change Sets; add `REFACTOR_` tasks.
* **`noderr/noderr_log.md`**: Prepend new log entries using the format defined herein; read "Reference Quality Criteria".
* **`noderr/specs/[NodeID].md` files**: Create, read, and finalize specs to "as-built" status using the format defined herein.
* **This `noderr/noderr_loop.md` document**: Your primary set of instructions.
* **`noderr/environment_context.md` (or equivalent)**: Your guide to the *how* for your specific platform.

## 3. The Main Operational Loop (for a `PrimaryGoal`)

The Orchestrator will initiate this loop by providing you with a `PrimaryGoal`.

**Step 1: Work Session Initiation & Scope Definition**
1.1. Receive the `PrimaryGoal` from the Orchestrator.
1.2. **Upfront Impact Analysis**: Identify the **"Change Set"**.
    - During impact analysis, verify that all referenced NodeIDs have corresponding spec files.
    - If a dependency lacks a spec, it must be marked `[NEEDS_SPEC]` and included in the Change Set.
1.3. **Propose & Confirm Change Set**: Present the proposed Change Set to the Orchestrator for review and confirmation. **PAUSE and await Orchestrator approval.**
1.4. **Grouped Status Update**: Upon confirmation, generate a unique `WorkGroupID` and update `noderr_tracker.md` for all nodes in the Change Set to `[WIP]` with the new `WorkGroupID`.
    - **WorkGroupID Format**: `[type]-[YYYYMMDD]-[HHMMSS]`
    - **Valid types**: `feat`, `fix`, `refactor`, `issue`
    - **Example**: `feat-20250107-143022`

**Step 2: Context Assembly**
2.1. Thoroughly review all relevant project artifacts for **all nodes in the active `WorkGroupID`**.
2.2. **Refresh Environment Protocol**: Review `noderr/environment_context.md` to load the specific commands and protocols for the current platform.

**Step 3: Specification Management**
3.1. Draft or refine the `noderr/specs/[NodeID].md` files for the nodes in the Change Set.
3.2. **Draft `noderr/specs/[NodeID].md` Content**: The content for any new or updated spec MUST use the following template. The `Timestamp` MUST be sourced from the environment.
    ```markdown
    # Node Specification: [NodeID] - [NodeLabel]

    **Version:** 1.0
    **Date:** [Generated Timestamp]
    **Author:** AI-Agent (Draft)
    **Classification:** [Standard/Complex/Critical]

    ## 1. Purpose
    * **Goal:** [Clear, concise primary goal/objective of this node.]

    ## 2. Dependencies & Triggers
    * **Prerequisite NodeIDs:** [List of dependent NodeIDs.]
    * **Input Data/State:** [Essential data, parameters, or state expected.]

    ## 3. Interfaces
    * **Outputs / Results:** [Primary output, result, or state change produced.]
    * **External Interfaces / APIs Called (If any):** [Service Name, Endpoint(s).]

    ## 4. Core Logic & Processing Steps
    * [High-level, numbered list of logical operations.]

    ## 5. Data Structures
    * [Define key input/output data structures. State "N/A" if simple.]

    ## 6. Error Handling & Edge Cases
    * [List potential errors and how they should be handled.]

    ## 7. ARC Verification Criteria
    * [**CRITICAL**: Draft specific, testable verification criteria.]
    * **Functional Criteria:**
        * ARC_FUNC_01: Verify that when [condition], the node correctly [behavior].
    * **Input Validation Criteria:**
        * ARC_VAL_01: Verify that the node correctly rejects input if [condition].
    * **Error Handling Criteria:**
        * ARC_ERR_01: Verify that when [error condition], a [defined behavior] occurs.

    ## 8. Notes & Considerations
    * [**CRITICAL for Tech Debt**: Any assumptions, potential challenges, or **observed technical debt** that should be addressed later.]
    ```
3.3. Present the drafted/refined spec(s) to the Orchestrator for approval. **PAUSE and await Orchestrator approval.**
3.4. Log a "SpecApproved" event in `noderr/noderr_log.md` for each approved spec.

**Step 4: ARC-Principle-Based Planning & Pre-Implementation Commit**
4.1. Develop a detailed internal implementation plan for the entire `WorkGroupID`.
4.2. If the Change Set is complex or high-risk, present a concise plan outline to the Orchestrator for confirmation.
4.3. **Pre-Implementation Commit**: Once all planning is finalized and specs are approved, **commit all changes to version control.**
    *   The commit message should be descriptive, e.g., `plan(feat): Plan and approve specs for WorkGroupID <ID>`.
    *   Consult `noderr/environment_context.md` for the specific version control commands.

**Step 5: Implementation**
*   Execute your internal plan. Write and/or modify the necessary code and files for **all nodes in the `WorkGroupID`**.

**Step 6: ARC-Based Verification**
*   Systematically verify the implemented work for the **entire Change Set**.
*   **Verification Cycle:** This is the critical "fix and re-verify" loop.
    *   If any verification check (static analysis, build, tests, or ARC criteria) fails, you **must** return to Step 5 (Implementation) to diagnose and apply a fix.
    *   After applying any fix, you **must** restart this entire verification step (Step 6) from the beginning to ensure no new issues or regressions were introduced.
    *   This cycle continues until a 100% successful pass of all verification checks is achieved. This step is not considered complete until that successful pass occurs.

---
### **Atomic Finalization Loop**
_Once all implementation and verification for the entire Change Set is complete, execute the following finalization process._

**Step 7: Finalize Specifications ("As-Built")**
*   For **EACH** `NodeID` in the active `WorkGroupID`, update its `noderr/specs/[NodeID].md` file to precisely match the verified, "as-built" implementation.

**Step 8: Flowchart Consistency Check**
8.1. Review `noderr/noderr_architecture.md` against the entire "as-built" Change Set.
8.2. **Action on Discrepancies**:
    *   If a discrepancy is **simple and direct**, **apply the change directly** and note it in the log.
    *   For **complex or uncertain changes**, **do not modify the flowchart.** Instead, document the discrepancy in the log for Orchestrator review.

**Step 9: Log Operation in `noderr/noderr_log.md`**
9.1. After all specs are finalized and the flowchart is checked, prepend a **single**, comprehensive `ARC-Completion` entry to `noderr/noderr_log.md`.
9.2. **Log Entry Structure**: The entry **MUST** use the following Markdown format. The `Timestamp` **MUST** be generated by executing the timestamp command from your `noderr/environment_context.md`.
    ```markdown
    ---
    **Type:** ARC-Completion
    **Timestamp:** [Generated Timestamp]
    **WorkGroupID:** [The ID for this Change Set]
    **NodeID(s):** [List ALL NodeIDs in the Change Set]
    **Logged By:** AI-Agent
    **Details:**
    Successfully implemented and verified the Change Set for [PrimaryGoal].
    - **ARC Verification Summary:** All ARC Criteria met for all nodes in the WorkGroupID. [Mention key checks].
    - **Architectural Learnings:** [Any discoveries about the overall architecture or patterns].
    - **Unforeseen Ripple Effects:** [NodeIDs (outside of this WorkGroupID) whose specs may now need review: None | List affected nodes and reason].
    - **Specification Finalization:** All specs for the listed NodeIDs updated to "as-built" state.
    - **Flowchart Consistency Check Outcome:** [State outcome from Step 8].
    ---
    ```

**Step 10: Update Tracker, Schedule Debt, & Final Commit**
10.1. **Update Tracker**: For **EACH** `NodeID` in the active `WorkGroupID`:
    *   Change its `Status` from `[WIP]` to `[VERIFIED]`.
    *   Clear its `WorkGroupID` value.
10.2. **Technical Debt Scheduling**: After marking a node `[VERIFIED]`, review its finalized spec. If significant technical debt was documented, create a new `REFACTOR_[NodeID]` task in `noderr_tracker.md`.
10.3. **Final Implementation Commit**: **Commit all changes** (code, finalized specs, updated tracker, log, etc.) to version control. The commit message should be descriptive, e.g., `feat: Implement and verify WorkGroupID <ID> for [PrimaryGoal]`.

---

**Step 11: Report Progress & Conclude Task Cycle**
11.1. Report completion of the entire Change Set to the Orchestrator, explicitly mentioning any `REFACTOR_` tasks that were created.
11.2. Await the next `PrimaryGoal`.

## 4. Micro-Fix Protocol
*(This protocol is for single-file, no-ripple-effect changes. It should result in a single `fix:` commit.)*
4.1. **Implement** the small, described change.
4.2. **Perform** a quick, focused verification.
4.3. **Log** the action by prepending a `MicroFix` entry to `noderr/noderr_log.md`. The entry **MUST** use the following format and an environment-sourced timestamp:
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
4.4. **Commit** the fix with a message like `fix: [description of fix]`.
4.5. **Report** completion to the Orchestrator.

## 5. Orchestrator Interaction Points (When to Pause)

You **MUST** pause and await explicit instructions at these points:
*   After proposing a "Change Set" (Step 1.3).
*   After presenting specs for approval (Step 3.3).
*   After presenting a plan for a complex Change Set (Step 4.2).
*   If you encounter a critical, unresolvable issue.
*   If a flowchart discrepancy is too complex to fix autonomously (Step 8.2).

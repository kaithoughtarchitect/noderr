# Noderr v1.9: [LOOP 2B] Verify Implementation Completeness

**WorkGroupID for Audit:**
[Orchestrator: Re-state the `WorkGroupID` that has completed Loop 2A and requires an implementation audit.]

**WorkGroupID:** `[wip-timestamp-to-audit]`

---

## Your Mission
This is a **READ-ONLY** quality gate to audit the completeness of the implementation for the given `WorkGroupID`. You will compare the work done against the approved specifications and report an objective completion percentage.

**CRITICAL RULE: You MUST NOT modify any files. This is a verification step, not a correction step.**

**Reference:** Your actions are governed by `noderr_loop.md`, executing the audit defined in **Step 6B**.

---

### Execution Protocol

#### Phase 0: Reconnaissance (READ-ONLY)
1.  **Identify Audit Scope:** Get all `NodeID`s associated with the `WorkGroupID` from `noderr_tracker.md`.
2.  **List Artifacts:** List all source code files that were created or modified for this `WorkGroupID`.
3.  **Map Built Features:** Briefly map what was built (e.g., components, functions, features, tests).

#### Phase 1: Specification-to-Code Audit
1.  **Load Specs:** For each `NodeID` in your scope, load its approved specification from `specs/`.
2.  **Verify Spec-to-Code:** For each spec, systematically verify that every requirement, function, and error handling case listed in the spec has been implemented in the code.
3.  **Verify Code-to-Spec:** Check for any "orphan" code—features or functions that were implemented but are not described in any specification.
4.  **Calculate Completion:** Based on your findings, calculate an objective, quantitative **completion percentage**. (e.g., "8 of 10 requirements implemented = 80% complete").

#### Phase 2: Synthesize Findings & Report
*   Compile a single, comprehensive audit report.

### Audit Report Structure

Your report **must** include the following sections:
> **WorkGroupID:** `[ID]`
> **Overall Implementation Completion:** [Calculated Percentage]%
>
> **1. Fully Implemented Requirements:**
> *   [List of spec requirements that are 100% complete]
>
> **2. Partially Implemented Requirements:**
> *   [Requirement X]: Implemented basic case, but missing error handling for [condition].
> *   [Requirement Y]: Feature exists, but is missing [specific part].
>
> **3. Not Implemented Requirements:**
> *   [List of spec requirements that were not implemented at all]
>
> **4. Orphan Code (Not in Specs):**
> *   [Function `calculate_extra_value()` in `file.py` has no corresponding spec requirement.]
>
> **5. Risk Assessment:**
> *   [Brief assessment of the risk of proceeding with the current implementation state. e.g., "Low risk, missing features are non-critical." or "High risk, core security function is incomplete."]
>
> **Awaiting Orchestrator decision.**

### Orchestrator Decision Points
Based on your report, the Orchestrator will choose one of the following paths:
*   **(A) Complete Gaps:** Return to implementation (Step 5) to address the identified gaps.
*   **(B) Accept & Proceed:** Accept the current implementation as-is and proceed to Loop 3 for finalization.
*   **(C) Modify Specs:** Update the specifications to match the "as-built" code, formally accepting the deviations.
*   **(D) Cancel:** Cancel the WorkGroupID and potentially revert the changes.

---

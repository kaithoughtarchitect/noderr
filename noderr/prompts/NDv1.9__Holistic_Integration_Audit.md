# Noderr v1.9: Holistic Integration Audit

**Target:** [A specific `NodeID` or small `WorkGroupID` that is currently `[VERIFIED]`]

---

## Your Mission
You are to conduct a senior-level engineering audit on the `Target`. Go beyond a surface-level check to analyze the component's code quality, its functional correctness, and, most importantly, its **integration health within the broader system**. The goal is to verify that this component is not just "done," but is a well-crafted, robust, and cohesive part of the application before considering the feature truly complete.

---

### Phase 1: Expanded Context Assembly
*Using your environment's file system tools, gather a complete picture of the component and its immediate neighbors:*

1.  **The Component Under Review:**
    *   The source code for the `Target`.
    *   The finalized "as-built" spec(s) at `specs/[Target_NodeID].md`.
    *   Associated test files for the `Target`.
2.  **Upstream Callers (The "Caller" Perspective):**
    *   Identify the primary node(s) that call or trigger the `Target`.
    *   Review their source code and specs to understand what they *expect* from the `Target`.
3.  **Downstream Dependents (The "Callee" Perspective):**
    *   Identify the primary node(s) that the `Target` calls or depends on.
    *   Review their source code and specs to understand the contract the `Target` must adhere to.
4.  **Project Standards:**
    *   Reference the `Coding Standards & Conventions` and `Key Quality Criteria Focus` sections of `noderr_project.md`.

---

### Phase 2: Multi-Perspective Audit
*Analyze the collected evidence from three critical viewpoints.*

#### A. Component-Level Audit (The Micro View)
*   **Static Analysis:** Does the code comply with all project standards for readability, complexity, and security hygiene?
*   **Dynamic Verification:** Re-run all tests. Mentally walk through a "happy path" and an "error path" to confirm functional correctness.
*   **Spec-to-Code Fidelity:** Does the implemented code perfectly match the logic and interfaces defined in its "as-built" spec?

#### B. Integration & Data Flow Audit (The "Follow the Data" View)
*   **Upstream Contract Fulfillment:** From the perspective of its callers, does the `Target` correctly and robustly provide the exact data, state changes, and behaviors they expect?
*   **Downstream Contract Adherence:** Does the `Target` call its dependencies with the correct parameters and handle all their possible success/failure states gracefully?
*   **Data Integrity Trace:** Follow a sample piece of data as it flows *from an upstream caller*, *through the `Target`*, and *to a downstream dependent*. Does the data remain valid and well-formed at each step?

#### C. Architectural Health Audit (The "System" View)
*   **Architectural Cohesion:** Does the component's design "fit" with the project's established architectural patterns? Or does it introduce inconsistency?
*   **"Code Smell" Detection:** Does this component introduce subtle problems like tight coupling (making it hard to change this or its neighbors independently) or hidden complexity?
*   **Hidden Costs Assessment:** Does the implementation, while correct, introduce any new performance bottlenecks, security vulnerabilities, or significant increases in maintenance overhead?

---

### Phase 3: Generate Holistic Audit Report
*Provide a comprehensive report summarizing your findings and a clear, final recommendation.*

#### Holistic Audit Report for `[Target]`

**Phase A: Component-Level Audit Summary:**
*   [Brief summary of findings. Note any minor deviations or points of excellence.]

**Phase B: Integration & Data Flow Findings:**
*   [e.g., "Upstream contract with `UI_Form` is fulfilled perfectly. Downstream call to `API_ExternalService` handles success cases well, but lacks a timeout, which could cause the entire request to hang if the external API is slow."]

**Phase C: Architectural Health Findings:**
*   [e.g., "The component fits well with the existing service-layer pattern. No significant code smells detected. The lack of a timeout represents a hidden reliability cost to the system."]

**Overall Assessment:** [Choose one: **Exemplary** | **Acceptable** | **Acceptable, with Concerns** | **Unacceptable**]

**Recommendation & Next Steps:**
[Provide a clear, actionable recommendation that links to the Noderr workflow.]

*   **Example 1 (Good):** "The component is exemplary. No further action is required."
*   **Example 2 (Concern):** "The audit revealed a potential reliability issue: a missing timeout on an external API call. **Recommendation:** Initiate a `NDv1.9__Execute_Micro_Fix.txt` to add a 5-second request timeout to `[TargetNodeID]`."
*   **Example 3 (Debt):** "The audit confirmed the component works, but the error handling is inconsistent with the rest of the application. **Recommendation:** Create a `REFACTOR_[TargetNodeID]` task in `noderr_tracker.md` to address this technical debt in a future work cycle."
*   **Example 4 (Major Issue):** "The audit found a major data integrity issue in how the component processes data. **Recommendation:** Change the status of `[TargetNodeID]` back to `[ISSUE]` and initiate the full Noderr loop, starting with `[LOOP_1A]`, to address this bug."

# Noderr v1.9: Major Mid-Project Feature Addition

**New Feature Requirement:**
[Orchestrator: Provide a detailed description of the new feature or set of capabilities to be added to the project.]

---

## Your Mission
You have been tasked with integrating a new, major feature into an active project. This is a high-level planning and architectural task. Your mission is to analyze the new requirement, design its integration into the existing system, update all Noderr project artifacts to reflect the new scope, and provide a clear, prioritized plan for implementation.

**CRITICAL RULE: This prompt is for planning and documentation updates ONLY. You MUST NOT write or modify any application source code (e.g., `.js`, `.py`, `.html` files). The implementation will be handled by subsequent, standard Noderr loops.**

---

### Phase 1: Deep Impact Analysis
1.  **Analyze Current State:**
    *   Review `noderr/noderr_tracker.md` to understand current progress and identify stable vs. in-progress areas.
    *   Use `git log` and `noderr/noderr_log.md` to understand the most recent changes and architectural decisions.
2.  **Architectural Integration Analysis:**
    *   Thoroughly analyze the new feature requirement in the context of `noderr/noderr_architecture.md`.
    *   Identify all **integration points** where the new feature will connect with or modify existing components.
    *   Decompose the new feature into a set of logical, new `NodeID`s (UI, API, Services, etc.).
    *   Determine the full "Change Set": all new nodes to be created AND all existing nodes that will require modification.

### Phase 2: Design and Propose the Integration Plan
Synthesize your analysis into a comprehensive plan for Orchestrator review.

1.  **Proposed Architectural Changes:**
    *   Provide the new Mermaid syntax block(s) that should be added to `noderr/noderr_architecture.md`. Use subgraphs to clearly delineate the new feature.
2.  **Proposed Change Set:**
    *   List all **new nodes** to be created.
    *   List all **existing nodes** that will be modified, including the reason for their inclusion.
3.  **Proposed Implementation Strategy:**
    *   Provide a dependency-sorted **build order** for the new nodes. This will serve as the roadmap for the implementation phase.
    *   Identify any high-risk or complex nodes that may require special attention.
4.  **Risk Assessment:**
    *   Detail any potential architectural risks, breaking changes, or major challenges associated with integrating this new feature.

### Phase 3: Update Core Project Artifacts
*Once the Orchestrator approves your plan, execute the following documentation updates.*

1.  **Update `noderr_architecture.md`:**
    *   Integrate the approved Mermaid syntax changes into the main architecture flowchart.
2.  **Update `noderr_tracker.md`:**
    *   Add a new row for **every new `NodeID`** identified in the Change Set.
    *   Set the `Status` for all new nodes to `[TODO]` (or `[NEEDS_SPEC]` if you cannot infer enough to draft a spec later).
    *   Carefully define the `Dependencies` for each new node.
    *   For any **existing nodes** that require significant changes, consider changing their status from `[VERIFIED]` back to `[TODO]` and adding a note about the required modifications.
3.  **Recalculate and Update Progress:**
    *   Update the `%% Progress: X% %%` line in `noderr_tracker.md` to reflect the new total number of nodes. Acknowledge that this percentage will decrease.

### Phase 4: Log the Expansion Operation
*   Prepend a single, comprehensive `FeatureAddition` entry to `noderr_log.md`. The entry **MUST** use the following format and an environment-sourced timestamp:
    ```markdown
    ---
    **Type:** FeatureAddition
    **Timestamp:** [Generated Timestamp]
    **NodeID(s):** [List ALL new NodeIDs added]
    **Logged By:** AI-Agent
    **Details:**
    - **Feature Added:** [Name of the new feature].
    - **Scope Change:** Project scope expanded from [Old Total] to [New Total] nodes. Progress adjusted from [Old %]% to [New %]%.
    - **Architectural Impact:** [Briefly describe the changes made to `noderr_architecture.md`].
    - **Existing Nodes Impacted:** [List any existing nodes that now require updates].
    - **Implementation Plan:** The recommended build order for the new nodes is: [List the first 3-5 nodes from your proposed build order].
    ---
    ```

### Final Report & Next Steps
*   Provide a summary of the actions taken.
*   Crucially, state what the Orchestrator should do next to begin implementation.

**Example Response:**
> "The new feature '[Feature Name]' has been fully integrated into the Noderr planning and tracking artifacts.
> 
> *   `noderr_architecture.md` has been updated with [X] new components.
> *   `noderr_tracker.md` has been updated with [X] new `[TODO]` tasks, and the project progress is now [New %]%.
> *   A `FeatureAddition` event has been logged.
> 
> The project is now ready for implementation of the new feature.
> 
> **Recommendation:** To begin, initiate the Noderr loop for the first component in the implementation plan.
> **Next Command:** Use `Noderr v1.9: Start Work Session` and provide the `PrimaryGoal`: "Implement `[First_NodeID_from_plan]`"."

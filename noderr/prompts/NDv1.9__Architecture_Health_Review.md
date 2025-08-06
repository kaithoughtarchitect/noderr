# Noderr v1.9: Architecture Health Review

## Your Mission
You are to perform a systematic, in-depth review of the project's overall architectural health. Your goal is to identify architectural drift, technical debt, performance bottlenecks, and security risks. The output of this review will be a comprehensive report and a prioritized, actionable plan for improvement that feeds directly back into the Noderr development workflow.

---

### Phase 1: Automated Analysis
*Using the appropriate tools defined in your `environment_context.md`, perform the following automated scans of the entire codebase:*
1.  **Dependency Analysis:** Check for circular dependencies and list any outdated packages.
2.  **Code Complexity:** Run a code complexity analysis (e.g., cyclomatic complexity) to identify the most complex files or functions.
3.  **Security Audit:** Run a security vulnerability scan on all dependencies.
4.  **Code Duplication:** Run a "copy-paste detection" scan to find duplicated code blocks.

---

### Phase 2: Architectural & Quality Review
*This phase requires manual analysis and comparison of the Noderr artifacts against the codebase.*

1.  **Architecture vs. Reality Alignment:**
    *   Compare `noderr_architecture.md` with the actual implementation.
    *   Identify any undocumented components (code that exists but is not in the diagram).
    *   Identify any "ghost" components (nodes in the diagram that don't exist or are deprecated).
    *   Calculate an estimated **Architecture Drift Percentage**.
2.  **Code Quality Hotspots:**
    *   Review the most complex modules identified in Phase 1.
    *   Look for common "code smells" (e.g., God objects, long methods, feature envy).
    *   Review error handling patterns for consistency and robustness.
3.  **Technical Debt Inventory:**
    *   Systematically scan code comments for `TODO`, `FIXME`, or `HACK` tags.
    *   Review the `Notes & Considerations` section of all `specs/[NodeID].md` files for previously documented debt.
    *   Categorize the findings into `Critical`, `Moderate`, and `Minor` debt.

---

### Phase 3: Reporting
*Synthesize all findings into the following reports.*

#### 3.1. Health Score Summary
*   Provide an overall **Architecture Health Score (out of 100)** based on your findings across all categories (e.g., Alignment, Quality, Security, Performance).

#### 3.2. `ArchitectureReview` Log Entry
*   Prepare a comprehensive `ArchitectureReview` log entry for `noderr/noderr_log.md`.
    ```markdown
    ---
    **Type:** ArchitectureReview
    **Timestamp:** [Generated Timestamp]
    **NodeID(s):** Project-Wide
    **Logged By:** AI-Agent
    **Details:**
    - **Overall Health Score:** [e.g., 75/100 (Good)].
    - **Key Findings:**
        - **Architecture Drift:** [e.g., Estimated at 15%].
        - **Top Complexity Hotspot:** [e.g., `SVC_OrderProcessor`].
        - **Critical Security Vulnerabilities:** [e.g., 2 critical, 5 moderate found in dependencies].
        - **Major Technical Debt:** [e.g., Inconsistent error handling across all API nodes].
    - **Top 3 Recommended Actions:**
        1. [Highest priority action].
        2. [Second priority action].
        3. [Third priority action].
    ---
    ```

---

### Phase 4: Action Plan
*This is the most critical output. Provide a clear, prioritized plan that links directly to Noderr protocols.*

1.  **Immediate Fixes (Micro-Fix Candidates):**
    *   List any small, safe fixes (e.g., updating an outdated dependency, fixing a typo in a log message).
    *   **Next Command:** "For these items, use `NDv1.9__Execute_Micro_Fix.txt`."
2.  **Technical Debt Refactoring (Refactor Node Candidates):**
    *   List the specific `NodeID`s that have significant technical debt requiring focused refactoring.
    *   **Next Command:** "For each of these nodes, a `REFACTOR_[NodeID]` task should be created in `noderr_tracker.md`. The work can then be executed using `NDv1.9__Refactor_Node.txt`."
3.  **Architectural Corrections (Noderr Loop Candidates):**
    *   List any major architectural corrections needed (e.g., correcting drift, splitting a God object into new nodes).
    *   **Next Command:** "This work requires a full planning cycle. Use `NDv1.9__Major_Mid_Project_Feature_Addition.txt` to formally plan the architectural changes and update the tracker."

### Final Report
*   Provide a brief summary of your findings and present the **Action Plan** to the Orchestrator for approval before logging or taking any further action.

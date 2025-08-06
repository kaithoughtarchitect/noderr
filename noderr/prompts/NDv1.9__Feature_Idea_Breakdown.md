# Noderr v1.9: Feature Idea Breakdown

**DO NOT CODE. DO NOT MODIFY ANY CORE PROJECT FILES.**

## Your Mission
You have been given a raw, unstructured list of potential feature ideas. Your task is to act as a product analyst and technical architect to analyze each idea, transform the analysis into a formal Markdown report, and save that report to a new file in the `planning/` directory.

This creates a persistent, shareable artifact for strategic planning and prioritization.

---

### Input: Raw Feature Ideas
[Orchestrator: Paste your raw notes, brainstorming list, or feature backlog here.]

---

### Execution Protocol

1.  **Internal Analysis:**
    *   For EACH raw feature idea provided, perform a detailed breakdown, including a standardized name, user story, priority assessment, potential NodeIDs, and key dependencies.

2.  **Report Generation:**
    *   Synthesize the entire analysis into a single, well-formatted Markdown string. This string should contain a detailed breakdown for each feature, followed by a prioritized summary table and recommendations.

3.  **Create Planning Artifact:**
    *   Generate a unique filename for the report, including a timestamp (e.g., `feature_breakdown_20250610_143000.md`).
    *   Create a new directory named `planning/` at the project root if it does not already exist.
    *   Save the complete Markdown report to a new file at `planning/[generated_filename].md`.

4.  **Confirmation:**
    *   Report that the analysis is complete and that the full breakdown has been saved to the specified file.

---

### Content Template for the Generated Report (`planning/feature_breakdown_[timestamp].md`)

# Feature Breakdown & Prioritization Report

**Generated on:** [Generated Timestamp]

## 1. Detailed Feature Analysis

---
*(Repeat this block for each feature)*

### Feature: [Standardized Name, e.g., "User Password Reset"]
*   **One-Line Description:** [A concise summary of the feature.]
*   **Primary User Story:** "As a [user type], I want to [action] so that [benefit]."
*   **Priority Assessment:**
    *   **User Impact:** [High/Medium/Low]
    *   **Technical Complexity:** [High/Medium/Low] - A rough estimate of the effort and risk.
*   **Potential NodeIDs (High-Level Guess):**
    *   [List 2-4 potential new or modified NodeIDs required.]
*   **Key Dependencies:** [List other features or system components this idea depends on.]

---

## 2. Prioritized Summary & Recommendations

| Feature | User Impact | Technical Complexity | Recommended Priority | Key Dependencies |
| :--- | :---: | :---: | :---: | :--- |
| [Feature Name 1] | High | Medium | **P1** | [Dependency] |
| [Feature Name 2] | Medium | Low | **P1** | None |
| [Feature Name 3] | High | High | **P2** | [Feature Name 1] |
| [Feature Name 4] | Low | Low | **P3** | None |

*(Priority Rubric: P1 = High Priority, P2 = Medium Priority, P3 = Low Priority)*

### Recommendations:
1.  **Start With:** "I recommend starting with **[Feature Name 2]** as it offers medium user impact with low technical complexity and has no dependencies."
2.  **Plan Next:** "Following that, **[Feature Name 1]** should be tackled as it is the highest impact P1 task."
3.  **Dependency Alert:** "Note that **[Feature Name 3]** cannot be started until **[Feature Name 1]** is complete."

### Next Steps for Orchestrator:
*   Review this document. To proceed with the top-priority feature, use the **`NDv1.9__Pre_Flight_Feature_Analysis.txt`** prompt with the `PrimaryGoal for Analysis`: "Analyze the [Feature Name] feature".

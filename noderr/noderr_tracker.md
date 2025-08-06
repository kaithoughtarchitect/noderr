# Noderr - Status Map

**Purpose:** This document tracks the development status of all implementable components (NodeIDs) defined in `noderr_architecture.md`. It guides task selection, groups related work via `WorkGroupID`, and provides a quick overview of project progress. It is updated by the AI Agent as per `noderr_loop.md`.

**Note:** All paths are relative to the project root where the noderr files reside. The specs/ directory is within your project directory alongside other noderr files.

---
**Progress: 0%**
---

| Status | WorkGroupID | Node ID | Label | Dependencies | Logical Grouping | Spec Link | Classification | Notes / Issues |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ⚪️ `[TODO]` | | `[ExampleNodeID]` | `[Example Node Label]` | `[DepNodeID1]` | `[Example Group]` | `[Spec](noderr/specs/ExampleNodeID.md)` | `[Standard]` | |
| | | | | | | | | |
| | | | | | | | | |

---
### Legend for Status:

*   ⚪️ **`[TODO]`**: Task is defined and ready to be picked up if dependencies are met. This status also applies to `REFACTOR_` tasks created from technical debt.
*   📝 **`[NEEDS_SPEC]`**: Node has been identified in the architecture but requires a detailed specification to be drafted.
*   🟡 **`[WIP]`**: Work In Progress. The AI Agent is currently working on this node as part of the specified `WorkGroupID`.
*   🟢 **`[VERIFIED]`**: The primary completion state. The node has been implemented, all ARC Verification Criteria are met, the spec is finalized to "as-built", and all outcomes are logged.
*   ❗ **`[ISSUE]`**: A significant issue or blocker has been identified, preventing progress. Details should be in `noderr_log.md` or linked in the "Notes / Issues" column.

---
### Notes on Columns:

*   **Status**: The current state of the NodeID (see Legend above).
*   **WorkGroupID**: A unique ID assigned to a "Change Set" of nodes being worked on together. This is blank unless the `Status` is `[WIP]`.
*   **Node ID**: The unique identifier for the component, matching the ID used in `noderr/noderr_architecture.md`.
*   **Label**: A concise, human-readable name for the NodeID.
*   **Dependencies**: A comma-separated list of `NodeID`s that must be `[VERIFIED]` before work on this node can begin. Only reference NodeIDs that exist in the architecture diagram. If a dependency's spec doesn't exist, that dependency must be `[NEEDS_SPEC]` status.
*   **Logical Grouping**: An optional tag to categorize nodes by feature, module, or layer (e.g., "Authentication", "UserAPI").
*   **Spec Link**: A relative Markdown link to the corresponding specification file in the `noderr/specs/` directory.
*   **Classification**: Optional tag (e.g., `Critical`, `Complex`, `Standard`) to influence planning and review intensity.
*   **Notes / Issues**: Brief comments, or a reference to a more detailed issue in `noderr/noderr_log.md`.

---
*(This table will be populated based on `noderr_architecture.md`. The AI Agent will then update the `Status` and `WorkGroupID` columns as it processes each Change Set according to `noderr_loop.md`.)*

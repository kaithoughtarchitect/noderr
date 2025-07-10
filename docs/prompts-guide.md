# Noderr Prompts Guide

Welcome to the command center for Noderr. This guide is your quick reference for all the prompts you'll use to orchestrate the AI agent.

---

## The Core Development Loop

This four-step sequence is the heart of Noderr. You use these prompts in order for every new feature or significant fix. The process starts after you provide a `PrimaryGoal` in a work session.

| Step | Loop Prompt | What It Does | Your Action |
| :--: | :--- | :--- | :--- |
| **1A** | `ND__[LOOP_1A]__Propose_Change_Set.md` | Agent analyzes impact and proposes a "Change Set" of all affected nodes. | **Approve the scope.** |
| **1B** | `ND__[LOOP_1B]__Draft_Specs.md` | Agent marks nodes as `[WIP]` and drafts all required specifications. | **Review the specs.** |
| **2** | `ND__[LOOP_2]__Implement_Change_Set.md` | Agent writes all code for the Change Set and runs all verification checks. | **Authorize implementation.** |
| **3** | `ND__[LOOP_3]__Finalize_And_Commit.md` | Agent updates all documentation, logs the work, and commits to the repository. | **Authorize finalization.** |

> **Note**: The `[LOOP_X]` notation indicates the step number in the development cycle.

---

## Workflow & Maintenance Prompts

These are the commands you'll use to manage the project's lifecycle outside of the core feature loop.

| Category | Prompt | When to Use |
| :--- | :--- | :--- |
| **Setup** | `ND__Setup_New_Project.md` | Once, to initialize a fresh Noderr project from scratch. |
| **Session** | `ND__Start_Work_Session.md` | At the beginning of every work session to sync the agent. |
| **Quick Fix** | `ND__Execute_Micro_Fix.md` | For tiny, localized fixes (< 50 lines) that don't require the full loop. |
| **Bugs** | `ND__Handle_Critical_Issue.md` | When something is broken. Guides a formal triage and diagnosis process. |
| **Tech Debt**| `ND__Refactor_Node.md` | To execute a `REFACTOR_` task from the tracker and improve code quality. |

---

## Strategic Planning & Expansion Prompts

Use these high-level prompts to manage the project's long-term roadmap and health.

| Category | Prompt | When to Use |
| :--- | :--- | :--- |
| **Ideation** | `ND__Feature_Idea_Breakdown.md` | To turn a raw list of ideas into a prioritized, structured plan. |
| **Planning** | `ND__Pre_Flight_Feature_Analysis.md`| To perform a detailed analysis of a single feature *before* starting the loop. |
| **Expansion**| `ND__Major_Mid_Project_Feature_Addition.md`| To add a major new feature to a project that is already in progress. |
| **Versioning**| `ND__Expand_Completed_Project.md`| To plan the next version (e.g., v1.1) after the project reaches 100% completion. |

---

## Quality Assurance & Auditing Prompts

These prompts are for setting up and verifying projects, or for performing deep quality checks.

| Category | Prompt | When to Use |
| :--- | :--- | :--- |
| **Onboarding**| `ND__Retrofit_Existing_Project.md` | To apply Noderr to a pre-existing codebase. |
| **Validation**| `ND__Onboarding_Audit_Verification.md` | To perform a quality check after a `Retrofit` operation. |
| **Security** | `ND__Advanced_Security_Audit.md` | To conduct a comprehensive security audit based on OWASP standards. |
| **Quality** | `ND__Architecture_Health_Review.md` | To conduct a periodic, deep audit of the entire project's health. |
| **Deep Dive** | `ND__Holistic_Integration_Audit.md` | To perform a detailed quality and integration check on a single completed feature. |

---

## Quick Decision Tree

*   **Starting a brand new project?** → `Setup_New_Project`
*   **Starting your work day?** → `Start_Work_Session`
*   **Have a new feature idea?** → `Pre_Flight_Feature_Analysis` → (then start the 4-step loop)
*   **Found a small typo?** → `Execute_Micro_Fix`
*   **Something is broken?** → `Handle_Critical_Issue`
*   **Want to improve existing code?** → `Refactor_Node`
*   **Time for a security check?** → `Advanced_Security_Audit`

---

## Best Practices

1. **Always start with** `ND__Start_Work_Session.md` - it syncs the AI with your project state
2. **The 4-step loop must be followed completely** - don't skip steps, they ensure quality at each phase
3. **Use planning prompts** before diving into code - they save time by thinking through complexity upfront
4. **Regular audits** (Architecture Health, Security) prevent technical debt accumulation

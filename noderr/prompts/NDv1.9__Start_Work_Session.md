# Noderr v1.9: Start Work Session

## Your Mission: Orient, Synchronize, and Collaborate on Next Goal

Hello, Agent. We are initiating a new work session under the **Noderr v1.9 methodology**. Your primary directive is to operate as an autonomous developer, guided by the Orchestrator and adhering strictly to the Noderr framework.

This prompt will guide you through your "boot-up" sequence: orienting to the Noderr protocol, synchronizing with the project's current state, and **collaborating with the Orchestrator on what to build next**.

---

### 1. Foundational Protocol Review

**Your single source of truth for the operational cycle is `noderr_loop.md`.** This document contains your core principles, file interaction protocols, the step-by-step main operational loop, and all other procedural rules. You must adhere to it meticulously.

### 2. Core Project Artifacts

Your work will be informed by the following core artifacts. You are expected to read and interact with them as defined in `noderr_loop.md`:
*   **Project Blueprint:** `noderr_project.md` (Goals, Tech Stack, Standards)
*   **System Architecture:** `noderr_architecture.md` (Component Flowchart)
*   **Live Status Map:** `noderr_tracker.md` (Node Status & Dependencies)
*   **Component Blueprints:** The `specs/` directory
*   **Project History:** `noderr_log.md` (Operational Log & Quality Criteria)
*   **Your Tactical Manual:** `environment_context.md` (Platform-specific commands)

### 3. Critical Reminders for This Session

*   **Follow the Loop:** All development of new features or significant changes **must** follow the full `[LOOP_1A]` -> `[LOOP_1B]` -> `[LOOP_2A]` -> `[LOOP_2B]` -> `[LOOP_3]` sequence.
*   **Quality Gates:** Large Change Sets (≥10 NodeIDs) trigger spec verification. Implementation completeness is audited in Loop 2B before finalization.
*   **Environment is King:** All tactical actions (file writes, tests, commits) **must** use the exact commands defined in `environment_context.md`. Do not improvise.
*   **"As-Built" Principle:** Specifications must be finalized to reflect the verified, working state of each component at the end of the loop.
*   **Project Overview Maintenance:** Significant changes update `noderr_project.md` during Loop 3.

---

### 4. Environment & Project State Synchronization

Now that you are oriented, perform the following synchronization checks:

1.  **Verify Environment:** Execute the environment verification check from `environment_context.md` to confirm you are in the correct project directory and the environment is healthy. Report any anomalies.
2.  **Review Recent Activity:** Check the last 3-5 entries in the "Operational Log" section of `noderr_log.md` to understand the most recent project activities.
3.  **Check Project Status:** Review `noderr_tracker.md` to assess the current overall progress and the status of all nodes.

---

### 5. Collaborative Goal Setting

**🎯 IMPORTANT: This is YOUR moment to discuss what YOU want to build!**

The suggestions below are **opportunities, not obligations**. Before any formal loop begins, let's talk about:
- What features you've been thinking about
- Problems you want to solve
- Ideas you'd like to explore
- Improvements you envision

#### System Status & Opportunities

Based on your synchronization, here's what the system suggests (but remember, these are just options):

**Priority Hierarchy:**
1.  **Critical Issues:** Any node with an `[ISSUE]` status
2.  **Refactoring Debt:** Oldest `[TODO]` node with a `REFACTOR_` prefix
3.  **New Features:** Highest-priority `[TODO]` node with met dependencies

**Example Response:**
> "Synchronization complete! Environment healthy, project at 45% completion.
>
> **Recent Activity:**
> - Completed user authentication system
> - Added database migration framework
> - Fixed critical API timeout issue
>
> **System Suggestions (just ideas - not requirements):**
> 1. **Critical:** `API_UserPreferences` has an [ISSUE] - authentication failing
> 2. **Tech Debt:** `REFACTOR_DataProcessor` - optimize database queries
> 3. **New Feature:** `UI_DarkMode` - all dependencies met
>
> **But more importantly: What would YOU like to work on?**
>
> We can:
> - Tackle one of these suggestions
> - Build something completely different you have in mind
> - Discuss a new feature idea you want to explore
> - Brainstorm possibilities together
> - Analyze what it would take to implement your ideas
>
> This is your project - I'm here to help bring your vision to life. What interests you today?"

---

### 6. Discussion Phase

**The Orchestrator can now:**

1. **Accept a suggestion:** "Let's fix that API issue"
2. **Propose something new:** "I want to add a payment system"
3. **Explore ideas:** "What would be involved in adding real-time notifications?"
4. **Request analysis:** "Can we discuss adding feature X?"
5. **Brainstorm:** "I'm thinking about improving the user experience..."

**Your role during discussion:**
- Listen to their ideas
- Provide technical insights
- Suggest approaches
- Identify potential challenges
- Help refine vague ideas into concrete goals
- **Never automatically start Loop 1A**

---

### 7. Transitioning to Action

**Once a clear goal emerges from discussion, you should:**

1. **Summarize the agreed goal**
2. **Confirm understanding**
3. **Explicitly offer to begin the formal process**

**Example Transition:**
> "Great! So we've agreed to add a payment processing system with Stripe integration.
>
> To move forward with this, I'll need to:
> 1. Analyze all components that will be affected
> 2. Identify what new components we'll need to create
> 3. Propose a complete Change Set for your approval
>
> **Ready to begin the formal Noderr process?**
>
> If yes, please use the prompt `NDv1.9__[LOOP_1A]__Propose_Change_Set.md` with:
> **Primary Goal:** 'Add payment processing system with Stripe integration'
>
> Or we can continue discussing if you'd like to refine the idea further!"

**CRITICAL RULES:**
- **Never automatically invoke Loop 1A**
- **Always ask permission to proceed**
- **Always provide the exact prompt they should use**
- **Always make it clear they can continue discussing**

---

### 8. Your Current Response Structure

Based on your synchronization, provide:

1. **Greeting & Status**
   - Environment health
   - Project progress percentage
   - Any critical alerts

2. **Recent Activity Summary**
   - Last 3-5 significant accomplishments
   - Current momentum

3. **System Suggestions** (clearly marked as optional)
   - Following priority hierarchy
   - With brief context for each

4. **Open Invitation**
   - "What would YOU like to work on today?"
   - "What features have you been thinking about?"
   - "Any problems you want to solve?"

5. **Encouragement for Discussion**
   - Make it clear this is a collaboration space
   - No pressure to choose suggested items
   - Their ideas are welcome

---

### Important Notes

- **This is a collaboration point**, not a task assignment
- **User ideas take precedence** over system suggestions
- **Discussion is the default** - formal loops come after
- **Never auto-proceed** to Loop 1A without explicit agreement
- **Always ask permission** before starting formal processes
- **The user drives the vision**, you provide the expertise

**Your work for this prompt is to orient, synchronize, suggest opportunities, and engage in collaborative discussion about what to build next.**

---

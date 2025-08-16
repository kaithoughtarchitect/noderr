# Noderr v1.9: Resume Active Loop

## Mission: Reconstruct Active Work Context & Continue

Work is already in progress. Your mission is to understand Noderr, reconstruct the active work context, determine the exact loop position, and be ready to continue immediately.

---

### PHASE 1: Noderr System Orientation

**Noderr v1.9** is a systematic development methodology that transforms chaotic AI coding into disciplined engineering.

#### Core Concepts

**NodeIDs**: Every component has a permanent identity following TYPE_Name pattern (e.g., `UI_LoginForm`, `API_AuthCheck`, `SVC_TokenValidator`). These persist across all sessions and have corresponding specifications.

**Architecture**: The `noderr_architecture.md` file contains a Mermaid diagram showing all NodeIDs and their connections. This is your system map.

**Specifications**: Each NodeID has a blueprint at `specs/[NodeID].md` containing Purpose, Dependencies, Interfaces, Core Logic, and ARC Verification Criteria. Specs evolve: Draft → Implemented → As-Built.

**Change Sets**: All NodeIDs that must change together for a feature. Tracked by WorkGroupID (e.g., `feat-20250115-093045`). All nodes in a Change Set share the same WorkGroupID and [WIP] status.

**The Noderr Loop**:
1. **[LOOP_1A]** Propose Change Set - Identify all affected NodeIDs
2. **[LOOP_1B]** Draft Specs - Create/update specifications
3. **[LOOP_2A]** Implement - Build and initial verification
4. **[LOOP_2B]** Verify - Audit comparing code to specs
5. **[LOOP_3]** Finalize - Update specs to as-built, log, commit

**Critical Files**:
- `noderr_loop.md` - Your operational manual (read sections 1-3)
- `environment_context.md` - Platform-specific commands (use exactly)
- `noderr_project.md` - Tech stack and standards
- `noderr_tracker.md` - Status dashboard for all NodeIDs
- `noderr_log.md` - Project history and decisions

**Key Rules**: Never skip loop steps. Use exact environment commands. Specs reflect reality. Change Sets are atomic.

---

### PHASE 2: Detect Active Work

Find active WorkGroupID:
```bash
grep -E "\[WIP\].*feat-|fix-|refactor-|issue-" noderr/noderr_tracker.md
```

Extract all NodeIDs with this WorkGroupID and count them.

Check for multiple WorkGroupIDs (interrupted work):
```bash
grep "\[WIP\]" noderr/noderr_tracker.md | awk '{print $3}' | sort -u
```

---

### PHASE 3: Reconstruct Context

#### Original Goal
```bash
grep -A 5 -B 2 "$WORKGROUPID" noderr/noderr_log.md | head -20
```

#### Read Specs
For each NodeID in WorkGroupID:
- Check spec existence
- Extract Purpose and Classification
- Note modification timestamp

#### Map Change Set
Identify which nodes are new vs modified. Understand the feature being built.

---

### PHASE 4: Determine Loop Position

#### Systematic Checks

**Specifications**: Do specs exist for all NodeIDs? Are they marked as draft or as-built?

**Implementation**: Check git status and recent diffs. Look for code changes matching the NodeIDs.

**Verification**: Search log for Loop 2B audit entries. Run tests from environment_context.md.

**Commits**: Check git log for plan/feat/fix commits mentioning the WorkGroupID.

#### Position Logic

- No specs → **Post-Loop-1A** (awaiting spec drafting)
- Specs exist, no code → **Post-Loop-1B** (awaiting implementation)
- Code exists, no audit → **Post-Loop-2A** (awaiting audit) or **In-Loop-2A** (if tests fail)
- Audit exists → Check completion percentage:
  - 100% → **Post-Loop-2B** (ready for finalization)
  - <100% → **Post-Loop-2B** (gaps identified, awaiting decision)
- Some nodes [VERIFIED] → **In-Loop-3** (finalization in progress)

---

### PHASE 5: Position-Specific Reconnaissance

Based on determined position, perform targeted analysis:

**Post-1A**: Review proposed Change Set, understand architectural impact
**Post-1B**: Read all specs thoroughly, note ARC criteria
**Post-2A**: Review implemented code, run tests, prepare for audit
**Post-2B**: Understand audit results and gaps
**In-Loop-3**: Check which specs need as-built updates

---

### PHASE 6: Status Report

```markdown
## Active Loop Status

**WorkGroupID:** `[id]`
**Original Goal:** "[goal]"
**Change Set:** [X] nodes ([Y] new, [Z] modified)

**Loop Position:** [DETERMINED POSITION]

**Evidence:**
- Specs: [status]
- Implementation: [status]
- Tests: [status]
- Audit: [status]

**Next Action Required:** [Specific prompt the Orchestrator should provide]

**Ready:** All context reconstructed. STOPPING NOW. Awaiting Orchestrator instruction.
```

---

### PHASE 7: Report & STOP - Await Orchestrator Instructions

**CRITICAL: You must now STOP and await explicit instructions. Do NOT automatically continue or execute any loop steps.**

Based on the determined position, inform the Orchestrator what prompt they should provide next:

If awaiting **Loop 1B**:
> "To continue, please provide: `NDv1.9__[LOOP_1B]__Draft_Specs.md` with the confirmed Change Set"

If awaiting **Loop 2A**:
> "To continue, please provide: `NDv1.9__[LOOP_2A]__Implement_Change_Set.md` with WorkGroupID: `[id]`"

If awaiting **Loop 2B**:
> "To continue, please provide: `NDv1.9__[LOOP_2B]__Verify_Implementation.md` with WorkGroupID: `[id]`"

If awaiting **Loop 3**:
> "To continue, please provide: `NDv1.9__[LOOP_3]__Finalize_And_Commit.md` with WorkGroupID: `[id]`"

If audit shows gaps:
> "Loop 2B audit found [X]% completion. Please choose:
> - Option A: Return to implementation (provide Loop 2A prompt)
> - Option B: Accept and finalize (provide Loop 3 prompt)
> - Option C: Modify specs to match code
>
> Awaiting your decision."

**YOU MUST NOT PROCEED WITHOUT EXPLICIT ORCHESTRATOR COMMAND.**

---

### Emergency States

**Multiple WorkGroupIDs**: Ask which to continue
**No active work**: Report no WorkGroupID found
**Ambiguous state**: Present evidence and request clarification
**User knows position**: Accept their input to override detection

---

## Success Factors

1. **Accuracy**: Correctly determine loop position
2. **Completeness**: Reconstruct all context
3. **Readiness**: Continue immediately WHEN INSTRUCTED
4. **Safety**: Verify everything, assume nothing
5. **Control**: STOP after reporting - await explicit orchestrator command

---

**FINAL INSTRUCTION: After providing your status report and next step recommendation, you must STOP and wait. Do not automatically execute any loop steps. The Orchestrator will provide the appropriate prompt when ready to continue.**

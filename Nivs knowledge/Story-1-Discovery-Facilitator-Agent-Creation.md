# Discovery Facilitator Agent Creation - Brownfield Addition

## User Story

As a user of the AI Diary System,
I want the Discovery Facilitator agent to dynamically load all psychology frameworks and facilitation methods available in the system,
So that I can access the full range of psychological insights and facilitation techniques during diary sessions without the agent being limited to hard-coded knowledge.

## Story Context

**Existing System Integration:**
- Integrates with: Existing discovery-facilitator.md agent definition
- Technology: Pure markdown with BMAD self-documenting patterns and LLM instructions
- Follows pattern: Agent definitions with psychological capabilities and embedded LLM instructions
- Touch points: `/data/knowledge/` directory (4 psychology frameworks), `/data/methods/` directory (11 methods across brainstorming/facilitation/goal-seeking subdirectories)

## Acceptance Criteria

**Functional Requirements:**

1. Agent includes dynamic file loading instructions for ALL files in `/data/knowledge/` directory (currently 4 psychology frameworks: facilitation-psychology-methods.md, goal-hierarchy-theory.md, motivation-language-patterns.md, sdt-framework.md)
2. Agent includes dynamic file loading instructions for ALL files in `/data/methods/` directory structure (currently 11 methods across brainstorming/, facilitation/, and goal-seeking/ subdirectories)
3. Agent implements method selection protocol offering 2 choices to user during sessions
4. Agent includes user-driven termination rules allowing users to end sessions naturally

**Integration Requirements:**

5. Existing Discovery Facilitator psychological capabilities continue to work unchanged 
6. New functionality follows existing BMAD self-documenting pattern with `<!-- LLM: -->` instructions
7. Integration with existing knowledge and methods files maintains current behavior while expanding access

**Quality Requirements:**

8. Agent references ALL files in data directories dynamically, not specific counts or hardcoded filenames
9. LLM instructions are embedded following established `<!-- LLM: -->` pattern
10. No regression in existing psychological facilitation capabilities verified

## Technical Notes

- **Integration Approach:** Add LLM instructions to existing discovery-facilitator.md that direct AI to dynamically load all available knowledge and methods files
- **Existing Pattern Reference:** Follow BMAD self-documenting patterns with `<!-- LLM: -->` instructions as seen in existing methods files
- **Key Constraints:** Must maintain pure markdown architecture, zero-code dependencies, and work across any AI platform (Claude Code/ChatGPT/Cursor)

## Definition of Done

- [ ] Functional requirements met: Dynamic loading instructions added for both data directories
- [ ] Integration requirements verified: Agent maintains existing capabilities while adding new system integration
- [ ] Existing functionality regression tested: Psychological facilitation capabilities remain intact
- [ ] Code follows existing patterns and standards: Uses BMAD self-documenting patterns with embedded LLM instructions
- [ ] Agent references ALL files in data directories without hardcoded counts or specific filenames
- [ ] Method selection protocol offers 2 choices to users during facilitation sessions
- [ ] User-driven termination rules allow natural session ending

## Risk and Compatibility Check

**Minimal Risk Assessment:**
- **Primary Risk:** Agent might fail to properly load or utilize all available knowledge and methods files
- **Mitigation:** Clear LLM instructions for dynamic file loading, explicit integration testing with existing data structure
- **Rollback:** Revert discovery-facilitator.md to current version, all existing functionality restored

**Compatibility Verification:**
- [ ] No breaking changes to existing APIs (file-based system, no APIs)
- [ ] Database changes are additive only (file-based system, no database)
- [ ] UI changes follow existing design patterns (follows BMAD markdown patterns)
- [ ] Performance impact is negligible (simple file references, minimal overhead)

## Validation Checklist

**Scope Validation:**
- [ ] Story can be completed in one development session (updating single agent file with integration instructions)
- [ ] Integration approach is straightforward (adding LLM instructions for file loading)
- [ ] Follows existing patterns exactly (BMAD self-documenting with `<!-- LLM: -->` instructions)
- [ ] No design or architecture work required (using established patterns and file structure)

**Clarity Check:**
- [ ] Story requirements are unambiguous (clear integration with specific data directories)
- [ ] Integration points are clearly specified (4 knowledge files, 11 methods files across subdirectories)
- [ ] Success criteria are testable (can verify dynamic loading, method selection, termination rules)
- [ ] Rollback approach is simple (revert single file to previous version)
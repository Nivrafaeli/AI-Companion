# Precise Rules for Writing LLM Instructions
## Analysis of Effective Instruction Patterns from Original Files

*Extracted by analyzing exactly HOW your original files give instructions to agents vs how I wrote them.*

---

## AGENT PREPARATION RULES

### 1. **Always Include Pre-Execution Reading Instructions**
**Your Pattern**:
```markdown
<!-- LLM INSTRUCTIONS: This protocol determines which type of session to execute.
     
     CRITICAL IMPLEMENTATION PROCESS:
     1. READ THIS ENTIRE PROTOCOL FIRST - Understand all decision points before starting
     2. LOAD PATIENT CONTEXT - Read all required patient files completely
```

**My Mistake**: Started with content without telling agent to read everything first
**Rule**: ALWAYS begin with explicit reading/preparation instructions. Use numbered steps.

### 2. **Specify Exact File Reading Order**
**Your Pattern**:
```markdown
1. **Load Patient Context**:
   - `AI-therapy/{patient}/profile.yaml` - Core patient information
   - `AI-therapy/{patient}/preferences.yaml` - Communication style
   - `AI-therapy/{patient}/all-session-summary.md` - Treatment overview
```

**My Mistake**: Generic "read patient files" without specific order or file names
**Rule**: Always list exact files to read, in specific order, with brief purpose for each.

---

## QUESTION/OPTION INSTRUCTION RULES

### 3. **Explicitly State Selection Method for Multiple Options**
**Your Pattern**:
```markdown
**Start with ONE broad question (choose based on patient's presentation):**
- "How has your week been?" (standard opener)
- "What's been on your mind since we last talked?" (if patient seems reflective)

**ASK ALL FOUR - these are required:**
- "Do you understand that this is AI therapy with these limitations?"
```

**My Mistake**: Listed questions without specifying selection method
**Rule**: Always specify exactly HOW to handle multiple options:
- **"Choose ONE based on [criteria]"**
- **"Ask ALL in order"**
- **"Use examples only if they fit naturally"**

### 4. **Use Conditional Instructions with Clear Triggers**
**Your Pattern**:
```markdown
**ONLY if concerning content emerges, respond naturally:**
- If mentions death: "When you say that, I want to make sure you're safe..."
- If severe distress: "It sounds like you're really struggling - are you having thoughts of hurting yourself?"
```

**My Mistake**: Vague conditional guidance
**Rule**: Use format **"ONLY if [specific trigger], then [exact response]"** with concrete examples.

---

## EXECUTION FLOW RULES

### 5. **Include Completion Criteria Before Moving Forward**
**Your Pattern**:
```markdown
### PHASE COMPLETION CRITERIA
**Don't move to next phase until:**
- **Phase 1**: Mood assessed, week reviewed, safety monitored
- **Phase 2**: Homework reviewed, learning extracted, barriers addressed
```

**My Mistake**: Assumed agent would know when phase was complete
**Rule**: Always specify exact completion criteria before each phase. Use format **"Don't proceed until: [specific checklist]"**

### 6. **Use Decision Tree Format for Complex Logic**
**Your Pattern**:
```markdown
```
IF High-Risk Crisis Indicators Present:
→ Execute `crisis-session-protocol.md`
→ STOP triage process

IF Medium-Risk Indicators Present:
→ Continue to Step 3 but flag for enhanced safety monitoring
```

**My Mistake**: Narrative explanations instead of clear decision trees
**Rule**: Use visual decision trees with arrows (→) and clear IF/THEN/ELSE structure.

---

## SELF-MONITORING INSTRUCTION RULES

### 7. **Include Agent Self-Check Prompts**
**Your Pattern**:
```markdown
### AGENT SELF-MONITORING
**Throughout session, continuously ask yourself:**
- "Have I completed this phase's objectives?"
- "Is the patient ready to move forward?"
- "Are there any red flags I need to address?"
```

**My Mistake**: No self-monitoring guidance for the agent
**Rule**: Include explicit self-questioning prompts that agents should ask themselves during execution.

### 8. **Build in Quality Verification Steps**
**Your Pattern**:
```markdown
### Address Missing Items (required if any unchecked)
**If ANY item missing:**
1. **STOP ending process**
2. **Address immediately**: "Before we finish, let me make sure we covered [missing area]"
3. **Complete missing element**
4. **Re-check list**
```

**My Mistake**: Quality checks without remediation steps
**Rule**: Always include **"If missing, then do this"** instructions with numbered steps.

---

## LANGUAGE PRECISION RULES

### 9. **Use Imperative Commands, Not Suggestions**
**Your Pattern**:
- "Execute `crisis-session-protocol.md` IMMEDIATELY"
- "DON'T ask direct safety questions unless indicators emerge"
- "READ THIS ENTIRE PROTOCOL FIRST"

**My Mistake**: 
- "You might want to consider..."
- "It would be helpful to..."
- "Consider using..."

**Rule**: Use direct commands. Start with action verbs: READ, EXECUTE, ASK, DON'T, STOP, CONTINUE.

### 10. **Specify Exact Quantities and Sequences**
**Your Pattern**:
- "Ask ALL FOUR questions in order"
- "Choose ONE based on patient presentation"
- "Use 2-3 specific examples"

**My Mistake**: "Ask some questions" or "provide examples"
**Rule**: Always specify EXACTLY how many items and in what order.

---

## ERROR HANDLING INSTRUCTION RULES

### 11. **Provide Explicit Failure Recovery Steps**
**Your Pattern**:
```markdown
### Missing Patient Data
**If required files are missing or incomplete:**
1. Treat as **new patient** and execute `first-session-protocol.md`
2. Recreate missing files using templates
3. Gather missing information during session
```

**My Mistake**: Assumed agent would figure out error recovery
**Rule**: For every possible failure point, provide numbered recovery steps.

### 12. **Include Override Instructions for Emergencies**
**Your Pattern**:
```markdown
**When red flags appear**: Stop current session protocol and re-run triage assessment
```

**My Mistake**: No emergency override instructions
**Rule**: Always include **"Stop everything and do this if..."** instructions for critical situations.

---

## FORMATTING RULES FOR CLARITY

### 13. **Use Visual Hierarchy with Consistent Patterns**
**Your Pattern**:
```markdown
### Required Actions Before Starting
1. **Load Patient Context**: [specific action]
2. **Execute Triage Decision Tree**: [specific action]

**ASK BOTH questions:**
1. "Of those options, what feels most urgent or important right now?"
2. "Is there anything else you really want to make sure we cover today?"
```

**My Mistake**: Inconsistent formatting without clear visual hierarchy
**Rule**: Use consistent formatting patterns:
- **Bold for emphasis on critical words**
- Numbered lists for sequential actions
- **"Required"** vs **"Optional"** clearly marked

### 14. **Include Implementation Examples**
**Your Pattern**:
```markdown
**Example flow (adapt to patient's responses):**
- **After they share**: "Tell me more about [specific thing they mentioned]"
- **For timeline**: "When did you first notice this happening?"
```

**My Mistake**: Abstract instructions without concrete examples
**Rule**: Always include **"Example:"** sections showing exactly how to implement abstract instructions.

---

## FILE REFERENCE RULES

### 15. **Use Exact File Paths and Names**
**Your Pattern**:
- "Execute `crisis-session-protocol.md`"
- "Reference `cbt-methods/cognitive-methods.md`"
- "Read `AI-therapy/{patient}/profile.yaml`"

**My Mistake**: "Use appropriate method files" or "refer to relevant protocols"
**Rule**: Always use exact file names with paths. Use backticks for file references.

### 16. **Specify What to Look For in Referenced Files**
**Your Pattern**:
```markdown
**Consult appropriate consolidated method file:**
**For Cognitive Work:**
- Reference `cbt-methods/cognitive-methods.md` (contains thought records, cognitive restructuring, downward arrow, evidence examination, etc.)
```

**My Mistake**: File references without explaining what to find there
**Rule**: When referencing files, specify exactly what information to extract from them.

---

## CRITICAL INSTRUCTION PATTERNS

### 17. **Mark Critical vs Optional Instructions**
**Your Pattern**:
- **"CRITICAL: Must deliver ALL content before proceeding"**
- **"Required questions"**
- **"Optional if fits naturally"**

**My Mistake**: All instructions seemed equally important
**Rule**: Use explicit priority markers: **CRITICAL**, **REQUIRED**, **OPTIONAL**, **EXAMPLES ONLY**.

### 18. **Include Stop/Continue Decision Points**
**Your Pattern**:
```markdown
**If consent not obtained**: Provide human therapist resources and end session respectfully
```

**My Mistake**: No clear exit/continuation criteria
**Rule**: Always include explicit **"If X, then STOP"** and **"If Y, then CONTINUE"** instructions.

---

## FINAL META-RULES FOR LLM INSTRUCTION WRITING

### 19. **Test Every Instruction for Literal Interpretation**
**Rule**: Read each instruction and ask: "Could an LLM misinterpret this?" If yes, add specificity.

### 20. **Assume Zero Prior Context**
**Rule**: Write as if the LLM has never seen these files before and needs complete guidance for each step.

### 21. **Use Progressive Disclosure**
**Rule**: Give instructions in the order they should be executed:
1. **Pre-execution setup** (what to read first)
2. **Phase-by-phase execution** (what to do when)
3. **Quality checks** (how to verify completion)
4. **Error recovery** (what to do if things go wrong)

---

## SUMMARY PATTERN FOR EFFECTIVE LLM INSTRUCTIONS

```markdown
<!-- LLM INSTRUCTIONS: [What this file does]

CRITICAL IMPLEMENTATION PROCESS:
1. READ [specific files] FIRST
2. UNDERSTAND [specific concepts]
3. EXECUTE [specific steps]

[Rest of detailed instructions following these patterns]
```

**The Golden Rule**: If you handed these instructions to a competent human who had never done this task before, could they execute it successfully without asking questions? If not, add more specificity.
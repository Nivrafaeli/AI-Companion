# Method Creation Guide

## How to Add New Methods to the AI Diary System

Based on BMAD's proven approach, here's how to create and add new facilitation, brainstorming, and goal-seeking methods.

## Method Description Format

### **Simple One-Line Execution**
Each method should have a **simple, clear execution instruction** - no over-engineering.

**Examples from BMAD:**
- **Five Whys**: Ask "why" and wait for their answer before asking next "why"
- **What If Scenarios**: Ask one provocative question, get their response, then ask another
- **Analogical Thinking**: Give one example analogy, ask them to find 2-3 more

### **Method Template Structure**

```markdown
**[Method Name]**: [One-line execution instruction]

**When to use**: [Brief context - 1 sentence]
**Natural completion**: [When/how it naturally ends]
**Capture**: [What insight/result to save in user files]

**Example flow:**
- [Step 1 example]
- [Step 2 example]
- [Natural completion example]
```

## Method Categories

### **1. Facilitation Methods** (`methods/facilitation/`)
**Purpose**: Help users explore thoughts and feelings deeper

**Examples:**
- Five Whys (explore motivations)
- Values Archaeology (uncover core beliefs)
- Emotion Mapping (understand feeling patterns)
- Future Self Dialog (explore identity goals)

### **2. Brainstorming Methods** (`methods/brainstorming/`)
**Purpose**: Generate creative solutions and possibilities

**Examples:**
- What If Scenarios (explore possibilities)
- Assumption Reversal (challenge beliefs)
- Metaphor Building (use analogies for insight)
- Time Shifting (past/future perspectives)

### **3. Goal-Seeking Methods** (`methods/goal-seeking/`)
**Purpose**: Clarify, organize, and achieve goals

**Examples:**
- Goal Hierarchy Mapping (understand goal relationships)
- Resource Availability Analysis (realistic goal setting)
- Obstacle Anticipation (prepare for challenges)
- Success Visualization (motivate through imagery)

## Writing Guidelines

### **Keep It Simple**
- **One-line execution** - no complex instructions
- **Natural flow** - let conversation evolve organically
- **User signals completion** - don't force rigid structure
- **Trust the LLM** - minimal instructions work better

### **Focus on Flow**
- Methods should **enhance conversation**, not interrupt it
- User should **barely notice** the structured approach
- **Seamless transitions** in and out of methods
- **Respect user resistance** - back off if they're not engaged

### **Natural Completion Signals**
Methods naturally complete when:
- User discovers insight ("Oh, I never thought of that!")
- User changes subject or asks different question
- User shows emotional response (breakthrough moment)
- Method reaches logical end (5 whys completed)
- User gives resistance signals ("I don't know", silence)

## Example Method Creation

### **Obstacle Anticipation Method**

```markdown
**Obstacle Anticipation**: Ask "What might get in the way?" then help them prepare for each obstacle mentioned

**When to use**: When user has clear goal but seems worried about achieving it
**Natural completion**: When user feels prepared or runs out of concerns
**Capture**: Main obstacles and preparation strategies in goals.md

**Example flow:**
- "What might get in the way of this goal?"
- [wait for their concerns]
- "How could you prepare for that obstacle?"
- [continue until they seem ready or change subject]
```

### **Energy Source Mapping**

```markdown
**Energy Source Mapping**: Ask "What gives you energy around this?" then explore those sources deeper

**When to use**: When user seems drained or stuck on a goal
**Natural completion**: When user identifies energy sources or topic shifts
**Capture**: Energy sources and patterns in patterns.md

**Example flow:**
- "What part of this actually gives you energy?"
- [wait for positive response]
- "Tell me more about what makes that energizing"
- [continue until energy patterns clear]
```

## File Organization

### **Methods Directory Structure**
```
data/
├── knowledge/                     # Theoretical information
│   ├── sdt-framework.md          # Psychology theories
│   ├── goal-hierarchy-theory.md  # Theoretical models
│   └── motivation-research.md     # Research insights
└── methods/                       # Practical workflows
    ├── facilitation/
    │   ├── five-whys.md
    │   ├── values-archaeology.md
    │   └── emotion-mapping.md
    ├── brainstorming/
    │   ├── what-if-scenarios.md
    │   ├── assumption-reversal.md
    │   └── metaphor-building.md
    └── goal-seeking/
        ├── goal-hierarchy-mapping.md
        ├── obstacle-anticipation.md
        └── success-visualization.md
```

### **Agent Integration Instructions**

```markdown
# In discovery-facilitator.md

## Method Selection Protocol

<!-- LLM: Read all files in data/methods/ for available techniques -->

**When user needs deeper exploration:**
1. Analyze their situation and emotional state
2. Select 2 most fitting methods from methods/ directory
3. Offer both: "We could [method A] or [method B]. What feels right?"
4. Execute chosen method using its simple instruction
5. Continue until natural completion signals appear

**Method categories:**
- **Facilitation**: Explore thoughts/feelings (methods/facilitation/)
- **Brainstorming**: Generate possibilities (methods/brainstorming/) 
- **Goal-seeking**: Clarify/achieve goals (methods/goal-seeking/)
```

## Testing New Methods

### **Before Adding:**
1. **Test in conversation** - try the method manually first
2. **Check natural flow** - does it enhance or interrupt dialogue?
3. **Validate completion** - do users naturally signal when done?
4. **Confirm value** - does it generate useful insights?

### **After Adding:**
1. **Monitor usage** - does agent select it appropriately?
2. **Check execution** - does agent follow simple instructions?
3. **Validate results** - are insights captured properly?
4. **User feedback** - do users find it helpful?

## Best Practices Summary

✅ **Simple one-line instructions**
✅ **Natural conversation flow** 
✅ **User-driven completion**
✅ **Trust LLM judgment**
✅ **Respect user signals**

❌ **Complex step-by-step processes**
❌ **Rigid numbered sequences**
❌ **Forced method completion**
❌ **Over-engineered instructions**
❌ **Ignoring user resistance**

Remember: The goal is **enhanced conversation**, not **structured interrogation**. Methods should feel like natural deepening of dialogue, not clinical procedures.
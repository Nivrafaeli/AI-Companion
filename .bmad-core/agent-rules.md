# BMAD Agent Rules

## Rule: Complex Question Presentation Protocol

When presenting complex questions or analysis with multiple sections that require user review, all BMAD agents must follow this protocol:

### Step 1: Present the Complete Question/Analysis
First, provide the user with the full question or analysis broken down into all relevant sections. This gives the user complete context and understanding of what needs to be reviewed.

### Step 2: Transition to Interactive Review
After presenting the complete analysis, immediately transition with:

**"Let's go section by section. I'll present you with 3 options for each section and my recommendation."**

### Step 3: Section-by-Section Review Process
For each section:

1. **Present 3 Options:**
   - **Option A:** [Description of first approach/choice]
   - **Option B:** [Description of second approach/choice] 
   - **Option C:** [Description of third approach/choice]

2. **Provide Your Recommendation:**
   - **My Recommendation:** [Clear recommendation with brief rationale]

3. **Wait for User Selection:**
   - Ask: "Which option do you prefer for this section?"

### Step 4: Implementation
- Only proceed to the next section after receiving user confirmation
- Keep track of user choices for final implementation
- Provide a summary of all choices at the end

### Example Flow:
```
[Complete analysis with all sections presented]

"Let's go section by section. I'll present you with 3 options for each section and my recommendation.

**Section 1: Architecture Approach**

Option A: Monolithic architecture with all services in one codebase
Option B: Microservices architecture with separate repositories  
Option C: Hybrid approach with core monolith and microservices for specific features

My Recommendation: Option B - Microservices architecture for better scalability and team independence

Which option do you prefer for this section?"
```

### Benefits:
- Ensures user has complete context before making decisions
- Breaks down complex decisions into manageable choices
- Provides clear recommendations while maintaining user agency
- Creates a structured, predictable interaction pattern
- Prevents overwhelming the user with too many choices at once

This rule applies to all BMAD agents: Analyst, Architect, BMAD Master, BMAD Orchestrator, Developer, Project Manager, Product Owner, QA, Scrum Master, and UX Expert.

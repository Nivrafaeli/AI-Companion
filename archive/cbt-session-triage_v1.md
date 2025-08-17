# CBT Session Triage Protocol

<!-- LLM INSTRUCTIONS: This protocol determines which type of session to execute.
     Follow this decision tree EVERY time before starting a session.
     Make decisions based on patient data and current presentation. -->

## Overview

This triage system analyzes the patient's current state and history to determine the appropriate session type. Execute this protocol before every therapeutic interaction.

## Step 1: Patient Status Check

### New Patient Assessment
**Check for existing patient files in `AI-therapy/{patient-name}/`**

**If NO patient directory exists:**
- **Decision**: Execute `first-session-protocol.md`
- **Rationale**: Initial assessment and engagement required
- **Skip remaining triage steps**

**If patient directory exists BUT profile.yaml is empty/minimal:**
- **Decision**: Execute `first-session-protocol.md` 
- **Rationale**: Incomplete initial assessment
- **Skip remaining triage steps**

## Step 2: Crisis Assessment

### Immediate Risk Evaluation
**Monitor NATURALLY during conversation for crisis indicators:**

#### High-Risk Crisis Indicators (Execute crisis-session-protocol.md IMMEDIATELY)
- **Direct suicidal statements**: "I want to die", "I'm going to kill myself"
- **Self-harm mentions**: Recent cutting, burning, or other self-injury
- **Psychotic symptoms**: References to voices, delusions, severe confusion
- **Severe intoxication**: Slurred speech, incoherent responses
- **Immediate danger statements**: Threats to self or others
- **Severe dissociation**: "I'm not real", complete detachment

#### Medium-Risk Indicators (Enhanced monitoring during regular session)
- **Hopelessness expressions**: "What's the point", "Nothing matters"
- **Death wishes**: "I wish I wouldn't wake up", "I'm tired of living"
- **Recent trauma mentions**: "Something terrible happened"
- **Substance concerns**: "I've been drinking a lot", "I used today"
- **Severe distress**: Overwhelming emotions, inability to function

#### Natural Assessment Approach
**DON'T directly ask about self-harm unless indicators emerge**

**Instead, use natural check-ins:**
- "How has your week been?"
- "What's been on your mind lately?"
- "How are you feeling today?"
- "Tell me what's been going on"

**ONLY ask direct safety questions IF suspicious content emerges:**
- If mentions death: "When you say that, I want to make sure you're safe..."
- If severe distress: "It sounds like you're really struggling - are you having thoughts of hurting yourself?"
- If concerning behavior: "I'm noticing... can we talk about your safety?"

### Crisis Decision Point
```
IF High-Risk Crisis Indicators Present:
→ Execute `crisis-session-protocol.md`
→ STOP triage process

IF Medium-Risk Indicators Present:
→ Continue to Step 3 but flag for enhanced safety monitoring
→ Use regular session with increased risk assessment

IF Low Risk:
→ Continue to Step 3
```

## Step 3: Treatment Status Evaluation

### Read Treatment History
**Required files to check:**
- `all-session-summary.md` - Overall treatment progress
- `last-session.yaml` - Most recent session details
- `profile.yaml` - Treatment goals and phase

### Treatment Phase Assessment

#### Assessment Phase (Sessions 1-3)
**Indicators:**
- Fewer than 4 completed sessions
- Primary goals not yet established
- Case formulation incomplete
- Basic CBT education not completed

**Decision**: Execute `first-session-protocol.md` if session 1, otherwise `regular-session-protocol.md` with assessment focus

#### Active Treatment Phase (Sessions 4-16)
**Indicators:**
- 4-16 sessions completed
- Clear treatment goals established
- Currently learning or applying CBT skills
- Making progress toward goals

**Decision**: Execute `regular-session-protocol.md`

#### Consolidation Phase (Sessions 17+)
**Indicators:**
- 17+ sessions completed
- Significant progress made on primary goals
- Strong CBT skill base established
- Preparing for treatment independence

**Decision**: Check for termination readiness

### Termination Readiness Assessment

#### Ready for Termination (Execute final-session-protocol.md)
**All criteria must be met:**
- **Goal Achievement**: Primary treatment goals largely met
- **Skill Mastery**: Patient demonstrates independent CBT skill use
- **Functioning**: Significant improvement in daily functioning
- **Stability**: Symptom reduction maintained for 4+ weeks
- **Confidence**: Patient expresses readiness for independence
- **Relapse Plan**: Patient can articulate coping strategies

#### Continue Treatment (Execute regular-session-protocol.md)
**If any criteria not met:**
- Goals not achieved or only partial progress
- Patient struggles with independent skill use
- Functioning still significantly impaired
- Recent setbacks or symptom increases
- Patient expresses need for continued support

## Step 4: Session Frequency Assessment

### Special Circumstances

#### Returning After Break
**Indicators:**
- Last session more than 2 weeks ago
- Patient took planned treatment break
- Life circumstances interrupted treatment

**Modifications:**
- Use `regular-session-protocol.md` with extended check-in
- Review coping strategies used during break
- Assess any changes in symptoms or functioning
- Update goals if life circumstances changed

#### Booster Session
**Indicators:**
- Treatment previously completed
- Patient returning for support with specific issue
- Relapse prevention or skill refresher needed

**Decision**: Execute `regular-session-protocol.md` with focused agenda

## Step 5: Final Session Type Decision

### Decision Matrix

| Patient Status | Crisis Level | Session Count | Treatment Progress | Session Type |
|----------------|--------------|---------------|-------------------|--------------|
| New Patient | Any | 0 | N/A | `first-session-protocol.md` |
| Existing | High Crisis | Any | Any | `crisis-session-protocol.md` |
| Existing | Low/Medium | 1-16 | Active/Building | `regular-session-protocol.md` |
| Existing | Low | 17+ | Goals Met | `final-session-protocol.md` |
| Existing | Low | 17+ | Goals Not Met | `regular-session-protocol.md` |
| Returning | Low | Any | Any | `regular-session-protocol.md` + extended check-in |

## Implementation Protocol

### Before Starting Session
1. **Load Patient Context**:
   ```
   - Read AI-therapy/{patient}/profile.yaml
   - Read AI-therapy/{patient}/all-session-summary.md  
   - Read AI-therapy/{patient}/last-session.yaml
   - Read AI-therapy/{patient}/preferences.yaml
   ```

2. **Execute Triage Decision Tree**:
   - Step 1: Check patient status (new vs existing)
   - Step 2: Assess crisis indicators
   - Step 3: Evaluate treatment phase
   - Step 4: Consider special circumstances
   - Step 5: Make final session type decision

3. **Document Triage Decision**:
   - Create `session-on-work.yaml`
   - Record triage reasoning and session type selected
   - Note any risk factors or special considerations

### Triage Documentation Template
```yaml
triage_assessment:
  date: "2025-08-14"
  patient_status: "existing_patient"  # new_patient, existing_patient, returning_patient
  crisis_level: "low"  # low, medium, high, critical
  session_count: 8
  treatment_phase: "active_treatment"  # assessment, skill_building, active_treatment, consolidation
  special_circumstances: []  # break_return, booster_session, crisis_followup
  
session_decision:
  type: "regular_session"  # first_session, regular_session, crisis_session, final_session
  protocol_file: "regular-session-protocol.md"
  modifications: ["enhanced_risk_monitoring"]  # any special adjustments needed
  
risk_factors:
  immediate: []  # any current session risks
  ongoing: ["work_stress", "relationship_conflicts"]  # chronic stressors to monitor
```

## Quality Assurance

### Triage Accuracy Checks
- **Review decision reasoning** with each patient file
- **Document rationale** for session type selection
- **Monitor outcomes** - did correct session type address patient needs?
- **Adjust criteria** based on effectiveness patterns

### Red Flags for Re-assessment
- Patient presentation doesn't match expected session type
- Unexpected crisis emergence during session
- Patient requests different session focus
- Safety concerns arise mid-session

**When red flags appear**: Stop current session protocol and re-run triage assessment

## Error Handling

### Unclear Triage Decisions
**If multiple session types seem appropriate:**
1. Default to **higher safety level** (crisis > regular > first)
2. Consider **patient preference** if explicitly stated
3. Choose **more structured approach** when uncertain
4. Document decision rationale for learning

### Missing Patient Data
**If required files are missing or incomplete:**
1. Treat as **new patient** and execute `first-session-protocol.md`
2. Recreate missing files using templates
3. Gather missing information during session
4. Document data gaps for future sessions

### Technical Issues
**If unable to access patient files:**
1. **Prioritize safety** - conduct basic risk assessment
2. Use **crisis-session-protocol.md** if any safety concerns
3. Operate in **limited capacity mode** with basic support
4. Recommend rescheduling if files cannot be accessed

---

**This triage system ensures every session is appropriately matched to patient needs while maintaining safety as the highest priority.**
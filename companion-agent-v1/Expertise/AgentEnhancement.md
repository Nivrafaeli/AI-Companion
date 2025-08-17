# Agent Enhancement Expertise

## Protocol for Adding New Abilities to Companion Agent

### Phase 1: Analysis & Planning
1. **Identify the Gap**
   - What ability is missing or broken?
   - What specific behavior should be added/changed?
   - Where in the system should this be implemented?

2. **Impact Assessment**
   - Which files need to be updated?
   - What dependencies are affected?
   - Are there any conflicts with existing functionality?

3. **Enhancement Design**
   - What new instructions/protocols are needed?
   - What new files need to be created?
   - How will this integrate with existing systems?

### Phase 2: Implementation Plan
1. **File Updates Required**
   - `.claude/commands/companion-agent.md` (main instructions)
   - `companion-agent-v1/agents/companion-agent-Documentation.md` (documentation)
   - Any dependency files (user-data/, methods/, Expertise/)
   - Any new files to be created

2. **Implementation Order**
   - Update activation instructions if needed
   - Update/create dependency files
   - Update main command file
   - Update documentation file
   - Test functionality

### Phase 3: Systematic Implementation
1. **Update Activation Instructions**
   - Add new steps to activation-instructions if needed
   - Update LIVE MEMORY PROTOCOL if needed
   - Add new file loading requirements

2. **Update/Create Dependencies**
   - Create new method files if needed
   - Update existing user-data files if needed
   - Add new expertise areas if needed

3. **Update Main Command File**
   - Add new commands if needed
   - Update persona/core_principles if needed
   - Add new dependencies to dependencies section
   - Update protocols and instructions

4. **Update Documentation File**
   - Sync all changes to companion-agent-v1/agents/companion-agent-Documentation.md
   - Maintain markdown format for documentation
   - Keep core concepts aligned between both files

### Phase 4: Quality Assurance Protocol
1. **File Verification Checklist**
   - [ ] Main command file updated (.claude/commands/)
   - [ ] Documentation file synced (companion-agent-v1/agents/)
   - [ ] All dependency files created/updated
   - [ ] All file paths are absolute and correct
   - [ ] YAML syntax is valid and properly closed

2. **Functionality Testing**
   - [ ] Agent loads successfully with new abilities
   - [ ] New commands work as expected
   - [ ] No existing functionality is broken
   - [ ] Memory/file systems work correctly
   - [ ] Integration with existing protocols works

3. **Content Quality Check**
   - [ ] Instructions are clear and explicit
   - [ ] No ambiguous or inferential language
   - [ ] All protocols are bulletproof step-by-step
   - [ ] User preferences are respected
   - [ ] Documentation is up-to-date

### Phase 5: Testing & Validation
1. **Reload Agent**
   - Use `*s` command to save and reload with new abilities
   - Verify all new functionality loads correctly

2. **Test New Abilities**
   - Execute new commands/behaviors
   - Verify integration with existing systems
   - Test edge cases and error handling

3. **User Validation**
   - Demonstrate new abilities to user
   - Get feedback on implementation
   - Make adjustments if needed

## File Update Templates

### Main Command File Update Template
```yaml
# Add to activation-instructions:
- STEP X: [New activation step if needed]

# Add to persona.core_principles:
- [New principle if behavior change]

# Add to commands:
- new-command: Description of new command

# Add to dependencies:
section-name:
  - new-file.md
```

### Documentation Sync Template
```markdown
# Convert YAML concepts to readable markdown
# Maintain alignment with main command file
# Keep examples and explanations user-friendly
```

## Common Enhancement Patterns

### Adding New Memory Capabilities
- Update LIVE MEMORY PROTOCOL
- Add new file to user-data/ dependencies
- Update activation instructions to load new file
- Add documentation trigger for when to update file

### Adding New Method Collections
- Create new method file in appropriate directory
- Add to dependencies section
- Add loading protocol with session tracking
- Add command to trigger loading

### Adding New Expertise Areas
- Create new expertise file in Expertise/
- Add auto-loading trigger conditions
- Add to dependencies and loading protocols
- Document when expertise should be used

### Modifying Core Behavior
- Update persona definition
- Update core_principles
- Update activation instructions
- Test thoroughly for behavior consistency

## Quality Standards for Enhancements

### Instruction Clarity
- Every instruction must be explicit and actionable
- No inferential or "figure it out" language
- Step-by-step protocols for all behaviors
- Clear trigger conditions for all actions

### File Organization
- Absolute paths for all file references
- Logical grouping in dependency sections
- Consistent naming conventions
- Proper directory structure

### Integration Standards
- New abilities must integrate seamlessly
- No conflicts with existing functionality
- Respect user preferences and communication style
- Maintain natural conversation flow

### Documentation Standards
- Both instruction and documentation files stay synced
- Clear examples and use cases
- User-friendly explanations
- Complete protocol documentation

## Enhancement Tracking Template

```markdown
### [Date] - [Enhancement Name]
- **Gap Identified**: [What was missing/broken]
- **Files Updated**: [List of all modified files]
- **New Abilities Added**: [Specific new capabilities]
- **Testing Results**: [What was verified]
- **User Feedback**: [User response to enhancement]
```

## Troubleshooting Enhancement Issues

### Common Problems
- **Agent won't load**: Check YAML syntax and file paths
- **New commands don't work**: Verify command definition and dependencies
- **Existing functionality broken**: Review changes for conflicts
- **Memory not updating**: Check LIVE MEMORY PROTOCOL updates

### Debugging Steps
1. Validate YAML syntax in main command file
2. Verify all file paths are absolute and correct
3. Test each new command individually
4. Reload agent to test integration
5. Check conversation history for error patterns

### Rollback Protocol
- Keep backups of all modified files
- Document all changes for easy reversal
- Test rollback procedures
- Have clear restoration steps

## Success Criteria for Enhancements

1. **Functionality**: New ability works as designed
2. **Integration**: Seamless integration with existing systems
3. **Quality**: Meets all quality standards
4. **User Satisfaction**: User confirms enhancement value
5. **Documentation**: All files properly updated and synced
6. **Testing**: All QA checklist items verified
7. **Stability**: No existing functionality broken
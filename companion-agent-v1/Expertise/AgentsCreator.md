# AgentsCreator Expertise

## Core Principles for Agent Development

### 1. User-Centered Design
- **Start with user needs** - understand what the user wants to achieve
- **Keep it simple** - avoid over-engineering
- **Test early** - get feedback and iterate quickly
- **Focus on value** - ensure the agent provides real benefit

### 2. Markdown-First Approach
- **Pure markdown** - no code dependencies
- **Human-readable** - clear, well-structured documentation
- **Version controlled** - easy to track changes
- **Portable** - works across different platforms

### 3. Modular Architecture
- **Separate concerns** - different files for different purposes
- **Reusable components** - methods and templates that can be shared
- **Clear interfaces** - well-defined command structures
- **Easy maintenance** - simple to update and improve

## Agent Structure Best Practices

### Command File Structure
```markdown
# /agent-name Command

When this command is used, adopt the following agent persona:

## COMPLETE AGENT DEFINITION FOLLOWS

```yaml
IDE-FILE-RESOLUTION:
  - Dependencies map to correct paths
  - Example: user-profile → /full/path/to/user-profile.md

activation-instructions:
  - STEP 1: Read THIS ENTIRE FILE
  - STEP 2: Adopt the persona defined below
  - STEP 3: Follow specific startup protocol
  - Additional steps as needed...

agent:
  name: Agent Name
  id: agent-id
  title: Agent Title
  icon: 🎯
  whenToUse: Clear description of when to use this agent

persona:
  role: Specific role description
  style: Communication style
  identity: Core identity
  focus: Primary focus areas
  core_principles:
    - Principle 1
    - Principle 2
    - Principle 3

commands:
  - command1: Description
  - command2: Description

dependencies:
  user-data:
    - file1.md
    - file2.md
  methods:
    - method1.md
    - method2.md
```

### File Organization
```
agent-project/
├── .claude/commands/
│   └── agent-name.md          # Main command file
├── agent-project/
│   ├── agents/
│   │   └── agent-name.md      # Documentation version
│   ├── user-data/
│   │   ├── user-profile.md
│   │   └── other-data.md
│   ├── methods/
│   │   ├── method1.md
│   │   └── method2.md
│   └── Expertise/
│       └── specialized-knowledge.md
```

## Development Process

### 1. Planning Phase
- **Define purpose** - what problem does this agent solve?
- **Identify user needs** - what does the user want to achieve?
- **Design persona** - what personality and approach?
- **Plan structure** - what files and methods are needed?

### 2. Implementation Phase
- **Create command file** - main agent definition
- **Build dependencies** - user data, methods, expertise
- **Test functionality** - ensure commands work properly
- **Refine behavior** - adjust based on testing

### 3. Documentation Phase
- **Create documentation** - explain how to use the agent
- **Update references** - keep all files in sync
- **Version control** - track changes and improvements
- **User feedback** - incorporate user suggestions

## Quality Standards

### Command File Requirements
- **Proper YAML syntax** - correctly formatted and closed
- **Clear activation instructions** - step-by-step startup process
- **Well-defined persona** - consistent personality and behavior
- **Comprehensive commands** - all necessary functionality
- **Correct dependencies** - proper file paths and references

### Content Standards
- **Clear language** - easy to understand
- **Consistent formatting** - uniform structure
- **Complete information** - no missing details
- **User-friendly** - accessible to target users

### Integration Standards
- **Compatible with Claude** - works with Claude's command system
- **Proper file paths** - absolute paths for reliability
- **Error handling** - graceful handling of missing files
- **Performance optimized** - efficient loading and operation

## Common Patterns

### Memory Management
- **User profiles** - store user information and preferences
- **Conversation history** - track important discussions
- **Progress tracking** - monitor goals and achievements
- **Pattern recognition** - identify recurring themes

### Method Organization
- **General methods** - broad approaches and techniques
- **Specialized methods** - domain-specific knowledge
- **Integration methods** - connecting different systems
- **Maintenance methods** - keeping systems running

### Expertise Areas
- **Domain knowledge** - specific subject matter expertise
- **Process knowledge** - how to accomplish tasks
- **Tool knowledge** - understanding available resources
- **Context knowledge** - situational awareness

## Troubleshooting

### Common Issues
- **File not found** - check absolute paths
- **YAML syntax errors** - validate YAML structure
- **Missing dependencies** - ensure all referenced files exist
- **Command conflicts** - avoid duplicate command names

### Debugging Steps
- **Check file paths** - verify all paths are correct
- **Validate YAML** - ensure proper syntax
- **Test commands** - verify each command works
- **Review dependencies** - confirm all files are accessible

### Performance Optimization
- **Lazy loading** - only load files when needed
- **Efficient queries** - minimize file system access
- **Caching strategies** - avoid redundant loading
- **Memory management** - clear unused data

## Best Practices Summary

1. **Start simple** - build basic functionality first
2. **Test frequently** - validate each component
3. **Document everything** - keep clear records
4. **Iterate quickly** - make improvements based on feedback
5. **Maintain consistency** - follow established patterns
6. **Focus on value** - ensure real benefit to users
7. **Keep it readable** - use clear, simple language
8. **Version control** - track all changes
9. **User feedback** - incorporate user input
10. **Continuous improvement** - always look for ways to enhance
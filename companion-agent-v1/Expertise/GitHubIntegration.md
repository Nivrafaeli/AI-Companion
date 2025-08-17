# GitHub Integration Expertise

## Core Functionality
This expertise enables the companion agent to save itself and the entire project to GitHub automatically, providing version control and backup capabilities.

## File Dependencies
- **external-services.md**: Contains GitHub credentials and tokens
- **github-settings.md**: Contains repository settings and preferences

## Authentication Protocol

### Credential Loading
```bash
# Load credentials from external-services.md
username=$(grep "Username" external-services.md | cut -d: -f2 | xargs)
token=$(grep "Personal Access Token" external-services.md | cut -d: -f2 | xargs)
repo_url=$(grep "Repository" external-services.md | cut -d: -f2- | xargs)
```

### Repository Setup (One-time)
```bash
# Add remote origin if not exists
git remote add origin https://github.com/Nivrafaeli/AI-Companion.git

# Or update existing remote
git remote set-url origin https://github.com/Nivrafaeli/AI-Companion.git
```

## GitHub Save Protocol

### Pre-commit Checks
1. **Verify authentication**: Check if external-services.md contains valid token
2. **Check git status**: Ensure repository is clean or has changes to commit
3. **Verify remote**: Ensure remote repository is properly configured
4. **Load settings**: Read preferences from github-settings.md

### Commit Process
1. **Stage all changes**: `git add .`
2. **Create commit message**: Use standard format with companion signature
3. **Commit locally**: `git commit -m "message"`
4. **Push to remote**: `git push origin main` with token authentication

### Commit Message Format
```
[Type]: [Description]

🤖 Generated with Companion Agent (Asa)
Co-Authored-By: Asa <companion@ai.agent>
```

**Types**: feat, fix, docs, refactor, save, backup, milestone

## Authentication Methods

### HTTPS with Personal Access Token
```bash
# Use token in URL for authentication
git push https://${username}:${token}@github.com/Nivrafaeli/AI-Companion.git main
```

### Error Handling
- **Invalid token**: Prompt user to update external-services.md
- **Network issues**: Retry with exponential backoff
- **Merge conflicts**: Alert user and provide guidance
- **Repository not found**: Verify repository URL and permissions

## Command Implementation

### Two-Save Strategy

#### *github-save Command (Incremental Saves)
**Purpose**: Quick backup during development - work in progress
**Process**:
1. Load GitHub settings and credentials
2. Show summary of changes to be committed
3. Ask user for confirmation
4. Execute git add, commit, push sequence
5. Report success/failure status

**Commit Format**: "save: [description] - work in progress"

#### *github-version-save Command (Major Milestones)
**Purpose**: Complete milestone with full documentation and versioning
**Process**:
1. Load GitHub settings and credentials
2. Determine next version number (v1.1, v1.2, etc.)
3. Auto-generate comprehensive version documentation (complete agent concept + version differences from last documentation file)
4. **Update previous version documentation** - Read Save1 format and update previous version doc with complete implemented capabilities
5. Save documentation to DOCUMENTATION/versions/
6. Show summary of changes + new documentation
7. Ask user for confirmation
8. Execute git add, commit, push sequence
9. Create git tag for version
10. Report success with version info

**Commit Format**: "version: v[X.Y] - [capability summary] with full documentation"
**Git Tag**: v[X.Y]
**Documentation**: Auto-generated in DOCUMENTATION/versions/v[X.Y] - [Summary].md
**Documentation Content**: Complete agent concept and capabilities (like Save1 format) + version differences from previous version

### Documentation Update Protocol

#### Previous Version Documentation Update
**When**: During step 4 of `*github-version-save` process
**Purpose**: Ensure previous version documentation reflects complete implemented capabilities, not just planned features
**Process**:
1. **Read Save1 format reference** - Use Save1 - Basic companion abilities.md as template structure
2. **Identify previous version** - Find the most recent version documentation file
3. **Update with complete capabilities** - Replace planned features with actual implemented capabilities
4. **Include full agent concept** - Core identity, principles, complete abilities system
5. **Add complete command system** - All implemented commands with descriptions
6. **Document file structure** - Complete file linkages and dependencies as implemented
7. **Preserve version history** - Keep changelog and improvement sections

#### New Version Documentation Creation
**When**: After previous version update is complete
**Purpose**: Create comprehensive standalone documentation for new version when complete
**Content Structure**:
- **Executive Summary**: Complete agent concept and purpose
- **Core Agent Identity**: Persona and principles (from existing standards)
- **Complete Abilities System**: All systems implemented in this version
- **Complete Command System**: All available commands
- **Improvements from Previous Version**: What's new/changed
- **File Structure**: Current organization and linkages
- **Implementation Details**: Technical details and protocols
- **Version History**: Previous versions and evolution

## File Management

### What Gets Committed
- **Entire AI-Companion project** (as specified by user)
- **All companion-agent-v1 files** including:
  - User data files (except sensitive tokens)
  - Method files
  - Expertise files
  - Documentation folder
- **Project-level files** (.claude commands, etc.)

### Exclusions (.gitignore)
```gitignore
# Sensitive information
**/external-services.md

# Temporary files
.DS_Store
*.tmp
*.log

# IDE files
.vscode/settings.json
.cursor/
```

## Security Considerations

### Token Security
- **Never commit tokens**: Add external-services.md to .gitignore
- **Token expiry tracking**: Monitor 60-day expiration
- **Rotation protocol**: Process for updating expired tokens

### Access Control
- **Repository permissions**: Ensure agent has necessary push access
- **Token scopes**: Minimum required permissions (repo access)
- **Authentication validation**: Verify credentials before operations

## Error Recovery

### Common Issues
1. **Authentication failure**: Check token validity and permissions
2. **Remote not configured**: Run repository setup protocol
3. **Merge conflicts**: Guide user through resolution
4. **Network timeout**: Implement retry logic with backoff

### Debugging Steps
1. **Check git status**: Verify repository state
2. **Test authentication**: Validate credentials with simple operation
3. **Verify remote**: Ensure remote URL is correct
4. **Check permissions**: Verify token has repo access

## Integration with Agent Enhancement

### When GitHub Integration is Triggered
- **Agent development tasks**: When creating or modifying agent files
- **Milestone completion**: After significant feature development
- **Documentation updates**: When DOCUMENTATION folder is updated
- **User explicit request**: Via *github-save command

### Loading Protocol
```yaml
# Add to main agent dependencies
dependencies:
  Expertise:
    - GitHubIntegration.md

# Add loading trigger
- GITHUB OPERATIONS: When user requests GitHub save or backup operations
```

## Testing Protocol

### Initial Setup Test
1. **Repository connection**: Verify remote is properly configured
2. **Authentication test**: Perform simple git operation with credentials
3. **Commit test**: Create test commit and push to verify full workflow
4. **Rollback test**: Ensure ability to revert if needed

### Regular Testing
- **Token validity**: Check authentication before each operation
- **Repository status**: Verify no conflicts or issues
- **Network connectivity**: Ensure GitHub is accessible

## User Communication

### Success Messages
```
✅ Successfully saved to GitHub!
📊 Committed: [number] files changed
🔗 View at: https://github.com/Nivrafaeli/AI-Companion/commit/[hash]
```

### Error Messages
```
❌ GitHub save failed: [specific error]
🔧 Suggested action: [specific fix]
📋 Need help? Use *github-help command
```

### Confirmation Prompts
```
📋 Ready to save to GitHub:
   • [number] files changed
   • Commit message: "[message]"
   • Push to: main branch
   
Continue? (y/n):
```

## Maintenance Protocol

### Token Renewal
- **Monitor expiry**: Track 60-day token expiration
- **Renewal reminder**: Alert user 7 days before expiry
- **Update process**: Guide user through token regeneration

### Repository Maintenance
- **Regular cleanup**: Remove old branches if created
- **Size monitoring**: Track repository size growth
- **History management**: Ensure important commits are preserved

## Command Reference

### Available Commands
- **github-save**: Manual save to GitHub with confirmation
- **github-status**: Show current git status and GitHub connection
- **github-help**: Display GitHub integration help and troubleshooting
- **github-setup**: Re-run initial repository setup if needed

### Implementation Requirements
```yaml
# Add to agent commands section
commands:
  - github-save: Save entire project to GitHub (loads GitHubIntegration.md when triggered)
  - github-status: Show git and GitHub connection status
  - github-help: GitHub integration help and troubleshooting
```

## Future Enhancements

### Advanced Features
- **Branch management**: Create feature branches for major changes
- **Release tagging**: Tag milestone versions
- **Pull requests**: Create PRs for major changes instead of direct commits
- **Automated backup**: Scheduled saves based on activity

### Integration Opportunities
- **CI/CD pipelines**: Trigger builds on commits
- **Issue tracking**: Link commits to GitHub issues
- **Project management**: Integration with GitHub Projects
- **Collaboration**: Multi-user agent development workflows

## Best Practices

### Commit Frequency
- **Major milestones**: Always commit after significant developments
- **Feature completion**: Commit when new abilities are fully implemented
- **Documentation updates**: Commit when documentation is created or updated
- **User request**: Always honor explicit save requests

### Message Quality
- **Descriptive**: Clear description of what changed
- **Consistent format**: Follow established message template
- **Attribution**: Always include companion agent signature
- **Context**: Reference specific features or fixes when relevant

### Repository Hygiene
- **Regular commits**: Avoid massive commits with too many changes
- **Clean history**: Ensure commits are logical and focused
- **Documentation sync**: Keep documentation updated with code changes
- **Security**: Never commit sensitive information

---

**Expertise Status**: Ready for integration and testing
**Dependencies**: external-services.md, github-settings.md
**Auto-loading**: When GitHub operations requested
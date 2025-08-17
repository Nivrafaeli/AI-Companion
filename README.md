# 🤗 AI Companion Agent

A flexible personal AI companion system built with Claude, featuring persistent memory, adaptive learning, and extensible capabilities.

## 🌟 What is AI Companion?

AI Companion is a personal AI assistant that remembers your story, understands your needs, and provides personalized support that grows with you. Unlike traditional AI tools, this companion builds a lasting relationship and can be extended with new capabilities as your needs evolve.

### Key Features

- **🧠 Persistent Memory**: Remembers your story, goals, and preferences across sessions
- **🔄 Adaptive Learning**: Continuously improves understanding of your needs
- **🔧 Extensible Architecture**: Easy to add new capabilities and methods
- **📦 Modular Design**: Separate components for different types of support
- **📝 Conversation History**: Tracks important insights and progress over time
- **⚡ Fast Iteration**: Built for rapid development and improvement

## 🚀 Quick Start

### Prerequisites
- Claude AI (Sonnet 4 or Opus recommended)
- Cursor IDE or VS Code
- Basic familiarity with markdown files

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ai-companion.git
   cd ai-companion
   ```

2. **Set up Claude commands**
   - Copy `.claude/commands/companion-agent.md` to your Claude commands directory
   - Ensure the file paths in the YAML configuration match your system

3. **Activate your companion**
   - In Claude, type: `/companion-agent`
   - Your companion "Asa" will greet you and begin learning about you

## 📁 Project Structure

```
companion-agent-v1/
├── .claude/commands/
│   └── companion-agent.md          # Main agent command file
├── companion-agent-v1/
│   ├── user-data/                  # User memory and preferences
│   │   ├── user-profile.md         # Core user information
│   │   ├── user-preferences.md     # Communication preferences
│   │   ├── thinking-patterns.md    # Behavioral patterns
│   │   ├── conversation-history.md # Conversation tracking
│   │   ├── goals-tracker.md        # Goal progress tracking
│   │   └── patterns-observed.md    # Observed patterns
│   ├── companion-methods/          # Guidance methods
│   │   ├── advice-methods.md       # Decision-making frameworks
│   │   └── belief-challenging-methods.md # Overcoming limiting beliefs
│   ├── Expertise/                  # Specialized knowledge
│   │   ├── AgentsCreator.md        # Agent development expertise
│   │   └── AgentEnhancement.md     # System enhancement protocols
│   └── agents/                     # Documentation
│       └── companion-agent-Documentation.md
```

## 🎯 Available Commands

Once activated, your companion responds to these commands:

- `*help` - Show available commands
- `*profile` - Display current understanding of you
- `*update-profile` - Update profile based on conversation
- `*advice` - Get guidance on decisions (loads advice methods)
- `*challenge` - Challenge limiting beliefs and assumptions (loads belief-challenging methods)
- `*expertise` - Access specialized knowledge (loads expertise files)
- `*save` - Update all memory files
- `*s` - Save and reload with updated memories
- `*exit` - End session and save memories

*Note: Commands may vary based on your agent's current capabilities and loaded methods.*

## 🧠 Memory System

### What Your Companion Remembers
- **Your Story**: Background, experiences, important relationships
- **Your Goals**: What you're working toward and why it matters
- **Your Patterns**: How you think, decide, and approach challenges
- **Your Preferences**: How you like to be supported and communicated with
- **Our History**: Key conversations, insights, and advice given

### Memory Files
- **Live Documentation**: Updates during conversation
- **Pattern Recognition**: Automatically documents observed patterns
- **Session Persistence**: Remembers across conversations
- **Automatic Syncing**: Save/reload commands for memory management

## 🔧 Customization

### Personalizing Your Companion

1. **Edit user-profile.md** - Add your background, goals, and preferences
2. **Modify user-preferences.md** - Set your communication style preferences
3. **Update thinking-patterns.md** - Document your decision-making patterns
4. **Customize existing methods** - Adapt current methods to your needs

### Adding New Capabilities

1. **Create new method files** in `companion-methods/` for new guidance approaches
2. **Add expertise areas** in `Expertise/` for specialized knowledge
3. **Update the YAML configuration** in the main command file to include new dependencies
4. **Test and iterate** based on your needs and use cases
5. **Document new features** in the appropriate documentation files

## 🛠️ Development

### Architecture Principles
- **Markdown-First**: Pure markdown with no code dependencies
- **Modular Design**: Separate concerns into different file types
- **User-Centered**: Built around user needs and preferences
- **Fast Iteration**: Designed for rapid development and improvement

### Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📚 Documentation

- **Agent Documentation**: `companion-agent-v1/agents/companion-agent-Documentation.md`
- **Development Guide**: `companion-agent-v1/Expertise/AgentsCreator.md`
- **Enhancement Protocols**: `companion-agent-v1/Expertise/AgentEnhancement.md`

## 🔄 Version History

- **v1.0** - Initial release with core companion capabilities
- Memory system with user profiles and conversation history
- Extensible architecture for adding new capabilities
- Modular design for different types of support
- Agent development expertise for system enhancement

## 🤝 Support

- **Issues**: Report bugs or request features via GitHub Issues
- **Discussions**: Join community discussions for tips and improvements
- **Documentation**: Check the documentation files for detailed guides

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with Claude AI by Anthropic
- Inspired by cognitive behavioral therapy principles
- Designed for personal growth and decision support

---

**Start your journey with a companion that truly understands you.** 🤗

# Code Studio Agent Library

A comprehensive collection of pre-configured custom agents for Syncfusion Code Studio. These specialized agents deliver consistent expertise across end-to-end workflows, reduce setup time, enforce team standards, and make outcomes repeatable.

## 📖 What are Custom Agents?

Custom agents are specialized versions of Syncfusion Code Studio that consist of:
- **Specific instructions** that define how the AI should behave for a given task
- **Tool configurations** that control which capabilities the agent can access
- **Consistent personas** tailored to specific development roles and tasks

This repository provides ready-to-use custom agents so you can immediately benefit from specialized expertise without creating them from scratch.

## ✨ Why Use This Library?

### Pre-configured Expertise
- **No setup required** - Each agent comes with detailed instructions and optimal tool configurations
- **Battle-tested workflows** - Agents are designed based on real-world development scenarios
- **Consistent behavior** - Get the same quality output every time

### Time Savings
- **Skip agent creation** - No need to write instructions from scratch
- **Instant productivity** - Start using specialized agents immediately
- **Team standardization** - Everyone uses the same proven agents

### Customizable Foundation
- **Modify to fit your needs** - All agents can be customized for your workflow
- **Learn by example** - See how professional agents are structured
- **Extend functionality** - Add handoffs and tool permissions as needed

## 📥 Installation

### Option 1: Workspace Installation (Team Sharing)

For sharing agents with your team via source control:

1. **Clone this repository:**
   ```bash
   git clone https://github.com/syncfusion/code-studio-agent-library.git
   ```

2. **Copy agents to your project's `.codestudio/agents/` folder:**
   ```bash
   # Create the directory if it doesn't exist
   mkdir -p YOUR-PROJECT/.codestudio/agents/
   
   # Copy all agent files
   cp code-studio-agent-library/*/*.agent.md YOUR-PROJECT/.codestudio/agents/
   ```

3. **Agents are automatically detected** by Code Studio - no restart needed!

### Option 2: User Profile Installation (Personal Use)

For using agents across all your projects:

1. **Download this repository**

2. **Copy agents to your user profile:**
   - **Windows**: `%USERPROFILE%\.codestudio\agents\`
   - **Mac/Linux**: `~/.codestudio/agents/`

3. **Code Studio automatically detects** the new agents

## 🚀 Quick Start

### Using Custom Agents

1. **Open Chat View** in Code Studio
2. **Click the agent dropdown** (left bottom of the chat interface)
3. **Select your desired agent** from the list
4. **Start chatting** - the agent follows its specialized instructions

📚 Learn more: [Code Studio Custom Agents Documentation](https://help.syncfusion.com/code-studio/reference/configure-properties/custom-agents)

## 📋 Complete Agent List

### 🎨 Design Department (`design/`)

- **[ui-designer](design/ui-desginer.agent.md)** - Create beautiful, functional interfaces that can be implemented quickly within rapid development cycles
- **[ux-researcher](design/ux-researcher.agent.md)** - Bridge the gap between user needs and rapid product development through lean research methodologies and actionable insights

### 🔧 Engineering Department (`engineering/`)

- **[backend-architect](engineering/backend-architect.agent.md)** - Design scalable APIs, databases, and server-side systems with proper security and performance optimization
- **[devops-automator](engineering/devops-automator.agent.md)** - Transform manual deployments into smooth, automated workflows with CI/CD pipelines and infrastructure as code
- **[rapid-prototyper](engineering/rapid-prototyper.agent.md)** - Transform ideas into functional applications at breakneck speed, build MVPs in days not weeks
- **[test-writer](engineering/test-writer.agent.md)** - Write comprehensive tests and maintain test suite integrity through intelligent test execution and repair

### 📣 Marketing Department (`marketing/`)

- **[content-creator](marketing/content-creator.agent.md)** - Generate cross-platform content from long-form blog posts to engaging video scripts and social media content

### 🧪 Testing & Benchmarking (`testing/`)

- **[api-tester](testing/api-tester.agent.md)** - Ensure APIs are battle-tested with comprehensive performance, load, and contract testing
- **[performance-benchmarker](testing/performance-benchmarker.agent.md)** - Turn sluggish applications into lightning-fast experiences through comprehensive performance testing and optimization
- **[tool-evaluator](testing/tool-evaluator.agent.md)** - Cut through marketing hype with rapid tool assessment and clear recommendations for development frameworks and services

### 📄 Documentation (`documentation/`)

- **[codebase-documenter](documentation/codebase-documenter.agent.md)** - Automatically generate comprehensive documentation for codebases, ensuring clarity and maintainability.

## 💡 Best Practices

1. **Let agents work together** - Many tasks benefit from multiple agents collaborating
2. **Be specific** - Clear task descriptions help agents perform better
3. **Trust the expertise** - Agents are designed for their specific domains
4. **Iterate quickly** - Agents support rapid development and iteration

## 📝 License

Copyright (c) Syncfusion Inc. All rights reserved.

Licensed under the [Syncfusion](https://downloads.sfcodestudio.com/eula/v1.0/code_studio_eula.pdf) license.

## 🔗 Resources

- [Code Studio Documentation](https://help.syncfusion.com/code-studio)
- [Custom Agents Guide](https://help.syncfusion.com/code-studio/reference/configure-properties/custom-agents)
- [Syncfusion Community Forum](https://www.syncfusion.com/forums)
- [Code Studio Download](https://www.syncfusion.com/code-studio)

---

Built with ❤️ for the Code Studio community

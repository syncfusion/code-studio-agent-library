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
   git clone https://github.com/YOUR-ORG/code-studio-agent-library.git
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

### Example Usage

- **rapid-prototyper**: "Create a new dashboard app with data visualization"
- **ui-designer**: "Design a modern login interface with dark mode support"
- **ux-researcher**: "Create a user journey map for our onboarding flow"
- **backend-architect**: "Design a RESTful API for our social sharing feature"
- **devops-automator**: "Set up CI/CD pipeline with automated deployments"
- **test-writer**: "Write tests for the authentication module"
- **api-tester**: "Test our REST API endpoints under heavy load"
- **performance-benchmarker**: "Profile our application and identify bottlenecks"
- **tool-evaluator**: "Should we use GraphQL or REST for our new API?"
- **content-creator**: "Create blog posts and social media content for our product launch"

## 📁 Directory Structure

Agents are organized by department for easy discovery:

```
code-studio-agent-library/
├── design/
│   ├── ui-designer.agent.md
│   └── ux-researcher.agent.md
├── engineering/
│   ├── backend-architect.agent.md
│   ├── devops-automator.agent.md
│   ├── rapid-prototyper.agent.md
│   └── test-writer.agent.md
├── marketing/
│   └── content-creator.agent.md
└── testing/
    ├── api-tester.agent.md
    ├── performance-benchmarker.agent.md
    └── tool-evaluator.agent.md
```

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

## 💡 Best Practices

1. **Let agents work together** - Many tasks benefit from multiple agents collaborating
2. **Be specific** - Clear task descriptions help agents perform better
3. **Trust the expertise** - Agents are designed for their specific domains
4. **Iterate quickly** - Agents support rapid development and iteration

## 🔧 Technical Details

### Agent File Structure

Each custom agent is defined in an `.agent.md` file with the following structure:

```markdown
---
name: agent-name
description: Brief description that appears in the chat interface
model: claude-sonnet-4.5
tools: ['read', 'edit', 'search', 'web']
handoffs:
  - label: Next Step
    agent: another-agent
    prompt: Pre-filled message for next agent
    send: false
---

# Agent Instructions

Detailed instructions in Markdown format that define:
- Agent's role and expertise
- Primary responsibilities
- Decision-making frameworks
- Best practices
- Examples and patterns
```

### Key Configuration Properties

- **name**: Unique identifier for the agent (e.g., `ui-designer`)
- **description**: Short hint shown in chat input area
- **model**: AI model powering the agent (e.g., `claude-sonnet-4.5`, `gpt-5-mini`)
- **tools**: Array of capabilities the agent can use:
  - `read`: Read files and directories
  - `edit`: Modify files
  - `search`: Search across workspace
  - `web`: Access web resources
  - `execute`: Run terminal commands
  - `agent`: Launch sub-agents
  - `myserver/*`: Include all tools from an MCP server
- **handoffs** (optional): Define workflow transitions to other agents

### Creating New Agents

1. **Create a new `.agent.md` file** in the appropriate department folder
2. **Add YAML frontmatter** with configuration between `---` markers
3. **Write detailed instructions** in Markdown below the frontmatter
4. **Include examples** showing when to use the agent
5. **Define handoffs** if the agent is part of a workflow
6. **Save the file** - Code Studio automatically detects it
7. **Test thoroughly** with real-world scenarios

## 🔄 Agent Workflows & Handoffs

Custom agents support **handoffs** - seamless transitions from one specialized agent to another with a single click. This enables guided workflows where each agent handles their specific expertise.

### Example Workflows

**Full-Stack Development Workflow:**
```
rapid-prototyper → backend-architect → ui-designer → test-writer → devops-automator
```

**Design & Research Workflow:**
```
ux-researcher → ui-designer → test-writer → performance-benchmarker
```

**Infrastructure & Deployment Workflow:**
```
backend-architect → devops-automator → performance-benchmarker → api-tester
```

**Tool Selection Workflow:**
```
tool-evaluator → rapid-prototyper → performance-benchmarker
```

**Content Creation Workflow:**
```
content-creator → (review) → (publish)
```

### How Handoffs Work

When a handoff is configured:
1. Agent completes their task
2. **Handoff button appears** in the chat interface
3. Click to **transition to next agent** with context
4. Next agent receives a **pre-filled prompt** to continue work

This eliminates manual switching and ensures consistent workflows across your team.

## 🎯 When to Use Each Agent

### Design
- **ui-designer** - Creating user interfaces, designing components, improving visual aesthetics
- **ux-researcher** - Conducting user research, creating journey maps, validating design decisions

### Engineering
- **backend-architect** - Designing APIs, building databases, architecting scalable backend systems
- **devops-automator** - Setting up CI/CD, configuring cloud infrastructure, automating deployments
- **rapid-prototyper** - Starting new projects, building MVPs, creating proof-of-concepts
- **test-writer** - Writing comprehensive tests, fixing failing tests, improving test coverage

### Marketing
- **content-creator** - Generating blog posts, video scripts, social media content

### Testing
- **api-tester** - Testing API performance, load testing, contract validation
- **performance-benchmarker** - Measuring speed, identifying bottlenecks, optimizing performance
- **tool-evaluator** - Evaluating frameworks, comparing services, making tool recommendations

## 🛠️ Customizing Agents

### Editing Existing Agents

1. **Navigate to the agents folder:**
   - **Workspace**: `YOUR-PROJECT/.codestudio/agents/`
   - **User Profile**: 
     - Windows: `%USERPROFILE%\.codestudio\agents\`
     - Mac/Linux: `~/.codestudio/agents/`

2. **Open the `.agent.md` file** you want to edit (e.g., `ui-designer.agent.md`)

3. **Make your changes** to the YAML frontmatter or instructions

4. **Save** (Ctrl+S or ⌘S) - changes take effect immediately

5. **Switch to the agent** in Code Studio to use the updated configuration

### Agent Customization Checklist

#### 📋 Required Components

**YAML Frontmatter (between `---` markers):**
- `name`: Unique agent identifier (kebab-case)
- `description`: Short description for chat interface (1-2 sentences)
- `model`: AI model to use (optional, defaults to workspace setting)
- `tools`: Array of tool permissions the agent needs
- `handoffs`: Workflow transitions (optional)

**Instruction Section (Markdown below frontmatter):**
- Agent Identity: Clear role definition and expertise area
- Core Responsibilities: 5-8 specific primary duties
- Domain Expertise: Technical skills and knowledge areas
- Best Practices: Specific methodologies and approaches
- Decision Frameworks: When to use different approaches
- Examples: Real-world usage scenarios

#### 🎯 Required Examples by Agent Type

**Engineering Agents need examples for:**
- Feature implementation requests
- Bug fixing scenarios
- Code refactoring tasks
- Architecture decisions

**Design Agents need examples for:**
- New UI component creation
- Design system work
- User experience problems
- Visual identity tasks

**Marketing Agents need examples for:**
- Campaign creation requests
- Platform-specific content needs
- Brand positioning tasks

**Testing Agents need examples for:**
- Performance analysis
- Test automation
- Quality assurance scenarios

## 📊 Agent Performance

Track agent effectiveness through:

- Task completion time
- User satisfaction
- Error rates
- Feature adoption
- Development velocity

## 🎯 Best Practices for Custom Agents

### Keep Instructions Clear
- Use bullet points and short sentences
- Avoid long paragraphs
- Be specific about agent behavior

### Use Handoffs Wisely
Create logical workflows that guide users through processes:
```
Plan → Develop → Review → Test → Deploy
```

### Tool Configuration
- **Read-only agents** (planners, reviewers): `['read', 'search', 'web']`
- **Development agents**: `['read', 'edit', 'search', 'execute']`
- **Testing agents**: `['read', 'edit', 'search', 'execute', 'web']`
- **All tools from MCP server**: `['myserver/*']`

### Agent Specialization
Each agent should have a clear, focused purpose:
- ✅ Good: "Reviews code for security vulnerabilities"
- ❌ Too broad: "Helps with coding"

## 🤝 Contributing

To improve existing agents or suggest new ones:

1. **Fork this repository**
2. **Create/modify agents** following the structure guidelines
3. **Test thoroughly** with real projects
4. **Document changes** in your pull request
5. **Submit PR** with clear descriptions of improvements

### Contribution Guidelines
- Maintain consistent file naming: `agent-name.agent.md`
- Follow the YAML frontmatter structure
- Write clear, actionable instructions
- Include practical examples
- Test agents in real-world scenarios

## 📝 License

[Add your license information here]

## 🔗 Resources

- [Code Studio Documentation](https://help.syncfusion.com/code-studio)
- [Custom Agents Guide](https://help.syncfusion.com/code-studio/reference/configure-properties/custom-agents)
- [Syncfusion Community Forum](https://www.syncfusion.com/forums)
- [Code Studio Download](https://www.syncfusion.com/code-studio)

---

Built with ❤️ for the Code Studio community

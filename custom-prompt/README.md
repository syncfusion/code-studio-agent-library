## 📖 What are Custom Prompts?

Custom prompts are pre-built templates and workflows that consist of:
- **Specific task instructions** that guide agents through structured workflows
- **Step-by-step processes** that ensure consistent, high-quality outputs
- **Chained workflows** that orchestrate multiple tasks in sequence

This custom prompt library provides ready-to-use prompts so you can immediately benefit from proven workflows without creating them from scratch.

## ✨ Why Use Custom Prompts?

### Pre-configured Workflows
- **No setup required** - Each prompt comes with detailed steps and best practices
- **Battle-tested processes** - Prompts are designed based on real-world development scenarios
- **Consistent results** - Get the same quality output every time you run a prompt

### Time Savings
- **Skip process creation** - No need to write workflow instructions from scratch
- **Instant productivity** - Start using structured prompts immediately
- **Team standardization** - Everyone follows the same proven processes

### Customizable Foundation
- **Modify to fit your needs** - All prompts can be customized for your workflow
- **Learn by example** - See how professional workflows are structured
- **Extend functionality** - Chain prompts together for complex workflows

## 📥 Installation

### Option 1: Workspace Installation (Team Sharing)

For sharing prompts with your team via source control:

1. **Clone this repository:**
   ```bash
   git clone https://github.com/syncfusion/code-studio-library.git
   ```

2. **Copy prompts to your project's `.codestudio/prompts/` folder:**
   ```bash
   # Create the directory if it doesn't exist
   mkdir -p YOUR-PROJECT/.codestudio/prompts/
   
   # Copy all prompt files
   cp code-studio-library/custom-prompt/*.prompt.md YOUR-PROJECT/.codestudio/prompts/
   ```

3. **Prompts are automatically detected** by Code Studio - no restart needed!

### Option 2: User Profile Installation (Personal Use)

For using prompts across all your projects:

1. **Download this repository**

2. **Copy prompts to your user profile:**
   - **Windows**: `%USERPROFILE%\.codestudio\prompts\`
   - **Mac/Linux**: `~/.codestudio/prompts/`

3. **Code Studio automatically detects** the new prompts

## 🚀 Quick Start

### Using Custom Prompts

1. **Open Chat View** in Code Studio
2. Type **/** in chat
3. **Select your desired prompt** from the list
4. **Follow the structured workflow** - the agent executes the prompt steps

📚 Learn more: [Code Studio Custom Prompts Documentation](https://help.syncfusion.com/code-studio/reference/configure-properties/custom-prompt)

## 📋 Prompt Organization

Prompts are organized by use case and domain:

### 📦 Sample Workflows (`sample-dashboard/`)

Pre-built workflows for common development tasks:

- **[lint-spec.prompt.md](sample-dashboard/lint-spec.prompt.md)** - Validate and review specifications before development
- **[compile.prompt.md](sample-dashboard/compile.prompt.md)** - Generate code from specifications with best practices
- **[test.prompt.md](sample-dashboard/test.prompt.md)** - Create comprehensive test coverage
- **[review.prompt.md](sample-dashboard/review.prompt.md)** - Perform code quality reviews
- **[security.prompt.md](sample-dashboard/security.prompt.md)** - Audit code for vulnerabilities
- **[full-workflow.prompt.md](sample-dashboard/full-workflow.prompt.md)** - Execute complete end-to-end development pipeline
- **[dashboard.prompt.md](sample-dashboard/dashboard.prompt.md)** - Reference specification template

## 💡 Best Practices

1. **Start with specification** - Clear requirements lead to better outcomes
2. **Chain prompts logically** - Use workflows that build on each other
3. **Review outputs carefully** - Validate prompt results before proceeding
4. **Customize for your needs** - Adapt prompts to your project's specific requirements
5. **Iterate and improve** - Refine prompts based on your team's feedback

## 📝 Customization

Each prompt can be customized for your specific needs:

1. **Copy the prompt** to your workspace
2. **Modify the task description** section
3. **Adjust the steps** to match your workflow
4. **Update success criteria** for your project
5. **Save and use** your custom version

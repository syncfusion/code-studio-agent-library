## 📖 What are Skills?

Skills let you extend Code Studio with reusable, task-focused capabilities packaged as a structured folder. Each Skill bundles a `SKILL.md` file alongside supporting assets—scripts, templates, and examples—that Code Studio loads when needed.

Skills encapsulate complete workflows: security scanning, code review checklists, testing routines, or domain-specific automation. Skills are portable and work across any agent.

## ✨ Why Use Skills?

### Pre-configured Workflows
- **No setup required** - Each Skill comes with detailed instructions and best practices
- **Battle-tested processes** - Designed based on real-world development scenarios
- **Consistent results** - Get the same quality output every time

### Time Savings
- **Skip process creation** - No need to write workflow instructions from scratch
- **Instant productivity** - Start using structured Skills immediately
- **Team standardization** - Everyone follows the same proven processes

### Customizable Foundation
- **Modify to fit your needs** - All Skills can be customized for your workflow
- **Learn by example** - See how professional workflows are structured
- **Extend functionality** - Chain Skills together for complex workflows

## 📥 Installation

### Option 1: Project Installation (Team Sharing)

For sharing Skills with your team via source control:

1. **Clone this repository:**
   ```bash
   git clone https://github.com/syncfusion/code-studio-library.git
   ```

2. **Copy all Skills to your project's `.codestudio/skills/` folder:**
   ```bash
   # From your project root directory:
   # Create the directory if it does nt exist

   mkdir -p .codestudio/skills/
  
   
   # Copy all Skills from code-studio-library:
   cp -r <path-to-code-studio-library>/skills/* .codestudio/skills/
   
   
  
   ```

3. **Skills are automatically detected** by Code Studio - no restart needed!

### Option 2: User Profile Installation (Personal Use)

For using Skills across all your projects:

1. **Download this repository**

2. **Copy Skills to your user profile:**
   - **Windows**: `%USERPROFILE%\.codestudio\skills\`
   - **Mac/Linux**: `~/.codestudio/skills/`

3. **Code Studio automatically detects** the new Skills

## 🚀 Quick Start

### Using Skills

1. **Open Chat View** in Code Studio
2. Type **/** in chat
3. **Select your desired Skill** from the list
4. **Follow the structured workflow** - the agent executes the Skill steps

📚 Learn more: [Code Studio Skills Documentation](https://help.syncfusion.com/code-studio/reference/configure-properties/skills)

## 📋 Skill Organization

Skills are organized by domain and capability:

### 🔒 Security Review (`security-review/`)

Pre-built Skill for comprehensive security analysis:

- **[SKILL.md](security-review/skills/securityreview/SKILL.md)** - Security review instructions and rules
- **Supporting prompts** - Copy these to `.codestudio/prompts/`:
  - `prompts/scan-file.prompt.md` - Single file vulnerability analysis
  - `prompts/scan-diff.prompt.md` - Code diff scanning
  - `prompts/aggregate-findings.prompt.md` - Findings aggregation

**Key capabilities:**
- Scan code diffs for vulnerabilities
- Analyze individual files for security issues
- Generate security reports with false-positive filtering

**Setup:**

Run these commands from your project root directory:

```bash
# Create the directory if it doesn't exist

mkdir -p .codestudio/skills/
mkdir -p .codestudio/prompts/

# Copy Skill (replace <path-to-code-studio-library> with actual path)
cp -r <path-to-code-studio-library>/skills/security-review/skills/securityreview .codestudio/skills/

# Copy supporting prompts
cp <path-to-code-studio-library>/skills/security-review/prompts/*.prompt.md .codestudio/prompts/
```

**Example:**
```bash
# If code-studio-library is at D:\security-skill\code-studio-library
cp -r D:\security-skill\code-studio-library\skills\security-review\skills\securityreview .codestudio\skills\   
cp D:\security-skill\code-studio-library\skills\security-review\prompts\*.prompt.md .codestudio\prompts\
```

## 💡 Best Practices

1. **Start with specification** - Clear requirements lead to better outcomes
2. **Chain Skills logically** - Use workflows that build on each other
3. **Review outputs carefully** - Validate Skill results before proceeding
4. **Customize for your needs** - Adapt Skills to your project's specific requirements
5. **Iterate and improve** - Refine Skills based on your team's feedback

## 📝 Customization

Each Skill can be customized for your specific needs:

1. **Copy the Skill** to your workspace
2. **Modify the SKILL.md** file and supporting assets
3. **Adjust instructions** to match your workflow
4. **Update procedures** for your project
5. **Save and use** your custom version

<pre>
 ██████╗ █████╗ ██████╗ ██╗   ██╗███████╗██████╗  █████╗  ██████╗ ███████╗███╗   ██╗████████╗███████╗
██╔════╝██╔══██╗██╔══██╗██║   ██║██╔════╝██╔══██╗██╔══██╗██╔════╝ ██╔════╝████╗  ██║╚══██╔══╝██╔════╝
██║     ███████║██████╔╝██║   ██║█████╗  ██████╔╝███████║██║  ███╗█████╗  ██╔██╗ ██║   ██║   ███████╗
██║     ██╔══██║██╔══██╗╗██╗ ██╔╝██╔══╝  ██╔══██╗██╔══██║██║   ██║██╔══╝  ██║╚██╗██║   ██║   ╚════██║
╚██████╗██║  ██║██║  ██║ ╚████╔╝ ███████╗██║  ██║██║  ██║╚██████╔╝███████╗██║ ╚████║   ██║   ███████║
 ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝  ╚═══╝  ╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝╚═╝  ╚═══╝   ╚═╝   ╚══════╝

                    🤖 Compound Engineering Framework for AI Agents 🤖
</pre>

## 🌟 Overview 

This framework transforms AI-coder development through **session-based workflows** with **intelligent context priming** and **continuous self-improvement**. Every development session automatically loads optimal model context and builds institutional knowledge that makes each subsequent session more effective.

## 🧠 Core Philosophy 

#### 🤖 Intelligent Context Priming
* Automatically provide AI models with precisely the right information from your codebase and documentation, eliminating manual context management.

#### 🎯 Learning-Driven Sessions
* Structure all development work into trackable sessions with clear goals and automatic progress documentation. Each session runs in its own Git branch - the system handles this automatically.

#### 📈 Continuous Self-Improvement
* Capture problems, solutions, and insights from every session to build a growing knowledge base that prevents repeated mistakes and accelerates future development.

## ✨ Key Features 

- **Smart Context Loading**: Automatically primes AI model context with relevant files and lessons based on session goals
- **Zero Manual Setup**: No need to explain project structure or copy-paste code snippets
- **Session Isolation**: Each session runs in its own Git branch automatically
- **Learning Capture**: Every challenge and solution becomes institutional knowledge
- **Documentation Evolution**: Project understanding improves automatically over time

## 🚀 Quick Start 

> *Note: The framework works out-of-the-box with Claude Code but can be easily modified to work with other AI coding agents.*

#### 0. Installation
```bash
git clone https://github.com/carveragents/compound-engg-ai.git
cp -R carveragents-compound-engg-ai/commands ~/.claude/
```

#### 1. Start with Intelligent Context Priming
```bash
 /session:start fix memory leak in data processing
```
*System analyzes your goal, loads relevant code and docs, surfaces applicable lessons, and creates an isolated branch `bugfix-memory-leak-data-processing` for development*

#### 2. Develop
*Develop as normal. Let AI generate code. It may encounter problems, solve as normal using human + AI mix.*

#### 3. Update and Capture Progress
```bash
/session:update
```
*Updates session progress, summarizes and captures development flow*

#### 4. End with Knowledge Capture
```bash
/session:end
```
*Updates lessons learned and prepares insights for future sessions*

## 🎁 Bonus: Git Utilities 

For convenience, the system includes intelligent Git commands:

- **`/git:commit`** - Analyzes session context and code changes to generate conventional commit messages with emojis. Automatically splits large changes into logical atomic commits.
- **`/git:merge-cleanup`** - Merges current session branch to main, pushes to origin, and cleans up the working branch.

These integrate seamlessly with the session workflow but are entirely optional - the core value is in session management and continuous learning.

## 🔧 Extending beyond Claude Code 

All logic lives in the **command contracts** (`commands/.../*.md`). To adapt:

- Map `allowed tools` and filesystem paths to your agent/runtime.
- Keep the **session file format** stable for portability.
- If your agent can run shell steps, branch creation and `git status` work as-is.

## 📋 Best Practices 

- **Specific Goals**: Start sessions with clear, measurable objectives
- **Regular Updates**: Document progress and discoveries as they happen
- **Honest Recording**: Capture what didn't work as well as what did
- **Review Lessons**: Let the system surface relevant insights from previous work

## 🤝 Contributing 

To improve this system, submit pull requests for better command instructions, new commands, session file formatting, and utilities for session analysis.

## 📚 References & Inspiration 

This framework was inspired by and builds upon ideas from:

- **[claude-sessions](https://github.com/iannuttall/claude-sessions)** - Session-based AI development tracking
- **[My AI Had Already Fixed the Code Before I Saw It](https://every.to/source-code/my-ai-had-already-fixed-the-code-before-i-saw-it)** - Compound Engineering article by [Every.to](https://every.to) on AI-assisted development workflows and the future of coding collaboration
- **[Building AI Agents that Actually Work](https://www.youtube.com/watch?v=Kf5-HWJPTIE)** - Principles for creating effective AI development workflows
- **[tevm/commit](https://github.com/evmts/tevm-monorepo/blob/main/.claude/commands/commit.md)** - Claude code git commit slash command

## ⚖️ License 

MIT License - see [LICENSE](LICENSE) file for details.


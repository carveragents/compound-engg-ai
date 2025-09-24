# CarverAgents Compound Engineering AI Framework

## Overview

This framework transforms AI-coder development through **session-based workflows** with **intelligent context priming** and **continuous self-improvement**. Every development session automatically loads optimal model context and builds institutional knowledge that makes each subsequent session more effective.

## Core Philosophy

### 🤖 Intelligent Context Priming
Automatically load AI models with precisely the right information from your codebase and documentation, eliminating manual context management.

### 🎯 Learning-Driven Sessions
Structure all development work into trackable sessions with clear goals and automatic progress documentation. Each session runs in its own Git branch - the system handles this automatically.

### 📈 Continuous Self-Improvement
Capture problems, solutions, and insights from every session to build a growing knowledge base that prevents repeated mistakes and accelerates future development.

## Key Features

- **Smart Context Loading**: Automatically primes AI model context with relevant files and lessons based on session goals
- **Zero Manual Setup**: No need to explain project structure or copy-paste code snippets
- **Session Isolation**: Each session runs in its own Git branch automatically
- **Learning Capture**: Every challenge and solution becomes institutional knowledge
- **Documentation Evolution**: Project understanding improves automatically over time

## Quick Start

#### 0. Setup
Clone the repo and copy the contents of `commands/` to your `.claude/` directory.

#### 1. Start with Intelligent Context Priming
```bash
 /session:start fix memory leak in data processing
```
*System analyzes your goal, loads relevant code and docs, surfaces applicable lessons, and creates an isolated branch `bugfix-memory-leak-data-processing` for development*

#### 2. Develop with Continuous Learning
*Develop as normal. Let AI generate code. It may encounter problems, solve as normal using human + AI mix.*

#### 3. Complete with Knowledge Synthesis
```bash
/session:end
```
*Updates lessons learned and prepares insights for future sessions*

## Session Lifecycle

```
Session Start → Context Priming → Problem Encounter → Solution Discovery (human-in-the-loop) → Knowledge Capture → Lesson Integration
```

### 1. **Model Context Priming**
- Analyzes session goal to identify relevant domains
- Discovers pertinent codebase files via session goal analysis
- Loads relevant documentation and historical lessons
- Creates isolated Git branch for the session
- Primes model with optimal context

### 2. **Continuous Progress Tracking**
- Documents code changes, decisions, and challenges
- Captures insights and lessons
- Tracks Git status and task completion

### 3. **Knowledge Synthesis & Storage**
- Generates comprehensive session summary
- Updates project/org memory with new insights and solutions
- Enhances project documentation with improved understanding
- Prepares knowledge for future session initialization

## Key Benefits

### 🚀 **Zero Manual Context Management**
No more explaining project structure or copying code snippets. Session start handles everything automatically.

### 🎯 **Optimal Model Performance**
AI models start with precisely the right context - relevant code, applicable lessons, pertinent documentation.

### ⚡ **Instant Productivity**
Skip setup and dive into productive development. The model understands your codebase and remembers solutions.

### 📚 **Compound Learning**
Each session builds upon previous knowledge:
- **Session 1**: Learns basic patterns
- **Session 10**: Applies previous lessons, discovers advanced techniques
- **Session 50**: Functions with deep institutional knowledge, avoids known pitfalls

## Best Practices

- **Specific Goals**: Start sessions with clear, measurable objectives
- **Regular Updates**: Document progress and discoveries as they happen
- **Honest Recording**: Capture what didn't work as well as what did
- **Review Lessons**: Let the system surface relevant insights from previous work

## Contributing

To improve this system, submit pull requests for better command instructions, new commands, session file formatting, and utilities for session analysis.

## License

MIT License - see [LICENSE](LICENSE) file for details.

---

*Every session is a learning opportunity. Every lesson learned accelerates future development.*

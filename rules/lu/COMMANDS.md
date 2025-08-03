# COMMANDS.md - LucasClaude Command Execution Framework

Command execution framework for Claude Code LucasCode integration.

## Command System Architecture

### Core Command Structure
```yaml
---
command: "/{command-name}"
category: "Primary classification"
purpose: "Operational objective"
---
```

### Command Processing Pipeline
1. **Input Parsing**: `$ARGUMENTS` with `@<path>`, `!<command>`, `--<flags>`
2. **Context Resolution**: Auto-persona activation and MCP server selection

### Integration Layers
- **Claude Code**: Native slash command compatibility
- **MCP Servers**: Context7, exa-search integration

## Development Commands

**`/ghprc $ARGUMENTS`**
```yaml
---
command: "/ghprc"
category: "Git integration"
purpose: "Commit all changed files, or selected paths or files, and push them to the remote repository."
---
```
- **Tool Orchestration**: [Read, Grep, Glob, Bash, TodoWrite, Edit, MultiEdit]
- **Arguments**: `[target]`, `@<path>`, `!<command>`, `--<flags>`

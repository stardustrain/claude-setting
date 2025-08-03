---
allowed-tools: [Bash, Read, Glob, TodoWrite, Edit]
description: "Build, compile, and package projects with error handling and optimization"
---

# /lu:ghprc - Auto commit and push

## command execution guideline
@rules/lu/COMMANDS.md

## Purpose
Execute comprehensive code analysis across quality, security, performance, and architecture domains.

## Usage
```
/lu:ghprc [target]
```

## Arguments
- `target` - Files, directories. If not specified, all changes will be committed.

## Execution
1. Analyze the current Git status and repository context
2. Check the “target” argument
  2-1. If not transmitted, set all changed files as targets.
  2-2. If transmitted, set only the transmitted paths and files as targets.
3. Analyze major changes between the main branch and the current branch.
  3-1. When analyzing changes, include only the “target” confirmed in step 2 as the analysis target.
4. Git add “target”
5. Write a commit message and commit
  5-1. When writing a commit message, first check the project's commit message conventions. Commit message conventions are only checked in files under ./cursor/rules or in the CLAUDE.md file at the project root.
  5-2. If a commit message convention is found, strictly adhere to it when writing the message
  5-3. If there is no commit message convention, follow the @rules/lu/commitMessgeConvention.md.
6. Provide clear feedback and next steps

## Claude Code Integration
- Uses Bash for Git command execution
- Leverages Read for repository analysis
- Applies TodoWrite for operation tracking
- Maintains Git best practices and conventions
- If necessary, use the GitHub CLI command (gh).

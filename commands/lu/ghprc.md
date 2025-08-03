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
/lu:ghprc [target] [--close-linear]
```

## Arguments
- `target` - Files, directories. If not specified, all changes will be committed.
- `--close-linear` - The linear issue number associated with this branch. If the branch name starts with "feature/", "refactor/", "chore/", or "fix/", the value following “/” is considered the issue number. default: false

## Execution
1. Analyze the current Git status and repository context
  1-1. If there are no changes, proceed to step 6.
2. Check the “target” argument
  2-1. If not transmitted, set all changed files as targets.
  2-2. If transmitted, set only the transmitted paths and files as targets.
3. Analyze major changes between the main branch and the current branch.
4. Git add “target”
5. Write a commit message and commit
  5-1. When writing a commit message, first check the project's commit message conventions. Commit message conventions are only checked in files under ./cursor/rules or in the CLAUDE.md file at the project root.
  5-2. If a commit message convention is found, strictly adhere to it when writing the message
  5-3. If there is no commit message convention, follow the @rules/lu/commitMessgeConvention.md.
6. Push to remote repository.
  6-1. Pull request titles must follow these rules.
    - The title format follow the `<type>[optional scope]: <description>`.
    - The length of the title must not exceed 50 characters.
    - Analyze the commit messages in the current branch and select the title that best represents the changes in this branch.
  6-2. Pull request body must follow these rules.
    - First, check if the .github/PULL_REQUEST_TEMPLATE.md file exists in the project.
    - If it exists, write the body in the following format. `close [issue number] \n [content of PULL_REQUEST_TEMPLATE.md]`
    - If it doesn't exist, write the body in the following format. `close [issue number]`
    - If issue number and PULL_REQUEST_TEMPLATE.md do not exist, only the title is included.
7. Provide clear feedback and next steps

## Claude Code Integration
- Uses Bash for Git command execution
- Leverages Read for repository analysis
- Applies TodoWrite for operation tracking
- Maintains Git best practices and conventions
- If necessary, use the GitHub CLI command (gh).

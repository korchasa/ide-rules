# AI Roles Collection

A collection of Cursor rules, designed to standardize work across various software development contexts.

!!!WARNING!!!
DO NOT USE THIS FILES AS IS. YOU MUST MODIFY THEM TO FIT YOUR PROJECT AND YOUR STYLE OF WORK.

## Framework

The main idea is to work together with the agent, keeping control over the process and acting as a guardrail between stages, explicitly switching them using `/task-*` command syntax.

Key Principles:
- instruction unification (in progress): setting up a new project should boil down to selecting instructions and editing `main.mdc`;
- splitting instructions into types:
  - Stages (Manual Apply): stages of work over the project (`task-*`);
  - Rules (Always Apply): working rules: tdd, code style, etc (`rules-*`);
  - Documentation (Always Apply): documentation guidelines (`docs-*`);
  - Project Maintenance (Always Apply): list of console commands for project maintenance (`run-commands.mdc`);
  - Howto (Apply Intelligent): automatic instructions for situational tasks that may arise for the model during work (`howto-*`);
- documentation as the agent's long-term memory:
  - all project documentation must reside in the repository;
  - two documentation schema options: cline-bank (7 files) and simplified (Software Requirements Specification + Software Design Specification, 4 files);
  - documentation in a compact style, and there is a dedicated task for its compacting;
- saving the current task into a file (`./documents/whiteboard.md`) for transfer between chats and stages;
- maximum automatic regression control: the entire project verification reduces to a single command (`./run check`), so the agent cannot perform only part of the checks; the same command is used in CI;
- a single list for invoking all project commands (`./run`).

## Available Components

### Task Commands
Task commands provide guided workflows for specific development activities:

- `task-commit.md` - Commit workflow following Conventional Commits (strict)
- `task-execute.md` - Execute and implement planned tasks
- `task-fix.md` - Fix errors, warnings, and linting problems
- `task-github-issue-create.md` - Create GitHub issues using GODS framework
- `task-investigate.md` - Investigate and analyze codebase issues
- `task-plan.md` - Plan and break down complex development tasks
- `task-review.md` - Review code changes and implementation
- `task-update-docs.md` - Update project documentation

### Documentation Rules
Documentation schemas and guidelines:

- `docs-schema-cline-bank.mdc` - Cline-bank documentation schema (7 files)
- `docs-schema-rds-sds.mdc` - RDS-SDS documentation schema (4 files)

### How-to Guides
Practical guides for common development scenarios:

- `howto-commit-changes.mdc` - How to commit changes following repository rules
- `howto-compact-docs.mdc` - How to write documentation in compact style
- `howto-debug-by-playwright.mdc` - Manually test or debug using Playwright MCP tools
- `howto-fix-tests.mdc` - How to fix failing tests
- `howto-manage-github-tickets-by-mcp.mdc` - How to manage GitHub tickets using MCP
- `howto-working-with-git.mdc` - How to work with git in this repository
- `howto-write-in-informational-style.mdc` - How to write in informational style

### Development Rules
Rules that govern development practices and code quality:

- `rules-autonomous.mdc` - Autonomous mode development principles
- `rules-code-style-fullstack.mdc` - Fullstack code style guidelines
- `rules-code-style-swift.mdc` - Swift code style rules
- `rules-code-style-ts-strict.mdc` - TypeScript strict mode rules
- `rules-code-style-typescript-deno.mdc` - TypeScript Deno-specific rules
- `rules-gods.mdc` - GODS framework for issue creation and management
- `rules-tdd.mdc` - Test-Driven Development rules and flow
- `rules-zen.mdc` - Zen principles for clean development

### Project Maintenance
- `main-example.mdc` - Example main configuration file
- `run-commands.mdc` - CLI commands description (`./run.ts`)

## License

The project is distributed under the MIT license.

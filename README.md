# AI Roles Collection

A collection of Cursor rules, designed to standardize work across various software development contexts.

!!!WARNING!!!
DO NOT USE THIS FILES AS IS. YOU MUST MODIFY THEM TO FIT YOUR PROJECT AND YOUR STYLE OF WORK.

## Framework

The main idea is to work together with the agent, keeping control over the process and acting as a guardrail between stages, explicitly switching them using `@task-*`.

Key Principles:
- instruction unification (in progress): setting up a new project should boil down to selecting instructions and editing `main.mdc`;
- splitting instructions into types:
  + `task-*` [Apply Manual] — stages of task execution;
  + `rules-*` [Always Apply] — working rules: tdd, code style, etc;
  + `docs-*` [Always Apply] — documentation guidelines;
  + `run-commands.mdc` [Always Apply] — description of console commands for project maintenance;
  + `howto-*` [Apply Intelligent] — automatic instructions for situational tasks that may arise for the model during work;
- documentation as the agent's long-term memory:
  + all project documentation must reside in the repository;
  + two documentation schema options: cline-bank (7 files) and simplified (Software Requirements Specification + Software Design Specification, 4 files);
  + documentation in a compact style, and there is a dedicated task for its compacting;
- saving the current task into a file (`./documents/whiteboard.md`) for transfer between chats and stages;
- maximum automatic regression control: the entire project verification reduces to a single command (`./run check`), so the agent cannot perform only part of the checks; the same command is used in CI;
- a single list for invoking all project commands (`./run`).

## License

The project is distributed under the MIT license.

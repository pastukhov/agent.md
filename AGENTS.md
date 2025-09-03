# AGENTS.md Guidelines

This repository demonstrates how to write `AGENTS.md` files for any project.
Use this file as a template or reference when creating instructions for an
automated contributor.

## Purpose of `AGENTS.md`

`AGENTS.md` files give high‑level guidance to automated agents that edit or
maintain your code. They explain code style, required checks, and other
conventions the agent should follow.

## File placement and scope

- Place an `AGENTS.md` at the repository root for global instructions.
- Additional `AGENTS.md` files inside subdirectories override or extend
  instructions for their subtree.
- When multiple files apply, instructions in deeper directories take
  precedence.

## Writing effective instructions

1. **Be concise and explicit.**
   - State exactly which commands to run for formatting, linting, and tests.
   - Mention any required environment variables or setup steps.
2. **Describe style and structure.**
   - Note naming conventions, file locations, and preferred libraries.
   - Include examples when helpful.
3. **Specify testing requirements.**
   - List the commands for unit tests, integration tests, and linters.
   - Explain when certain tests can be skipped or are expected to fail.
4. **Detail version‑control expectations.**
   - Explain commit message format and branching strategy.
   - Note whether changes should be grouped by feature or file.
5. **Link to external resources.**
   - Reference style guides, documentation, or READMEs for deeper context.

## Example skeleton

```md
# AGENTS.md

- Run `npm test` and `npm run lint` before committing.
- Follow the repo's `CONTRIBUTING.md` for commit message format.
- Place source files in `src/` and tests in `tests/`.
- Update `CHANGELOG.md` for user‑facing changes.
```

Customize these sections to reflect your project's needs so that automated
agents can contribute effectively.

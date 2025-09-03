# AGENTS.md Guidelines

This repository demonstrates how to write `AGENTS.md` files for any project. Use this file as a template or reference when creating instructions for an automated contributor.

## Purpose of `AGENTS.md`

`AGENTS.md` files give high‑level guidance to automated agents that edit or maintain your code. They explain code style, required checks, and other conventions the agent should follow.

## File placement and scope

- Place an `AGENTS.md` at the repository root for global instructions.
- Additional `AGENTS.md` files inside subdirectories override or extend instructions for their subtree.
- When multiple files apply, instructions in deeper directories take precedence.

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

## Recommended sections

Consider adding the following sections to tailor the file to your project:

- **Dev environment tips**
  - Provide shortcuts for navigating or bootstrapping packages, e.g. `pnpm dlx turbo run where <project_name>` or `pnpm create vite@latest <project_name> -- --template react-ts`.
  - Mention how to install dependencies, such as `pnpm install --filter <project_name>`.
  - Highlight checks like verifying the `name` field in each `package.json`.

- **Testing instructions**
  - Point to the CI plan (e.g. files in `.github/workflows`).
  - Show how to run the full suite (`pnpm turbo run test --filter <project_name>`), focused tests (`pnpm vitest run -t "<test name>"`), and linters (`pnpm lint --filter <project_name>`).
  - Encourage adding or updating tests and keeping the suite green before committing.

- **PR instructions**
  - Specify title formats like `[<project_name>] <Title>`.
  - Require running `pnpm lint` and `pnpm test` before each commit.
  - Call out any additional review or changelog requirements.

## Example skeleton

```md
# AGENTS.md

## Dev environment tips
- Use `pnpm dlx turbo run where <project_name>` to jump to a package.
- Run `pnpm install --filter <project_name>` to add the package to the workspace.

## Testing instructions
- Run `pnpm lint --filter <project_name>` and `pnpm test`.
- Focus a step with `pnpm vitest run -t "<test name>"`.
- Fix any type or test failures until the suite passes.

## PR instructions
- Title format: [<project_name>] <Title>
- Always run `pnpm lint` and `pnpm test` before committing.
- Add or update tests for your changes.
```

Customize these sections to reflect your project's needs so that automated agents can contribute effectively.

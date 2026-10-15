---
layout: post
title: Simple sandbox setup for AI Agent and team collaboration
date: 2026-07-12
---

Agile teams often face challenges in maintaining smooth collaboration across different roles and repositories. This setup aims to address those challenges by providing a shared workspace that supports AI agents for enhanced productivity.

Idea here is to create simple tooling composition for anyone involved in the development process, enabling them to collaborate effectively without the need for complex setups or additional platforms.

Agile team that consists of developers, product managers, QA, and DevOps can benefit from this setup by having a unified workspace that provides context-aware assistance and streamlines collaboration across different roles. No one is forced to use any specific tool, allowing team members to work with their preferred tools while still maintaining a shared context.

## Tooling & context

| Context | Tool |
| --- | --- |
| Source code | `git clone` | - source is check out locally
| QA tests | `git clone` | - tests are checked out locally
| Infrastructure as code | `git clone` | - IaC is checked out locally
| Documentation | Azure DevOps Wiki (`git clone`)  | - documentation is checked out locally from wikis
| Backlog | Azure DevOps Boards (`az cli`) / GitHub Projects (`gh cli`) | - simple cli tooling (to use with mcp setup)
| Harness | `copilot` in vs code |
| IDE | VS Code (`.code-workspace`) |  that collects all related repositories and provides a unified workspace for development and collaboration. This way llm can navigate all related code, tests, documentation, and infrastructure files seamlessly.
| Diagrams | `Mermaid.js` in Markdown files | to enable shared view of architectural diagrams and facilitate collaboration on system design. (even with LLM contribution)

## Composition of the workspace
All repositories should be cloned locally and opened in VSCode workspace. Opening VS Code in that setup allows access to all perspectives. Copilot needs only some small guide to understand repos or folders structure. It can then provide context-aware suggestions and code completions across the entire workspace.

## How to use the workspace
Anyone can use the tooling he wants, this is not enforced by this setup, but might be useful to use VS Code.
  - PM can use the setup to validate his requirements against the base code, and to check if the backlog is aligned with the codebase.
  - QA can use the setup to validate test cases against the codebase
  - DevOps can use the setup to validate IaC against the codebase and to check if the backlog is aligned with the codebase.
  - Dev can work on the codebase and validate backlog items against the documentation.

## Tools
- az cli or gh cli - allows to manage backlog and boards
- mermaid common way to draw any diagram in markdown files, and **copilot** can read and write them.



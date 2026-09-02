---
layout: post
title: Simple sandbox setup for AI Agent and team collaboration
date: 2026-07-12
---

A simple workspace setup for developers, product managers, QA, and DevOps to collaborate without adding another platform to maintain. Idea goes from and attempt to ensure smooth collaboration across roles and repositories, while keeping the team aligned on the same shared context with support of AI agents.

## Tooling & context

| Context | Tool |
| --- | --- |
| Source code | `git clone` |
| QA tests | `git clone` |
| Infrastructure as code | `git clone` |
| Documentation | Azure DevOps Wiki (`git clone`)  |
| Backlog | Azure DevOps Boards (`az cli`) / GitHub Projects (`gh cli`) |
| Harness | `copilot` in vs code |
| IDE | VS Code (`.code-workspace`) | 
| Diagrams | `Mermaid.js` in Markdown files |

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



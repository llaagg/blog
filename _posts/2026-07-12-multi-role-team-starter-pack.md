---
layout: post
title: The Multi-Role Team Starter Pack
date: 2026-07-12
---

A simple workspace setup for developers, product managers, QA, and DevOps to collaborate without adding another platform to maintain.

## Start with one shared foundation

When collaboration spans repositories, roles, and environments, complexity arrives quickly. A shared VS Code multi-root workspace gives everyone the same map: documentation, application code, and infrastructure in one window.

```json
{
  "folders": [
    { "name": "Documentation", "path": "./docs" },
    { "name": "Backend Service", "path": "./backend" },
    { "name": "Infrastructure", "path": "./infrastructure" }
  ]
}
```

## Keep the intelligence local

Good defaults matter. Exclude generated folders such as `node_modules`, `build`, and `dist` from indexing so the useful signal stays easy to find.

> The best team tool is often the one that makes the existing work easier to see.

## Let documentation stay alive

Architecture should not be a museum exhibit. Keep diagrams in plain-text Markdown files, use Mermaid when a visual is helpful, and make updates part of the same workflow as code changes.

## Make every role a first-class citizen

Product managers can keep requirements and acceptance criteria close to the code. Developers get the full context of adjacent services. QA can run shared tasks. DevOps can shape infrastructure with a clear view of the APIs it supports.

That is the whole idea: fewer handoffs hidden in private tools, more context available in the open, and a workspace that helps the team stay aligned.

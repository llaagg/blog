# The Multi-Role Team Starter Pack: A Simple Workspace Setup for Dev, PM, QA, and DevOps

When setting up collaboration for modern, multi-repository engineering teams, it is easy to get bogged down in complex architectures. This guide lays out a **minimal, out-of-the-box starter pack** that brings together Developers, Product Managers (PMs), Delivery Leads, Quality Assurance (QA), and DevOps engineers. 

To keep things as accessible as possible, **this setup requires no RAG (Retrieval-Augmented Generation), no custom databases, and no advanced autonomous agents.** It relies entirely on native local tools and lightweight repository files.

---

## The Core Toolchain & Setup Order

To build this unified workspace, configure your environment in the following sequence:

### 1. VS Code Multi-Root Workspace (The Foundation)
Instead of opening multiple editor windows or relying on complex service catalogs, group all your related projects (frontend, backend, infrastructure, and documentation) into a single window using a **VS Code Multi-root Workspace** [6, 7]. 
Create a unified `<project-name>.code-workspace` JSON file containing absolute or relative paths to each repository [6, 8]:
```json
{
  "folders": [
    { "name": "Documentation", "path": "./docs" },
    { "name": "Backend Service", "path": "./backend" },
    { "name": "Frontend Application", "path": "./frontend" },
    { "name": "Infrastructure (IaC)", "path": "./infrastructure" }
  ]
}
```
*Relative paths are highly recommended so team members can share the workspace file seamlessly [6].*

### 2. Exclusions & Local Indexing (The Intelligence)
By default, GitHub Copilot automatically builds an advanced local index of your project if it detects fewer than 750 files [7]. By using exclusions, you can easily index up to 2,500 files locally while keeping search and indexing extremely fast [7].
To prevent noisy build directories (like `node_modules` or compiled binaries) from polluting your index, define workspace-specific exclusions in your `.code-workspace` file [7, 8]:
```json
{
  "settings": {
    "files.exclude": {
      "**/node_modules": true,
      "**/build": true,
      "**/dist": true
    },
    "search.exclude": {
      "**/node_modules": true,
      "**/build": true,
      "**/dist": true
    }
  }
}
```
Once configured, run the **Build local workspace index** command in the VS Code Command Palette to establish a clean semantic map [7].

### 3. Living Architecture (The Blueprint)
Keep your technical diagrams in plain-text Markdown files (e.g., `docs/architecture.md`) using **Mermaid.js**. Since Copilot natively reads and writes Markdown, the AI can read these diagrams as active context [7] and update them automatically whenever code structures are modified.

### 4. CLI Context Automation (The Environment)
*To avoid global state mutations when switching environments, configure directory-scoped aliases for either `az cli` (using a fast subscription index-switcher script in your shell profile [5]) or `gh cli` (using directory-based conditional `includeIf` git configs to switch accounts [1]).*

---

## How Roles Collaborate (No Complex Agents Required)

This workspace acts as a shared arena where different team roles collaborate using natural language and basic automation.

*   **Product Managers & Delivery Leads:** Define requirements, feature definitions, and acceptance criteria in plain Markdown files in the `docs/` directory [6, 7]. PMs can discuss design ideas directly with Copilot Chat, which automatically references these requirements alongside the active codebase [7, 8].
*   **Developers:** Open the single workspace window and use inline chat or Copilot Chat to implement features [8]. Because Copilot indexes all folders, it understands dependencies between the frontend, backend, and documentation folders simultaneously [6, 7].
*   **Quality Assurance (QA):** Write and execute test suites alongside the code [8]. By defining common workspace tasks in the `.code-workspace` file, QA engineers can trigger local test runners for any component with a single keystroke [6]:
    ```json
    "tasks": {
      "version": "2.0.0",
      "tasks": [
        {
          "label": "Run QA Integration Tests",
          "type": "shell",
          "command": "npm test",
          "options": { "cwd": "${workspaceFolder:Frontend Application}" }
        }
      ]
    }
    ```
*   **DevOps Engineers:** Keep Infrastructure-as-Code (IaC) templates (Terraform, Dockerfiles, or Helm charts) inside the `infrastructure/` workspace folder [7]. DevOps can utilize Copilot to generate configuration files that are automatically tailored to the API structures defined in the backend codebase [8].

---

## Conclusion
By combining VS Code Multi-root Workspaces [6], highly targeted local indexing [7], and Markdown-based Mermaid documentation, you create an incredibly low-friction ecosystem. There is no infrastructure to maintain, no databases to host, and no complex API tokens to manage—just simple, local collaboration that keeps the entire team aligned.

---
id: 'monorepo-root-001'
title: 'AI Agents Monorepo'
type: 'documentation-entry-point'
status: 'active'
owner: '@root'
summary: 'Root README for the AI Agents Monorepo. This file serves as the primary entry point for machine agents. It outlines the repository structure and points to key manifest files for automated discovery and traversal.'
---

# mu

\<\!-- LLM AGENTS: START HERE. This section contains structured pointers to essential repository map and manifest files. Prioritize parsing these files for a comprehensive understanding of the codebase. \--\>

## ** Agent Entry Point & Data Sources**

For a complete and accurate map of this repository, consume the following files in order:

1. Monorepo Manifest (/MONOREPO\_MANIFEST.json):
   * Purpose: High-level project index.
   * Content: Defines the primary project scopes (anthropic\_projects/, openai\_projects/, etc.), lists all major projects/packages, and their locations.
   * Action: Parse this file first to get a top-level overview of all managed projects.
2. File Tree Map (/FILE\_TREE\_MAP.json or /FILE\_TREE\_MAP.yaml):
   * Purpose: Complete file and directory listing.
   * Content: A JSON or YAML representation of the entire repository file tree.
   * Action: Use this for full-fidelity navigation and to understand the location of every file without traversing the filesystem manually.
3. Repository Code Map (/REPOSITORY\_CODE\_MAP.md):
   * Purpose: Curated code summaries.
   * Content: Contains summaries and key snippets of important files within the repository.
   * Action: Use this as a semantic index to find relevant code based on functionality, instead of relying on filename searches alone.

Agent Protocol:

1. Ingest MONOREPO\_MANIFEST.json to identify all projects.
2. Cross-reference with FILE\_TREE\_MAP.json to locate specific files within those projects.
3. Consult REPOSITORY\_CODE\_MAP.md for semantic understanding of file contents before reading the files directly.
4. Default to reading individual file contents only after consulting the map files.

## **AI Agents Monorepo**

Welcome to *mu*, the AI Agents Monorepo. This repository consolidates multiple projects related to the development and tooling of AI agents from various organizations.

### **Purpose**

The primary goal of this monorepo is to provide a unified development environment that facilitates:

* Shared Tooling: Centralized scripts and configurations.
* Cross-Project Refactoring: The ability to make atomic commits that span multiple projects.
* Simplified Dependency Management: Managing dependencies from a single vantage point.
* Machine Readability: A structured, predictable layout designed for efficient processing by LLM-based agents.

### **Repository Structure**

The repository is organized into several key directories:

* /anthropic\_projects/: Contains projects and libraries originating from or related to Anthropic.
* /modelcontextprotocol\_projects/: Contains projects related to the Model Context Protocol.
* /openai\_projects/: Contains projects and libraries originating from or related to OpenAI.
* /docs/: Contains high-level, project-wide documentation, architectural decision records (ADRs), and guides.
* /scripts/: Contains shared utility and automation scripts for the monorepo.

### **Getting Started**

1. Explore the Code: Navigate the project directories to see the imported codebases.
2. Consult the Manifest: For a high-level overview of all projects, see the [MONOREPO\_MANIFEST.json](https://www.google.com/search?q=./MONOREPO_MANIFEST.json) file.
3. Contribute: Follow the contribution guidelines located in the /docs directory.

### **Updating Projects**

This monorepo was created using the git subtree strategy. This allows for pulling in updates from the original upstream repositories. To update a specific project, use the git subtree pull command.

```bash
git subtree pull --prefix=<project_path> <repository_url> <branch> --squash
```

Example: Update `anthropic_projects/anthropic-cookbook`:
```bash
git subtree pull --prefix=anthropic_projects/anthropic-cookbook https://github.com/anthropics/anthropic-cookbook.git main --squash
```


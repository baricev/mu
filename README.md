---
id: 'monorepo-root-001'
title: 'AI Agents Monorepo'
type: 'documentation-entry-point'
status: 'active'
owner: '@root'
summary: 'Root README for the AI Agents Monorepo. This file serves as the primary entry point for machine agents. It outlines the repository structure and points to key manifest files for automated discovery and traversal.'
---

# AI Agents Monorepo

## Repository Overview
This repository consolidates multiple projects related to AI agents development and tooling. The monorepo structure enables:
- Centralized tooling and configurations
- Atomic cross-project commits
- Simplified dependency management
- Machine-optimized layout

## Repository Structure
Top-level directories:
- `anthropic_projects/`: Anthropic-related projects and libraries
- `modelcontextprotocol_projects/`: Model Context Protocol projects
- `openai_projects/`: OpenAI-related projects and libraries
- `docs/`: Project-wide documentation and ADRs
- `scripts/`: Shared utility and automation scripts

## Essential Machine-Readable Files
### `/MONOREPO_MANIFEST.json`
- Purpose: High-level project index
- Content: Defines project scopes and lists all major projects/packages
- Action: Parse first for top-level overview

### `/FILE_TREE_MAP.json` or `/FILE_TREE_MAP.yaml`
- Purpose: Complete file/directory listing
- Content: JSON/YAML representation of repository file tree
- Action: Use for full-fidelity navigation

### `/REPOSITORY_CODE_MAP.md`
- Purpose: Curated code summaries
- Content: Key snippets and file summaries
- Action: Use as semantic index for code discovery

## Agent Protocol
1. Ingest `MONOREPO_MANIFEST.json` to identify projects
2. Cross-reference with `FILE_TREE_MAP.json` for file locations
3. Consult `REPOSITORY_CODE_MAP.md` for semantic understanding
4. Read individual files only after consulting map files

## Project Maintenance
Projects are maintained using `git subtree`. To update a project:

```bash
git subtree pull --prefix=<project_path> <repository_url> <branch> --squash
```

Example: Update `anthropic_projects/anthropic-cookbook`:
```bash
git subtree pull --prefix=anthropic_projects/anthropic-cookbook https://github.com/anthropics/anthropic-cookbook.git main --squash
```


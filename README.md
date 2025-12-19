# Google Anti-Gravity Global Workflows (v1.2.0)

> Automated workflows for managing Google Anti-Gravity projects with consistency, proper documentation, and version control.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Semantic Versioning](https://img.shields.io/badge/semver-2.0.0-blue)](https://semver.org/)

## 📋 Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Available Workflows](#available-workflows)
- [Semantic Versioning Guide](#semantic-versioning-guide)
- [Required Project Files](#required-project-files)
- [Typical Workflow](#typical-workflow)
- [Project Types](#project-types)
- [GitHub Integration](#github-integration)
- [Copyright Management](#copyright-management)
- [Best Practices](#best-practices)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

---

## Overview



This repository contains automated workflows for managing Google Anti-Gravity projects. These workflows ensure consistency, proper documentation, and version control across all projects.

---

## Installation

### Option 1: Use from Global Location (Recommended)

Copy the workflow files to your global `.gemini` directory:

```bash
# Copy workflows to global location
cp -r /Users/kuancheen/Documents/Github/anti-gravity-global-workflows/*.md /Users/kuancheen/.gemini/antigravity/workflows/
```

This makes workflows accessible from **all workspaces**.

### Option 2: Use from This Repository

Keep workflows in this repository and manually reference them when needed.

### Syncing Changes

After making updates to workflows in this repository:

```bash
# Sync to global location
cp -r *.md /Users/kuancheen/.gemini/antigravity/workflows/

# Or use git to track and push changes
git add .
git commit -m "chore: update workflows"
git push origin main
```

---

## 📋 Available Workflows

### 1. Project Setup and Compliance Audit (`/new-project-init`)

**Purpose**: Automatically sets up a new project OR audits an existing project for compliance with latest global workflow standards.

**What it does**:
- ✅ **Compliance Audit**: Reviews existing projects for required files, headers, and automation.
- ✅ **Auto-Fix Recommendations**: Offers to create missing files, update headers, and copy local workflows.
- ✅ Initializes Git repository with `.gitignore`.
- ✅ Creates GitHub repository with **name confirmation**.
- ✅ Generates GitHub Actions workflow for **GitHub Pages** (optional).
- ✅ Sets up **local workspace workflows** by copying global templates.
- ✅ Generates `README.md`, `CHANGELOG.md`, and `LICENSE` following the latest standards.
- ✅ Sets up initial version (**v0.0.1 (Beta)**).
- ✅ Commits and pushes to GitHub (with user confirmation).

**When to use**: 
- Starting any new Google Anti-Gravity project.
- **Reviewing an existing project** (especially older ones) for compliance with workflow standards.

**How to use**: Type `/new-project-init` in any project directory.

---

## 📋 Available Workflows

### 2. Version Update (`/version-update`)

**Purpose**: Automatically manages version updates across all project files following [Semantic Versioning](https://semver.org/).

**What it does**:
- 🔍 Analyzes changes to determine version bump (Major/Minor/Patch)
- 📝 Updates version in `index.html` (web apps only)
- 📋 Updates `CHANGELOG.md` with new version entry
- 📖 Updates `README.md` version references
- ©️ Updates copyright year if needed
- 🏷️ Creates Git commit and optional version tag
- 🚀 Pushes to GitHub (with user confirmation)

**When to use**: This workflow is **automatically triggered** by the agent after you confirm changes. You don't need to manually invoke it.

---

## 🎯 Semantic Versioning Guide

All projects follow semantic versioning: `MAJOR.MINOR.PATCH`

| Version Type | When to Use | Example |
|--------------|-------------|---------|
| **MAJOR** | Breaking changes that affect existing functionality | `1.5.3` → `2.0.0` |
| **MINOR** | New features that are backward compatible | `1.5.3` → `1.6.0` |
| **PATCH** | Bug fixes and minor improvements | `1.5.3` → `1.5.4` |

---

## 📁 Required Project Files

Every Google Anti-Gravity project must include:

### `README.md`
- Project title with version number (starting at `v0.0.1 (Beta)`).
- Description and purpose.
- Installation/setup instructions.
- Usage examples.
- Features list.
- License and copyright information.

### `CHANGELOG.md`
- Follows [Keep a Changelog](https://keepachangelog.com/) format.
- Documents all notable changes.
- Organized by version with dates.

### `LICENSE`
- Appropriate license (MIT, Apache 2.0, GPL, etc.).
- Copyright notice with dynamic year detection.

### `index.html` (Web Apps)
- Author/Description comment block at the very top.
- Version string (e.g., `App Version: v0.0.1 (Beta)`).
- Copyright notice in footer or meta tags.

---

## 🔄 Typical Workflow

### Starting a New Project

1. Create project directory.
2. Agent automatically runs `/new-project-init`.
3. GitHub repository name is confirmed.
4. All documentation files and local workflows are generated.
5. Initial commit is made and pushed (after your confirmation).

### Making Changes to Existing Project

1. Request feature/fix from agent.
2. Agent implements changes.
3. You review and confirm changes.
4. **Agent automatically runs version update workflow**.

---

## 🔐 GitHub Integration

All workflows include GitHub integration:

- **User Confirmation Required**: Agent will always request confirmation before pushing to GitHub.
- **Conventional Commits**: All commits follow conventional commit format.
- **Version Tags**: Optional Git tags for releases (e.g., `v1.5.3`).

---

## 🚀 Best Practices

1. **Perform Compliance Audits Regularly**: Run `/new-project-init` in existing projects to ensure they have the latest workflows and headers.
2. **Always confirm changes** before the agent proceeds with version updates.
3. **Review CHANGELOG entries** to ensure accuracy.
4. **Use descriptive commit messages** following conventional commits.

---

## 🛠️ Customization

These workflows can be modified by editing the `.md` files in this directory:
- `new-project-init.md`
- `version-update.md`

---

## 🤝 Contributing

We welcome contributions to improve these workflows! (See the `CHANGELOG.md` for our version history).

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Copyright (c) 2025 Google Anti-Gravity Team**

---

**Last Updated**: 2025-12-19
**Version**: 1.2.0  
**Maintained by**: Google Anti-Gravity Team

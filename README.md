# Google Anti-Gravity Global Workflows (v1.17.0)

> Automated workflows for managing Google Anti-Gravity projects with consistency, proper documentation, and version control.

![Version](https://img.shields.io/badge/version-v1.17.0-blue)
[![Status](https://img.shields.io/badge/status-active-success)](https://github.com/kuancheen/anti-gravity-global-workflows)
[![Live Demo](https://img.shields.io/badge/demo-online-green.svg)](https://github.com/kuancheen/anti-gravity-global-workflows)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/kuancheen/anti-gravity-global-workflows/blob/main/LICENSE)
[![Semantic Versioning](https://img.shields.io/badge/semver-2.0.0-blue)](https://semver.org/spec/v2.0.0.html)

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
- ✅ **Compliance Audit**: Reviews existing projects for required files, headers, badges, and automation.
- ✅ **Workflow Synchronization**: Verifies if local automation files match the latest global versions.
- ✅ **Auto-Fix Recommendations**: Offers to create missing files, update headers, add badges, and **replace** outdated workflows with global templates.
- ✅ Initializes Git repository with `.gitignore`.
- ✅ Creates GitHub repository with **name confirmation** and **auth pre-checks**.
- ✅ Generates GitHub Actions workflow for **GitHub Pages** (optional).
- ✅ **Versioned Slash Commands**: Workflows are versioned in their filenames (e.g., `/new-project-init-v1.11.0`) to ensure explicit version control.
- ✅ **Standardized Footer**: Enforces a consistent footer with MD-Viewer documentation links, GitHub profile link, and **Hits.sh view counter**.
- ✅ **Favicon & Cache Bursting**: Generates relevant favicons and implements cache bursting for internal assets.
- ✅ **Favicon & Cache Bursting**: Generates relevant favicons and implements cache bursting for internal assets.
- ✅ **Asset Separation**: Enforces moving inlined CSS and JS into separate `style.css` and `main.js` files.
- ✅ **Automates Pages Source**: Sets Pages build source to GitHub Actions via API.
- ✅ Sets up **local workspace workflows** by copying global templates.
- ✅ Generates `README.md` with **standardized badges**, `CHANGELOG.md`, and `LICENSE` following the latest standards.
- ✅ Sets up initial version (**v0.0.1 (Beta)**).
- ✅ Commits and pushes to GitHub (with user confirmation).

**When to use**: 
- Starting any new Google Anti-Gravity project.
- **Reviewing an existing project** (especially older ones) for compliance and workflow updates.

**How to use**: Type `/new-project-init` in any project directory.

---

## 📋 Available Workflows

### 2. Version Update (`/version-update`)

**Purpose**: Automatically manages version updates across all project files following [Semantic Versioning](https://semver.org/).

**What it does**:
- 🔍 Analyzes changes to determine version bump (Major/Minor/Patch)
- 📝 Updates version in `index.html` (web apps only)
- 🚀 **Updates Cache Bursting**: Automatically increments version query parameters on internal asset links.
- 📋 Updates `CHANGELOG.md` with new version entry
- 📖 **Updates README.md** references and **standardized badges** (Version, Status).
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
- **Standardized Badges**: Version, Status, (Live Demo), License, Semantic Versioning.
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
- **Robustness**: includes `gh auth status` checks and browser-based fallback strategies.

---

## 🚀 Best Practices

1. **Perform Compliance Audits Regularly**: Run `/new-project-init` in existing projects to ensure they have the latest workflows, headers, and badges.
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
**Version**: 1.17.0  
**Maintained by**: Google Anti-Gravity Team

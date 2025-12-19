# Google Anti-Gravity Global Workflows (v1.0.1)

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

### 1. New Project Initialization (`/new-project-init`)

**Purpose**: Automatically sets up a new project with all required documentation and GitHub integration.

**What it does**:
- ✅ **Reviews existing projects** for compliance with workflow standards
- ✅ Recommends changes for non-compliant projects
- ✅ Initializes Git repository with `.gitignore`
- ✅ Creates GitHub repository
- ✅ Generates `README.md` with project structure
- ✅ Creates `CHANGELOG.md` following [Keep a Changelog](https://keepachangelog.com/) format
- ✅ Adds `LICENSE` file with copyright
- ✅ Sets up initial version (v1.0.0)
- ✅ Commits and pushes to GitHub (with user confirmation)

**When to use**: 
- Starting any new Google Anti-Gravity project
- Reviewing an existing project for compliance with workflow standards

**How to use**: Type `/new-project-init` when creating a new project

---

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

**Automatic trigger conditions**:
- After implementing new features, bug fixes, or changes
- When user confirms the changes are ready
- Before finalizing any update

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
- Project title with version number
- Description and purpose
- Installation/setup instructions
- Usage examples
- Features list
- License and copyright information

### `CHANGELOG.md`
- Follows [Keep a Changelog](https://keepachangelog.com/) format
- Documents all notable changes
- Organized by version with dates
- Categories: Added, Changed, Fixed, Removed, Security

### `LICENSE`
- Appropriate license (MIT, Apache 2.0, GPL, etc.)
- Copyright notice with current year
- Full license text

### `.gitignore`
- Project-specific ignore patterns
- Common patterns (node_modules, build dirs, env files)

---

## 🔄 Typical Workflow

### Starting a New Project

1. Create project directory
2. Agent automatically runs `/new-project-init`
3. GitHub repository is created
4. All documentation files are generated
5. Initial commit is made and pushed (after your confirmation)

### Making Changes to Existing Project

1. Request feature/fix from agent
2. Agent implements changes
3. You review and confirm changes
4. **Agent automatically runs version update workflow**:
   - Determines version bump type
   - Updates all relevant files
   - Updates CHANGELOG with changes
   - Commits and pushes to GitHub (after your confirmation)

---

## 🎨 Project Types

### Web Applications
- Include `index.html` with version string (e.g., `App Version: v1.7.1`)
- Version displayed in UI footer or meta tags
- Copyright notice in HTML

### Non-Web Projects
- Version only in `README.md` and `CHANGELOG.md`
- No `index.html` modifications

---

## 🔐 GitHub Integration

All workflows include GitHub integration:

- **User Confirmation Required**: Agent will always request confirmation before pushing to GitHub
- **Conventional Commits**: All commits follow conventional commit format
- **Version Tags**: Optional Git tags for releases (e.g., `v1.5.3`)
- **Remote Tracking**: Automatic setup of remote repository

---

## 📝 Copyright Management

Copyright years are automatically managed:

- **Project creation year**: 2025
- **Current year = 2025**: Copyright shows `2025`
- **Current year > 2025**: Copyright shows `2025-[Current Year]`

Updated in: `LICENSE`, `README.md`, and `index.html` (web apps)

---

## 🚀 Best Practices

1. **Always confirm changes** before the agent proceeds with version updates
2. **Review CHANGELOG entries** to ensure accuracy
3. **Use descriptive commit messages** following conventional commits
4. **Tag releases** for important versions
5. **Keep documentation up-to-date** with actual functionality

---

## 🛠️ Customization

These workflows can be modified by editing the `.md` files in this directory:
- `new-project-init.md`
- `version-update.md`

---

## 📚 References

- [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
- [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

## 🤝 Contributing

We welcome contributions to improve these workflows!

### How to Contribute

1. **Fork the repository**
2. **Make your changes** following the workflow standards
3. **Test your changes** in a real project
4. **Update CHANGELOG.md** with your changes
5. **Submit a pull request** with a clear description

### Development Workflow

1. Make changes to workflow files in this repository
2. Test the workflows in a sample project
3. Update documentation if needed
4. Sync to global location:
   ```bash
   cp -r *.md /Users/kuancheen/.gemini/antigravity/workflows/
   ```
5. Commit and push:
   ```bash
   git add .
   git commit -m "feat: description of changes"
   git push origin main
   ```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Copyright (c) 2025 Google Anti-Gravity Team**

---

**Last Updated**: 2025-12-16  
**Version**: 1.0.1  
**Maintained by**: Google Anti-Gravity Team

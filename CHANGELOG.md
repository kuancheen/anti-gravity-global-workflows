# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-12-16

### Added
- Initial release of Google Anti-Gravity Global Workflows
- New Project Initialization workflow (`/new-project-init`)
  - Automatic project structure review for existing workspaces
  - Creates README.md, CHANGELOG.md, LICENSE, and .gitignore
  - GitHub repository creation and setup
  - Initial commit and push with user confirmation
- Version Update workflow (`/version-update`)
  - Automatic triggering after user confirms changes
  - Project compliance pre-check before version updates
  - Semantic versioning (Major/Minor/Patch) analysis
  - Updates across README.md, CHANGELOG.md, and index.html (web apps)
  - Copyright year management
  - Git commit, tag, and push with user confirmation
- Comprehensive README documentation
  - Workflow descriptions and usage instructions
  - Semantic versioning guide
  - Required project files specification
  - Typical workflow examples
  - GitHub integration details
  - Best practices and references

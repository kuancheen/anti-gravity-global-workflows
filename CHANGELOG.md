# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.2] - 2025-12-19

### Changed
- Copyright logic in `/version-update` updated to dynamically detect project creation year instead of hardcoding `2025`

## [1.1.1] - 2025-12-19

### Changed
- Starting version in `/new-project-init` updated to `v0.0.1 (Beta)`
- Copyright notices in `/new-project-init` updated to use dynamic current year
- Web apps now require an author/description comment block at the top of `index.html`

## [1.1.0] - 2025-12-19

### Added
- Repository name confirmation step in `/new-project-init`
- GitHub Pages deployment workflow (`static-pages-deploy.yml`)
- Local workflow setup in `/new-project-init` (copies global `version-update.md`)

## [1.0.1] - 2025-12-19

### Removed
- `GITHUB_SETUP.md` from the project and workspace

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

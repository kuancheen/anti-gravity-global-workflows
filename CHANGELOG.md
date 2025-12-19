# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.4.0] - 2025-12-19

### Added
- Automated README badge updates in `/version-update` (Version and Status)
- Logic to transition project status from "Beta" to "Live/Production" during version updates

## [1.6.0] - 2025-12-19

### Added
- Enforcement of clean asset separation (moving inlined CSS/JS to external files) in `/new-project-init`
- Automated cache bursting for internal CSS and JS files using version query parameters
- Cache bursting updates integrated into the `/version-update` workflow

## [1.5.0] - 2025-12-19

### Added
- Favicon auditing and automated setup for web applications in `/new-project-init`
- Support for SVG-based favicons (data URIs or separate files)

## [1.3.1] - 2025-12-19

### Changed
- Updated workspace `README.md` to include all five standard badges (Version, Status, Live Demo, License, SemVer)

## [1.3.0] - 2025-12-19

### Added
- Standardized badges in README generation logic (Version, Status, Live Demo, License, SemVer)
- Compliance Audit now checks for presence of required badges in existing projects

## [1.2.2] - 2025-12-19

### Added
- Enhanced Compliance Audit to check if local workflows match latest global versions
- Explicit logic to offer replacing/updating outdated local workflows (`version-update.md`, `static.yml`)

## [1.2.1] - 2025-12-19

### Added
- GitHub CLI authentication pre-check (`gh auth status`) in `/new-project-init`
- Automated GitHub Pages source configuration via API (`gh api`)
- Explicit browser fallback strategy for GitHub operations

## [1.2.0] - 2025-12-19

### Added
- Rebranded `/new-project-init` to **Project Setup and Compliance Audit**
- Enhanced audit logic for existing projects to check for:
  - HTML comment headers (Author, Description, App Name, Year)
  - Existence of local `.agent/workflows/`
  - Versioning consistency with `v0.0.1 (Beta)` standard
- New "Best Practice" to perform regular compliance audits

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

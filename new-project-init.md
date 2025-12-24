---
description: Initialize a new project or audit an existing one for compliance with workflow standards
---

# Project Setup and Compliance Audit Workflow

This workflow ensures every project starts and maintains the required documentation files, proper structure, and automation workflows.

## When Invoked in Existing Workspace

**IMPORTANT**: If this workflow is invoked in an **existing workspace** (not a new/empty project), it functions as a **Compliance Audit**:

1.  **Review Current Project Structure**:
    -   Check if `README.md` exists and contains:
        -   Project title with version number and **required badges**.
        -   Description and purpose.
        -   Installation/setup instructions.
        -   License and copyright information.
        -   **Hits.sh Badge** view counter (`style=flat`).
    -   Check if `CHANGELOG.md` exists and follows Keep a Changelog format.
    -   Check if `LICENSE` file exists with proper copyright.
    -   Check if `.gitignore` exists.
    -   **For web apps**:
        -   Check if `index.html` has the required **HTML Comment Header** (Author, Description, App Name, Year).
        -   Check if `index.html` has a version string.
        -   Check for a **favicon** (link tag in `index.html` and existence of the file/data URI).
        -   **Asset Separation**: Check if CSS and JS are inlined in `index.html` or separated into dedicated files (`style.css`, `main.js`).
        -   **Cache Bursting**: Check if internal CSS/JS links use version query parameters (e.g., `?v=X.Y.Z`). **Skip external CDNs**.
        -   **Standardized Footer**: Check if `index.html` contains the standardized footer with:
            -   Version string (e.g., `v1.0.0`).
            -   Links to `README` and `CHANGELOG` via `md-viewer` (e.g., `https://kuancheen.github.io/md-viewer/?...`).
            -   Copyright notice linking to the author's GitHub profile.
            -   **Hits.sh Badge** view counter.
    -   **Automation Check (Sync with Global)**:
        -   Check if `.agent/workflows/version-update.md` exists. **Verify if it matches the latest global version**.
        -   Check if `.github/workflows/static.yml` exists if it's a web app. **Verify if it matches the latest global template** (`static-pages-deploy.yml`).

2.  **Identify Missing or Outdated Elements**:
    -   List all missing required files or **missing badges** in README.
    -   Identify files that don't follow the latest standards (e.g., hardcoded years, missing headers).
    -   Identify missing or generic **favicons** in web projects.
    -   Identify **inlined assets** that should be moved to separate files.
    -   Identify **missing cache bursting filters** for internal assets.
    -   Identify **outdated local workflows** that should be replaced with the latest versions from the global workspace.
    -   Note any version inconsistencies (recommend `v0.0.1 (Beta)` if early stage).

3.  **Recommend Changes and Fixes**:
    -   Provide a clear list of recommended changes to bring the project into compliance.
    -   Offer to:
        -   Create missing files.
        -   Update non-compliant files (including adding badges, separating assets, and adding cache bursting).
        -   **Sync/Replace Local Workflows**: Offer to replace existing local `version-update.md` or `static.yml` with the latest versions from the global workspace.
        -   **Add GitHub Actions**: Offer to add `static.yml` for web projects if missing.
    -   **Request user confirmation** before making any changes.

4.  **After User Confirms**:
    -   Proceed with creating/updating/replacing files as needed.
    -   Continue with relevant steps below if the project also requires a new repository or initial commit.

---

1. **Initialize Git Repository**:
   - Run `git init` in the project directory.
   - Create `.gitignore` with common ignore patterns for the project type.
   - Include node_modules, build directories, environment files, etc.

2. **Create GitHub Repository**:
   - **Pre-check Authentication**:
     - Run `gh auth status` to verify GitHub CLI authentication.
     - **Fallback Strategy**: If not authenticated, notify the user and use the **Browser Tool** to create the repository and manage settings manually via the GitHub web interface.
   - **Suggest Repository Name**: Based on the project title, suggest a descriptive name (e.g., `my-new-project`).
   - **Request User Confirmation**: Wait for the user to confirm or provide a different repository name before proceeding.
   - **Create Repository**: Once confirmed, create the new repository on GitHub (via `gh repo create` or web interface).
   - Note the repository URL for later use.
   - Do not initialize with README, LICENSE, or .gitignore (we'll create these locally).

3. **Create README.md**:
   - Add project title with initial version (v0.0.1 (Beta)).
   - **Add Standard Badges**: Include the following badges at the very top, below the title:
     - **Version**: `![Version](https://img.shields.io/badge/version-v0.0.1%20(Beta)-blue)`
     - **License**: `![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)` (or appropriate for the license chosen)
     - **Semantic Versioning**: `![Semantic Versioning](https://img.shields.io/badge/semver-2.0.0-blue)`
     - **Views**: `![Views](https://hits.sh/:owner.github.io/:repo.svg?view=today-total&style=flat&label=👁️%20Views&extraCount=0&color=6366f1)`
     - **Status**: `![Status](https://img.shields.io/badge/status-active-success)` (for active development)
     - **Live Demo (Web Apps Only)**: `![Live Demo](https://img.shields.io/badge/demo-online-green.svg)` linking to the GitHub Pages URL.
   - Include project description and purpose.
   - Add installation/setup instructions.
   - Include usage examples.
   - Add features list.
   - Include license information.
   - Add copyright notice with **current year** (the year the project is initialized).
   - Include contact/contribution information if applicable.

4. **Create CHANGELOG.md**:
   - Add header: `# Changelog`.
   - Add description: `All notable changes to this project will be documented in this file.`.
   - Add format note: `The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).`.
   - Add initial version entry:
     ```
     ## [0.0.1 (Beta)] - YYYY-MM-DD
     ### Added
     - Initial release
     ```

5. **Create LICENSE**:
   - Choose appropriate license (MIT, Apache 2.0, GPL, etc.).
   - Add copyright notice with **current year** (the year the project is initialized).
   - Include full license text.
   - Add project/author name.

6. **Add GitHub Actions (Web Apps Only)**:
   - **Ask User**: Check if the project is a static web app and if they want GitHub Pages deployment.
   - **Create Workflow**: If yes, create `.github/workflows/static.yml` for deploying static content to GitHub Pages.
   - Use the standard template from global workflows (`static-pages-deploy.yml`) for deployment.
   - **Automate Pages Source**:
     - After creating the workflow, explicitly create the GitHub Pages site configuration via POST:
       ```bash
       echo '{"build_type":"workflow","source":{"branch":"main","path":"/"}}' | gh api -X POST repos/:owner/:repo/pages --input -
       ```
     - **Verification**: Run `gh api repos/:owner/:repo/pages` to verify `build_type` is `workflow`.
     - **Note**: This explicitly creates the Pages resource. It may still fail if the repository has no commits yet; if it fails, proceed to Step 10 and try again there.
     - **Fallback**: If the API call fails or CLI is not authenticated, use the **Browser Tool** to navigate to `Settings > Pages` and set the source to "GitHub Actions".

7. **Setup Local Workflows**:
   - **Copy Global Version Update**: Copy the global `/version-update.md` to the project's local `.agent/workflows/` directory.
   - This allows the project to have a workspace-specific version update workflow.

8. **Update Project Files**:
   - **For web apps only**:
     - **Asset Separation**: Always separate CSS and JS into `style.css` and `main.js` files. Link them in `index.html`.
     - **Cache Bursting**: Add version-based query parameters to **internal** asset links (e.g., `href="style.css?v=0.0.1 (Beta)"`).
     - **HTML Comment Header**: Add a comment block at the very top of `index.html` including:
       - Application Name
       - Brief description of the application
       - Author Name
       - Copyright year
     - **Version String**: If `index.html` exists, add version string (e.g., `App Version: v0.0.1 (Beta)`).
     - **Favicon**: Add a relevant SVG favicon. Use a data URI for simplicity or create a separate `favicon.svg` file and link it in `index.html`.
     - **Standardized Footer**: Add a footer to `index.html` with the following format:
       ```html
       <footer>
           <p>
               vX.Y.Z | 
               <a href="https://kuancheen.github.io/md-viewer/?https://github.com/:owner/:repo/blob/main/README.md" target="_blank">README</a> |                <a href="https://kuancheen.github.io/md-viewer/?https://github.com/:owner/:repo/blob/main/CHANGELOG.md" target="_blank">CHANGELOG</a> | 
                &copy; <span id="year">YYYY</span> <a href="https://github.com/:owner" target="_blank">:author</a> |
                <img src="https://hits.sh/:owner.github.io/:repo.svg?view=today-total&style=flat-square&label=👁️%20Views&extraCount=0&color=6366f1" alt="Hits">
            </p>
        </footer>
       ```
       - Replace `:owner`, `:repo`, and `:author` with the correct values.
     - Add copyright notice in footer or meta tags.
   - Ensure consistent branding across files.

9. **Verify Documentation**:
   - Check that all required files and badges are created.
   - Ensure version numbers are consistent (v0.0.1 (Beta)).
   - Verify copyright year is correct (current year).
   - Review that all documentation is accurate and complete.

10. **Initial Commit and Push to GitHub**:
    - Add remote: `git remote add origin <repository-url>`.
    - **Final Pages Source Check**: For web apps, try setting the Pages source to "Actions" again via API *now* that the remote is established.
    - Stage all files: `git add .`.
    - Create initial commit: `git commit -m "chore: initial project setup with documentation"`.
    - **Request user confirmation before pushing**.
    - After confirmation, push to GitHub: `git push -u origin main`.
    - **Post-Push Verification**:
      - Wait 10 seconds, then check if the Pages deployment action starts.
      - If the action fails with a 404 or "Pages not configured" error, re-run the `gh api` command to set the source and manually trigger the action again.

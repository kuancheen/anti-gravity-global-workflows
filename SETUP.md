# Setup Instructions

This document provides step-by-step instructions for setting up and using the Google Anti-Gravity Global Workflows.

## Initial Setup

### 1. Create GitHub Repository

Create a new repository on GitHub:

```bash
# Option 1: Using GitHub CLI
gh repo create anti-gravity-global-workflows --public --source=. --remote=origin

# Option 2: Using GitHub Web Interface
# 1. Go to https://github.com/new
# 2. Repository name: anti-gravity-global-workflows
# 3. Description: Automated workflows for managing Google Anti-Gravity projects
# 4. Public or Private (your choice)
# 5. DO NOT initialize with README, .gitignore, or license
# 6. Click "Create repository"
```

### 2. Add Remote and Push

```bash
# Add remote (replace with your GitHub username/org)
git remote add origin https://github.com/YOUR_USERNAME/anti-gravity-global-workflows.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Sync to Global Location

Copy workflows to the global location so they're accessible from all workspaces:

```bash
# Create global workflows directory if it doesn't exist
mkdir -p /Users/kuancheen/.gemini/antigravity/workflows

# Copy workflow files (excluding git files and other non-workflow files)
cp new-project-init.md version-update.md README.md /Users/kuancheen/.gemini/antigravity/workflows/
```

---

## Daily Workflow

### Making Changes to Workflows

1. **Edit workflows** in this repository
2. **Test** in a sample project
3. **Update CHANGELOG.md** with your changes
4. **Commit and push**:
   ```bash
   git add .
   git commit -m "feat: your change description"
   git push origin main
   ```
5. **Sync to global location**:
   ```bash
   cp new-project-init.md version-update.md README.md /Users/kuancheen/.gemini/antigravity/workflows/
   ```

### Using Workflows in Projects

From any workspace, use the workflows:

- Type `/new-project-init` to initialize a new project
- Version updates happen automatically after you confirm changes

---

## Troubleshooting

### Workflows Not Found

If workflows aren't being recognized:

1. Check that files exist in global location:
   ```bash
   ls -la /Users/kuancheen/.gemini/antigravity/workflows/
   ```

2. Re-sync from this repository:
   ```bash
   cp new-project-init.md version-update.md README.md /Users/kuancheen/.gemini/antigravity/workflows/
   ```

### Different Versions in Different Locations

To ensure consistency:

1. Edit workflows only in this repository
2. Always sync to global location after changes
3. Consider this repository as the source of truth

---

## Git Configuration

Set your Git identity (if not already set):

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

## Next Steps

1. ✅ Create GitHub repository
2. ✅ Push initial commit
3. ✅ Sync workflows to global location
4. ✅ Test workflows in a sample project
5. ✅ Share repository URL with team members

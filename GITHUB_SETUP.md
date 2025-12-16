# Quick GitHub Setup

Since GitHub CLI is not installed, follow these steps to create the repository and push:

## Step 1: Create Repository on GitHub

1. Go to https://github.com/new
2. Fill in the details:
   - **Repository name**: `anti-gravity-global-workflows`
   - **Description**: `Automated workflows for managing Google Anti-Gravity projects`
   - **Visibility**: Public (recommended) or Private
   - **DO NOT** check "Initialize this repository with a README"
3. Click "Create repository"

## Step 2: Push to GitHub

After creating the repository, GitHub will show you a URL. Copy it and run:

```bash
# Replace YOUR_USERNAME with your actual GitHub username
git remote add origin https://github.com/YOUR_USERNAME/anti-gravity-global-workflows.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Or Use SSH (if configured):

```bash
git remote add origin git@github.com:YOUR_USERNAME/anti-gravity-global-workflows.git
git branch -M main
git push -u origin main
```

## Already Done ✅

- ✅ Git repository initialized
- ✅ Initial commit created
- ✅ Workflows synced to global location: `/Users/kuancheen/.gemini/antigravity/workflows/`

## Next Steps

1. Create GitHub repository (steps above)
2. Add remote and push
3. Share the repository URL with your team
4. Start using workflows in any workspace with `/new-project-init`

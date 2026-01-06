---
description: Generate a comprehensive status report for cross-platform AI context sharing
---

# Summarize Progress Workflow

This workflow generates a detailed status report of the current project state, perfect for sharing context with other AI platforms or team members.

## Purpose

When you need to:
- Switch to a different AI platform mid-project
- Share project context with collaborators
- Create a checkpoint of current progress
- Document the current state for future reference

## Steps

1. **Read Current State**:
   - Review the latest `task.md` in the brain folder
   - Review the latest `walkthrough.md` in the brain folder
   - Review the latest `implementation_plan.md` if it exists
   - Check the current working directory and open files

2. **Analyze Project Context**:
   - Identify the main objective
   - List completed tasks
   - List in-progress tasks
   - List pending/blocked tasks
   - Note any important decisions or design choices

3. **Review Recent Changes**:
   - Check recent file modifications
   - Review recent commits (if applicable)
   - Identify key features implemented
   - Note any outstanding issues or bugs

4. **Generate Status Report**:
   Create a comprehensive markdown report (to be displayed and saved to `project-status-report.md` in the project root) with the following sections:
   
   ```markdown
   # Project Status Report
   Generated: [Current Date/Time]
   
   ## Project Overview
   - **Name**: [Project Name]
   - **Current Version**: [Version]
   - **Status**: [Active/Paused/Blocked]
   
   ## Main Objective
   [Brief description of the primary goal]
   
   ## Progress Summary
   ### Completed ✅
   - [List of completed tasks]
   
   ### In Progress 🔄
   - [List of current tasks]
   
   ### Pending ⏳
   - [List of upcoming tasks]
   
   ### Blocked 🚫
   - [List of blocked items with reasons]
   
   ## Recent Changes
   [Summary of recent modifications and additions]
   
   ## Key Decisions & Design Choices
   [Important architectural or design decisions made]
   
   ## Current Challenges
   [Any issues, bugs, or obstacles]
   
   ## Next Steps
   [Immediate next actions to take]
   
   ## Additional Context
   [Any other relevant information for continuity]
   ```

5. **Present and Persist Report**:
   - Display the formatted report to the user.
   - **Create or Update File**: Automatically create or update `project-status-report.md` in the project root with the generated content.
   - Offer to commit the changes if applicable.
   - Suggest any additional context that might be helpful.

## Notes

- This report is designed to be self-contained and portable
- Include enough context for someone (or another AI) to pick up where you left off
- Focus on actionable information and clear status indicators
- Keep technical details concise but comprehensive

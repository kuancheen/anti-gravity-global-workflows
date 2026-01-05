---
description: Quickly sync to current project state by reading brain artifacts
---

# Catch Up Workflow

This workflow allows the agent to instantly sync to the current project state by reading the latest artifacts from the brain folder.

## Purpose

Use this workflow when:
- Starting a new conversation session
- Resuming work after a break
- Switching contexts between projects
- An agent needs to quickly understand where the project stands

## Steps

1. **Locate Brain Folder**:
   - Identify the current brain folder path: `/Users/kuancheen/.gemini/antigravity/brain/[conversation-id]/`
   - Verify the folder exists and is accessible

2. **Read Latest Artifacts**:
   - **Read `task.md`**: 
     - Review all tasks (completed, in-progress, pending)
     - Understand the current task breakdown
     - Identify what's been done and what's next
   
   - **Read `walkthrough.md`**:
     - Review recent changes and implementations
     - Understand what was tested and verified
     - Note any important outcomes or results
   
   - **Read `implementation_plan.md`** (if exists):
     - Review the current plan
     - Understand proposed changes
     - Check if plan was approved or needs revision

3. **Analyze Current State**:
   - Determine the current phase (Planning/Execution/Verification)
   - Identify the active task or focus area
   - Note any blockers or pending decisions
   - Understand the immediate next steps

4. **Confirm Understanding**:
   - Provide a brief summary of what you learned:
     ```
     I've caught up on the project state:
     - Main Objective: [Brief description]
     - Current Phase: [Planning/Execution/Verification]
     - Last Completed: [Most recent achievement]
     - Next Steps: [What to do next]
     - Status: [Any blockers or notes]
     ```

5. **Ready to Continue**:
   - Confirm readiness to proceed with the next task
   - Ask if there are any updates or changes since the last session
   - Offer to continue from where the previous session left off

## Notes

- This workflow is designed for quick context restoration
- It relies on up-to-date brain artifacts (task.md, walkthrough.md)
- If artifacts are missing or outdated, notify the user
- This is particularly useful when switching between AI platforms or sessions

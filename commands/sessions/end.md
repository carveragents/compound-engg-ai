---
allowed-tools: Read, Write, Edit, Grep, Bash(echo:*), Bash(mkdir -p:*), Bash(cat:*)
description: End current development session
---

<!-- Some parts of this command are specific to Claude Code,
especially folder locations, front matter, and argument passing.
Modify as needed if using with other coding agents. -->

End the current development session by:

1. Check `.claude/.sessions/.current-session` for the active session
2. If no active session, inform user there's nothing to end
3. If session exists, append a comprehensive session summary including:
   - Session duration
   - Git summary:
     * Total files changed (added/modified/deleted)
     * List all changed files with change type
     * Number of commits made (if any)
     * Final git status
   - Todo summary:
     * Total tasks completed/remaining
     * List all completed tasks
     * List any incomplete tasks with status
   - Key accomplishments
   - All features implemented
   - Problems encountered and solutions
   - Breaking changes or important findings
   - Dependencies added/removed
   - Configuration changes
   - Deployment steps taken
   - Lessons learned including any reminders/tips/corrections provided by the user
   - What wasn't completed
   - Tips for future developers

4. Note the learnings from this sessions as follows:
	- Check if `docs/LESSONS.md` exists
	- If the file does not exist, create it and add two empty sections to it
		- SESSIONS
		- LESSONS
	- Append the label of the active session to the SESSIONS section
	- Update the LESSONS section in `docs/LESSONS.md` as follows:
		- Extract lessons from the current session (problems encountered + solutions + lessons learned, tips for future devs)
	  	- Compare against existing `docs/LESSONS.md` thoroughly to find similar/overlapping lessons
		- Consolidate intelligently:
			- If a new lesson is similar to an existing one → merge/enhance the existing lesson with new details
			- If a new lesson is completely unique → add it to the appropriate category
			- IMPORTANT: Don't just append new lessons - actually read and compare to avoid duplication
		- Replace the LESSONS section with the consolidated version

5. Note updates to `docs/README.md` as follows:
	- IMPORTANT: the readme file should be a reference style document. the purpose of the readme will be to orient anyone working on the project to quickly find the info they need. the readme file should only act as a pointer to all the info that is available in documentation. the readme file should be complete enough that anyone who wants to work on the project should be able to find the jumping off points in the file. 	
	- Check if `docs/README.md` exists
	- If the readme file does not exist:
		- read through all the documents in `docs/` and all subfolders
		- create `docs/README.md` to reference all the documents you read
		- ensure that you stick to the purpose of the readme
	- If the readme file already exists:
		- Update intelligently:
			- check if there are any new or updated files under `docs/`
			- if there are changes:
				- find the relevant section and update it with the changes if the section exists
				- if a relevant section does not exist, create one and update it with the changes
		- ensure that you stick to the purpose of the readme

6. Empty the `.claude/.sessions/.current-session` file (don't remove it, just clear its contents)
7. Inform user the session has been documented

The summary should be thorough enough that another developer (or AI) can understand everything that happened without reading the entire session.

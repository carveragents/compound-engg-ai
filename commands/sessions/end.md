---
allowed-tools: Read, Write, Edit, Grep, Bash(echo:*), Bash(mkdir -p:*)
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
   - Lessons learned
   - What wasn't completed
   - Tips for future developers

4. Note the learnings from this sessions as follows:
	- Check if `docs/LESSONS.md` exists
	- If the file does not exist, create it and add two empty sections to it
		- SESSIONS
		- LESSONS
	- Append the label of the active session to the SESSIONS section
	- Use the following to generate a comprehensive lessons-learned summary for the work done in this session:
		* "Problems encountered and solutions" section from the session summary
		* "Lessons learned" section from the session summary
		* existing contents of `docs/LESSONS.md`
	- Your new lessons-learned summary should include all problems encountered, how you solved them, and what lessons were learned, but don't duplicate lessons or information.
	- Replace the contents of the `docs/LESSONS.md` section with the new lessons-learned summary

5. Note updates to `docs/README.md`:
	- Check if `docs/README.md` exists
	- If the readme file does not exist:
		- read through all the documents in `docs/` and all subfolders
		- create `docs/README.md` to reference all the documents you read
		- the purpose of the readme will be to orient anyone working on the project to quickly find the info they need
		- the readme  file should only act as a pointer to all the info that is available in our documentation
  		- DO NOT replicate any info from the docs, the readme file should be a reference style document
  		- the readme file should be complete enough that anyone who wants to work on the project should be able to find the jumping off points in the file.
	- If the readme file already exists:
		- check if there are any new or updated files under `docs/`
		- if there are changes, update `docs/README.md` with these changes
		- ensure that you stick to the purpose of the readme

6. Empty the `.claude/.sessions/.current-session` file (don't remove it, just clear its contents)
7. Inform user the session has been documented

The summary should be thorough enough that another developer (or AI) can understand everything that happened without reading the entire session.

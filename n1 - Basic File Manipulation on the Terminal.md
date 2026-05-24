```markdown
# Basic File Manipulation on the Terminal - Bash Scripting Course (Part 3)

**Video:** [Basic File Manipulation on the Terminal](https://youtu.be/tKlRZbhXP4E)  
**Instructor:** Dave Eddy (ysap.sh / You Suck at Programming)  
**Part of:** The Complete Bash Scripting Course

## Overview

This section introduces fundamental terminal commands for creating, renaming/moving, and deleting files. It emphasizes the **power** (and danger) of these commands compared to graphical file managers like Finder, highlighting the lack of guardrails and trash/recovery options in the terminal.

## Key Commands Demonstrated

### 1. `touch` - Create New (Empty) Files
```bash
touch lesson1.ext
touch lesson2.ext
touch lesson3.ext
touch lesson4.ext
```
- Creates blank files or updates timestamps of existing ones.
- Used to quickly generate example files.

### 2. `mv` - Move or Rename Files
```bash
mv lesson44.ext lesson4.ext          # Rename
mv lesson4.ext lesson34.ext          # Another rename
```
- **No dedicated `rename` command** — `mv` (move) handles renaming by specifying source and target name in the same directory.
- **Critical Warning:** `mv` will **silently overwrite** existing files without confirmation.
  - Example: `mv lesson4.ext lesson3.ext` deletes the original `lesson3.ext` permanently.
- Think of it as "moving the content" to a new name/location.

### 3. `rm` - Remove (Delete) Files
```bash
rm lesson*.ext                       # Delete using wildcard (glob)
rm -i lesson*                        # Interactive mode (prompts for confirmation)
```
- Extremely fast and powerful — no trash/recycle bin.
- **Wildcard/Glob (`*`)**: Matches patterns (e.g., `lesson*.ext` deletes all matching files).
- **`-i` flag (interactive)**: Prompts `y/n` for each file — safer for beginners.

**Safety Tip:** Many users create an alias:
```bash
alias rm='rm -i'
```
This makes `rm` always prompt by default (until the alias is removed or shell restarted).

## Important Warnings & Best Practices

- **No Undo:** Deleted or overwritten files are **gone** (unless using version control like Git or backups).
- **Powerful but Dangerous:** Terminal commands assume you know what you're doing — no friendly error dialogs like in Finder.
- **Globbing (`*`)** is very powerful and can affect many files at once. Use carefully.
- **History Navigation:**
  - `↑` / `↓` arrows: Scroll through previous commands.
  - `history` command: View full command history.
- **Clear Screen:** `clear` or `Ctrl + L`.

## Additional Terminal Tips Shown

- Command history is persistent across sessions.
- Aliases can customize command behavior (more covered in later chapters).
- Always double-check before running `rm` or `mv` with wildcards.

## Context in the Course

This is early in the "Terminal and Finder" section (around 00:12:22 in the full course). It builds foundational skills before diving deeper into scripting, variables, loops, etc.

---

**Source:** Transcript and content from the video by Dave Eddy.  
**Full Course:** [course.ysap.sh](https://course.ysap.sh/) (free on YouTube)  
**GitHub Materials:** [bahamas10/bash-course](https://github.com/bahamas10/bash-course)

*Be careful out there — with great power comes great responsibility (and potential data loss)!*

---

[[n2 - Hidden Files on the Terminal]]
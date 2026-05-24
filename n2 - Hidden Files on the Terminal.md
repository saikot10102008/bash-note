```markdown
# Hidden Files on the Terminal - Bash Scripting Course (Part 4)

**Video:** [Hidden Files on the terminal](https://youtu.be/EAZqEAjXRp8)  
**Instructor:** Dave Eddy (You Suck at Programming)  
**Part of:** The Complete Bash Scripting Course

## Overview

This lesson explains the Unix/Linux/macOS convention for **hidden files** and introduces several essential terminal navigation and productivity features.

## Main Concepts

### 1. Hidden Files
- On Unix-like systems (macOS, Linux, etc.), any file or directory whose name **starts with a dot (`.`)** is considered hidden.
- Example:
  ```bash
  touch file.ext          # Visible file
  touch .dotfile.ext      # Hidden file
  ```

- **Finder** (macOS) does **not** show hidden files by default.
- `ls` also hides them by default.

### 2. Showing Hidden Files
```bash
ls -a          # Show all files (including hidden)
ls -la         # Long format + all files (most common)
```

**Key items you’ll always see with `ls -a`:**
- `.`     → Current directory
- `..`    → Parent directory
- `.DS_Store` → macOS-specific metadata file (often annoying)

### 3. Special Directory Shortcuts

| Shortcut | Meaning                  | Example |
|----------|--------------------------|---------|
| `.`      | Current directory        | `cd .` (does nothing) |
| `..`     | Parent directory         | `cd ..` |
| `-`      | Previous directory       | `cd -` |

**Demo in video:**
```bash
cd ..                  # Go up one level
cd -                   # Return to previous directory (very useful!)
```

### 4. Tab Completion (Tab Auto-complete)
One of the most powerful features of the terminal:

- Start typing a filename/command and press **Tab**.
- Bash tries to complete it automatically.
- If multiple matches exist, it will:
  - Show a list of possibilities
  - Or beep (make a sound) to indicate ambiguity

**Example:**
```bash
rm .DS<Tab>            # Completes to .DS_Store
rm f<Tab>              # If ambiguous → shows options
```

## Commands Demonstrated

- `touch` — create files (visible and hidden)
- `ls -a` — list all files
- `cd .` / `cd ..` / `cd -`
- `rm` — remove files
- Tab completion

## Best Practices & Tips

- Use `ls -a` or `ls -la` regularly when exploring directories.
- `.DS_Store` files are safe to delete on macOS but often reappear.
- `cd -` is extremely handy for jumping between two directories.
- Tab completion saves massive amounts of typing and reduces errors.
- Hidden files are commonly used for configuration (`.bashrc`, `.git/`, `.env`, etc.).

## Context in the Course

This is Part 4 of the early "Terminal and Finder" section. It builds on previous lessons about file creation, `mv`, and `rm`.

---

**Source:** Video by Dave Eddy (You Suck at Programming)  
**Full Course:** [course.ysap.sh](https://course.ysap.sh/)  
**Playlist:** [Complete Bash Scripting Course](https://www.youtube.com/playlist?list=PL-my9REMIFtGgiQAXqKPJ5UrLdSkxcLBT)

*Master these fundamentals — they will save you hours as you progress into real scripting!*

---

[[n3 - File Handling and Advanced Text Searching]]
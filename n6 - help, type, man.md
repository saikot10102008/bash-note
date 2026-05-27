## Manual Pages (man)

```bash
man ls
```
Displays the manual page for the `ls` command. Manual pages are the built-in documentation system, showing syntax, options, and descriptions.

```bash
man man
```
The manual page *about* the manual system itself. Shows how man pages are organized into sections (1-9) and how to navigate them.

```bash
man 1 cp
```
Explicitly opens section 1 (User Commands) of the `cp` manual. Useful when a term exists in multiple sections.

```bash
man printf
```
Shows the shell command version of `printf` (section 1 by default).

```bash
man 3 printf
```
Opens section 3 (Library Functions) – the C programming version of `printf`. This demonstrates why sections matter: same name, completely different content.

---

## Shell History

```bash
history
```
Lists your previously executed commands with line numbers. Stored in `~/.bash_history`.

```bash
man history
```
Shows the manual for the `history` *library functions* (C programming), not the shell builtin.

```bash
help history
```
Shows documentation for the *shell builtin* `history` command – this is the one you actually use in bash. The `help` command is specifically for bash builtins.

---

## Command Location & Identification

```bash
which ls
```
Shows the full path of the executable that runs when you type `ls`. Returns something like `/bin/ls` or `/usr/bin/ls`.

```bash
/bin/ls
```
Runs the `ls` program directly using its absolute path, bypassing any aliases or PATH search.

```bash
which history
```
Returns nothing (or an error) because `history` is a **shell builtin**, not an external executable on disk. `which` only finds executables in PATH.

```bash
type ls
```
Tells you *how* the shell interprets the command `ls`. Might say "ls is aliased to `ls --color=auto`" or "ls is /bin/ls". More informative than `which`.

```bash
type -a ls
```
Shows **all** known locations/interpretations for `ls` in order of precedence (aliases first, then functions, then external commands).

---

## Echo & Quoting

```bash
man echo
```
Manual page for the external `echo` command (usually `/bin/echo`).

```bash
echo -e 'hello'
```
Enables interpretation of backslash escapes. With just `'hello'`, there are no escape sequences to interpret, so it simply prints `hello`. More interesting with `echo -e 'hello\nworld'` which would add a newline.

```bash
type echo
```
Shows how `echo` is resolved – usually reports it as a shell builtin (which takes priority over the external `/bin/echo`).

```bash
type -a echo
```
Shows all forms: the builtin version *and* the external executable at `/bin/echo`.

---

## The help Command

```bash
help echo
```
Shows bash's builtin documentation for the `echo` builtin – this is what you actually use when typing `echo` in bash.

```bash
help help
```
Shows help about the `help` command itself. Meta!

```bash
help -m echo
```
Displays help for `echo` in **pseudo-manpage format** (structured like a traditional man page with NAME, SYNOPSIS, DESCRIPTION, etc.).

```bash
help -m echo | less
```
Same output, but piped through `less` for scrollable viewing. Useful for long help output that scrolls off-screen.

---

## Command Types

```bash
type history
```
Shows that `history` is a **shell builtin** – it's part of bash itself, not a separate program.

```bash
type -a kill
```
Shows that `kill` exists as both a **shell builtin** and as an external executable (`/bin/kill`). The builtin version runs by default.

---

## Command Completion Exploration

```bash
compgen -b
```
Lists **all shell builtin commands** available in your current bash session. `compgen` generates possible completions; the `-b` flag specifies builtins.

```bash
compgen -b | grep k
```
Filters the builtin list to show only builtins containing the letter "k" (e.g., `kill`, `break`, `trap`).

```bash
compgen -b | grep k | less
```
Same filtering, but displayed in the `less` pager for easy scrolling.

```bash
compgen -b > builtins.txt
```
Redirects the list of all builtins into a file called `builtins.txt` instead of displaying on screen.

```bash
cat builtins.txt
```
Displays the contents of the file you just created.

---

## Combining Concepts

```bash
history | grep less
```
Searches your command history for any commands containing "less" – practical way to recall previous `less` usages.

```bash
history | grep less | less
```
Same search, but displayed in `less` itself for comfortable browsing of results. A nice meta-moment: using `less` to view history of `less` usage.

---

## Key Concepts Illustrated

| Concept | Commands |
|---|---|
| **Builtin vs External** | `which` only finds executables; `help` documents builtins; `type` shows both |
| **Man sections** | Section 1 = user commands, section 3 = library functions |
| **Command resolution order** | aliases → functions → builtins → PATH executables |
| **Piping** | `|` sends output between commands; `>` redirects to files |
| **Exploration tools** | `compgen` for completions, `history` for recall, `type` for identification |


---
---

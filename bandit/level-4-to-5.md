# Bandit: Level 4 → Level 5

## Goal
Log in as bandit4 and find the password needed to access level 5.
This level has multiple files, but only one is a genuine text file
containing the password — the rest are decoys.

## Approach
Ran `ls` and found a directory called `inhere`. Inside, `ls` showed
ten files named `file00` through `file09`. Checking each one
individually with `cat` would work but is slow and messy, especially
since some of them likely contain binary/non-text data that would
print garbage to the terminal.

Instead, used the `file` command, which inspects a file's actual
content (not just its name or extension) and reports its type —
e.g. "ASCII text" vs "data" or other binary formats. Running it
against all ten files at once made it easy to spot which one was
plain text.

## Solution
ls
cd inhere
file ./file*
cat ./file0X # (whichever one was reported as ASCII text)


## What I learned
Learned that filenames and extensions can't be trusted to reveal
what's actually inside a file — the `file` command reads the actual
content/structure to determine the real type. This is a useful habit
for real investigations too: attackers sometimes disguise files with
misleading names or extensions, so checking actual file type rather
than trusting the name is a basic but important verification step.

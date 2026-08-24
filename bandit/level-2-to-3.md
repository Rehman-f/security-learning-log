# Bandit: Level 2 → Level 3

## Goal
Log in as bandit2 and find the password needed to access level 3.
Like level 1, the password file has an unusual name designed to
trip up standard commands.

## Approach
Ran `ls` and saw a filename that looked like this:
`--spaces in this filename--`

Two problems stood out:
1. The filename starts with two dashes, which `cat` could try to
   interpret as command-line options rather than a filename.
2. The filename contains spaces, which the shell would normally
   treat as separators between multiple arguments rather than one
   single filename.

## Solution
ls
cat "./--spaces in this filename--"


Combining `./` (to force it to be read as a path, not a flag) with
quotation marks (to treat the whole thing, spaces included, as one
argument) solved both problems at once.

## What I learned
Learned that shells treat spaces as argument separators by default,
so any filename with spaces needs to be quoted (or escaped) to be
read correctly as a single argument. Combined with the `./` trick
from the previous level, this reinforced that unusual filenames are
a common way to test whether someone actually understands how the
shell parses commands, rather than just copy-pasting solutions.

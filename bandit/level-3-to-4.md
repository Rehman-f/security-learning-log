# Bandit: Level 3 → Level 4

## Goal
Log in as bandit3 and find the password needed to access level 4.
This level introduces a subdirectory and hidden files.

## Approach
Ran `ls` in the home directory and found a single item: a directory
called `inhere`. Moved into it with `cd inhere` and ran `ls`, but
got no output at all — the directory appeared empty.

This was misleading: by default, `ls` doesn't show "hidden" files
(anything whose name starts with a dot). Running `ls -la` instead
showed all files, including hidden ones, and revealed a file named
`...Hiding-From-You`.

## Solution
ls
cd inhere
ls -la
cat ./...Hiding-From-You


## What I learned
Learned that Linux treats any filename starting with a dot as
"hidden" from default `ls` output, and that `-a` (or `-la` for
long format + all files) is needed to reveal them. This is a common
technique for hiding files in plain sight — not real security, just
obscurity — but it's useful to know since hidden config files and
dotfiles show up constantly in real systems (e.g. `.bashrc`, `.ssh`),
not just in CTF challenges.

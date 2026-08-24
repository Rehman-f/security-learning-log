# Bandit: Level 5 → Level 6

## Goal
Log in as bandit5 and find the password needed to access level 6.
This level has a large directory tree with many nested folders and
files, and the password file has to be found based on specific
properties rather than an obvious name or location.

## Approach
Ran `ls` and found a directory called `inhere`. Inside it were
many subdirectories named `maybehere00` through `maybehere17`,
each likely containing several files. Manually checking every file
in every subdirectory would take too long.

Instead, used the `find` command to search the entire tree at once,
filtering by the three known properties of the target file: it's
exactly 1033 bytes, not executable, and a regular file (not a
directory).

## Solution
ls
cd inhere
find . -size 1033c ! -executable -type f
cat ./maybehere07/.file2


## What I learned
Learned how to use `find` with multiple filters combined (`-size`,
`! -executable`, `-type f`) to search recursively through a large
directory structure instead of manually navigating each folder.
This scales far better than browsing by hand and mirrors real-world
tasks like locating a specific log file or config buried deep in a
filesystem, where you often know a file's characteristics before
you know its exact location.

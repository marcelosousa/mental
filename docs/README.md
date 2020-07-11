Premise
=======

Git was originally developer by Linus to cope with the number of changes in the Linux kernel.

It is a technology to efficiently store and retrieve versions of a directory in a file system.

`The core of git is a simple key-value data store. What this means is that you can insert any kind of content into a Git repository, for which Git will hand you back a unique key you can use later to retrieve that content.`

Git has three types of objects: blobs, commits and tags.

The goal is to find out whether git representation of codebases based on files is the most efficient for both CPU and storage.

Particular questions:

1. Is it an overkill to hash the AST instead of the file contents? To answer this question, I need to understand how the compression mechanism works in git.
The naive version of git will create a new file even if you only touch a single character because it's based on hashing.
Need to revisit (https://git-scm.com/book/en/v2/Git-Internals-Packfiles)


Some useful references to similar projects:

[Historage Project](https://github.com/sh5i/git-stein)
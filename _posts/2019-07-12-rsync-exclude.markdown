---
layout: post
title:  "rsync: Excluding Folders and Directories in File Transfers"
date:   2019-07-12
categories: unix
---

The process of copying files across directories, either remotely or locally, is a common operation for everyday command-line users.

Like `scp`, `rsync` can be used for transferring files from a source to a destination. `rsync` differs from `scp` in the way that it copies files; it is said to be better optimized for backups and syncs and more reliable than `scp` .

Particularly beneficial is the `--exclude` option, which comes in handy for excluding specific files and directories in recursive transfers.

## Example 1: Copying from a Remote Server to a Local Machine

In this example, we are copying files from a remote server to a local folder `copy_TO_folder_local` on a Mac machine.

This command will recursively copy files contained within `/some_remote_folder` on the remote server, **excluding** the folders `Desktop` and `Downloads`, as well as the file `exclude_me.txt`.

```
rsync -r --exclude=Desktop/ --exclude=Downloads/ --exclude=exclude_me.txt ira@remote.server.com:some_remote_folder/* /Users/ira/copy_TO_folder_local
```

## Example 2: Copying Across a Local Machine
In this example, we are copying files across folders located on the local machine.

This command will copy all the content from `copy_FROM_folder_local` to `copy_TO_folder_local`, **excluding** the folders `Desktop` and `Downloads`, as well as the file `exclude_me.txt`.
```
rsync -r --exclude=Desktop/ --exclude=Downloads/ --exclude=exclude_me.txt /Users/ira/copy_FROM_folder_local/* /Users/ira/copy_TO_folder_local
```

Adjust the number of `--exclude` options to match the number of directories and files you want to exclude from the recursive copy.
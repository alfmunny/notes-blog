---
title: Quick Notes
date: 2017-07-21 13:28:35
tags: [notes]
---
## Git

### How to rebase your branch

```
git checkout branchname
git rebase master
```

### Change local user name

```
git config user.name "Your name"
git config user.email "Your email"
```
### Synchronise git branch with master
[Git Forks And Upstreams](https://www.atlassian.com/git/articles/git-forks-and-upstreams)

```
git checkout branchname
# some work and some commits
# some time passes
git fetch upstream
git rebase upstream/master
```

### Sychronise git master

```
git checkout master
git fetch upstream
git merge upstream/master (or git rebase upstream/master)
```

### Delete the commit on remote github

[See here](https://stackoverflow.com/questions/448919/how-can-i-remove-a-commit-on-github)

#### First remove the last commit
git rebase -i HEAD~2 ( Or use the option in IDE )

#### Force push

git push origin +branchname

## Network

### check port being forwarded

netstat -tpln

### ssh without password
ssh-keygen -t rsa(with default config)
sh-copy-id root@172.100.51.192
ssh root@ip.address

## System

### unmount busy device
umount -l /path/to/busy-device

### unmount busy nfs
umount -f /path/to/busy-network-file-system


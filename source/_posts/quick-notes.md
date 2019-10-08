---
title: Quick Notes in Shell
date: 2017-07-21 13:28:35
tags: [notes]
categories: [posts]
toc: true
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
```
git rebase -i HEAD~2 ( Or use the option in IDE )
```

#### Force push

```
git push origin +branchname
```

## Network

### check port being forwarded

```
netstat -tpln
```

### ssh without password
```
ssh-keygen -t rsa(with default config)
ssh-copy-id root@172.100.51.192
ssh root@ip.address
```

### overwatch tcp call
Tool: tcpdump

```
tcpdump -i vmgmt port http and dst www.heise.de
```

### download from remote host

```
scp your_username@remotehost.edu:foobar.txt /local/dir
```

###

## System

### unmount busy device

```
umount -l /path/to/busy-device
```

### unmount busy nfs

```
umount -f /path/to/busy-network-file-system
```

### write random data to file

```
dd if=/dev/urandom of=sample.txt bs=1G count=1
dd if=/dev/urandom of=sample.txt bs=64M count=16
```

### firewall
```
/etc/init.d/firewall start
/etc/init.d/firewall stop
```

## Database

```
show databases;
GRANT ALL ON `DATABASE`.* TO 'user'@'localhost' IDENTIFIED BY 'password';
```

## Vim

### fold and unfold

zr: decrease one fold level
zM: fold all
zm: increase one fold level 
zR: unfold all
zo: open fold at cursor
zO: open all fold at cursor
zj: move to next fold
zk: move to previous fold

### vimgrep in current file

vimgrep /pattern/ %

### vimgrep in current folder

vimgrep /pattern/ *

### quickfix

open: copen
next: cnext
previous: cprev

### current date

:r !date

actually you can always run the shell command in VIM and insert the outputs like this

zsh:1: command not found: data
:r !command

### change to current folder

:cd %:h

%   full path to current path
%:h full path to current file without filename itself

### substitute

:%s/foo/bar/g   find and replace in all line
:s/foo/bar/g    find and replace in current line
:%s/foo/bar/gc    find and replace in current line and ask for confirmation
:%s/foo/bar/gci    find and replace in current line, ask for confirmation, case insensative

### edit command line
:<Ctrl-f> to edit the command line with vim normal mode

q:, q/, q?, edit, search in command line

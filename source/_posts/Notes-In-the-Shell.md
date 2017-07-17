---
title: Notes In the Shell
date: 2017-07-13 13:28:35
tags:
---

## Docker

### installation

[Official Website](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu)


### add docker group

`sudo groupadd docker`

`sudo usermod -aG docker $USER`

Try to run: `docker run hello-world`

### build a image

`docker build -t logsearcherbackend .`

### run a container

`docker run -d -p 2223:2223 logsearcherbackend`


## Mysql

### installation
```
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
systemctl status mysql.service
mysqladmin -p -u root version
```

### commands

```
mysql -u root -p
```

```
mysql> use logsearcher;
mysql> show tables;
```




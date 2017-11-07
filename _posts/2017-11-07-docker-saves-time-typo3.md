---
title: Docker saves time
---

### Install Docker from docker.io

NOT: `sudo apt-get install docker` (its a docking app for the taskbar)

BUT read the docs and install from here:

<https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/>

### get typo3 image

   sudo docker pull martinhelmich/typo3

### run db

on local port `3307`

```
sudo docker run -d --name typo3-db \
    -e MYSQL_ROOT_PASSWORD=password \
    -e MYSQL_USER=typo3 \
    -e MYSQL_PASSWORD=password \
    -e MYSQL_DATABASE=typo3 \
    -p 3307:3306 \
  mariadb:latest \
    --character-set-server=utf8 \
    --collation-server=utf8_unicode_ci
```
    
check db connection:

`mycli -P 3307 -u typo3 -p password typo3`
   
### run server with typo3

on local port `8080`

```
sudo docker run -d --name typo3-web \
    --link typo3-db:db \
    -p 8080:80 \
  martinhelmich/typo3
```

or without `--link` (obsolete)

```
sudo docker run -d --name typo3-web -p 8080:80 martinhelmich/typo3

sudo docker network create -d bridge --subnet 172.25.0.0/16 isolated_nw
sudo docker network connect isolated_nw typo3-web
sudo docker network connect isolated_nw typo3-db
```

### open in browser

<http://localhost:8080>

and setup typo3:

user: typo3
password: password
port: 3306
host: db

when using without `--link` (obsolete) use db-host from `docker network inspect isolated_nw`.

### notice

list running docker containers: `sudo docker ps`
get another version: use `martinhelmich/typo3:7`
stop container: `sudo docker stop typo3-db`
remove container: `sudo docker rm typo3-db`
`--link` parameter is depracted, so not used here
`docker network inspect isolated_nw` list devices in network
`sudo docker exec -it typo3-web bash` works only on running container

### Sources:

* <https://www.martin-helmich.de/de/blog/typo3-cms-docker.html>
* <https://wiki.typo3.org/TYPO3-Docker>
* <https://docs.docker.com/engine/userguide/networking/work-with-networks/#connect-containers>
* <https://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/>

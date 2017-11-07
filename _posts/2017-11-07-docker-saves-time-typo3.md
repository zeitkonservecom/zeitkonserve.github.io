---
title: Docker saves time
---

1. Install Docker from docker.io

NOT: `sudo apt-get install docker` (its a docking app for the taskbar)

BUT read the docs and install from here:

https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/

2. get typo3 image

sudo docker pull martinhelmich/typo3

3. run db

´´´
docker run -d --name typo3-db \
    -e MYSQL_ROOT_PASSWORD=password \
    -e MYSQL_USER=typo3 \
    -e MYSQL_PASSWORD=password \
    -e MYSQL_DATABASE=typo3 \
  mariadb:latest \
    --character-set-server=utf8 \
    --collation-server=utf8_unicode_ci
´´´
    
4. run server with typo3

on local port 8080

´´´
sudo docker run -d --name typo3-web \
    --link typo3-db:db \
    -p 8080:80 \
  martinhelmich/typo3
´´´

5. list running docker images

sudo docker ps

6. notice

get another version: use `martinhelmich/typo3:7`

Sources:

https://www.martin-helmich.de/de/blog/typo3-cms-docker.html
https://wiki.typo3.org/TYPO3-Docker

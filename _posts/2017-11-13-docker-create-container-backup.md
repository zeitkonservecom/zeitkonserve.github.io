```
sudo docker ps
CONTAINER ID        IMAGE                    COMMAND                  CREATED             STATUS                   PORTS                                NAMES
2a39af91fff0        martinhelmich/typo3:7    "docker-php-entryp..."   4 minutes ago       Up 4 minutes             0.0.0.0:9157->80/tcp                 typo3-web157
1a263bcf46a8        mysql/mysql-server:5.7   "/entrypoint.sh --..."   4 minutes ago       Up 4 minutes (healthy)   33060/tcp, 0.0.0.0:4157->3306/tcp    typo3-db157

sudo docker commit -p 2a39af91fff0 backup01
sha256:807cf5412fc37e7cd106ad724fe8f14a0b9fb365995f41073fb2aa8c9e70f133

sudo docker save -o /tmp/backup01.tar backup01
ls -l -h /tmp/backup01.tar 
-rw------- 1 root root 497M Nov 13 15:17 /tmp/backup01.tar
```

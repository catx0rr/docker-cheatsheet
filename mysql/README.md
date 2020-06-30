# Docker for mysql
---

### Commands
```
docker pull mysql/mysql-server:latest

docker run --name mysqltest -d mysql/mysql-server:latest

docker logs mysqltest 2>&1 | grep -i generated

docker exec -it mysqltest mysql -u root -p  

ALTER USER 'root'@'localhost' IDENTIFIED BY '[password]';

```

[link](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/docker-mysql-getting-started.html)



# Docker Apache+MariaDB+PHP Dev Env
自用配置，为 `php:8.5-apache` + `mariadb:lts`，加个 `phpmyadmin:latest`。

快速使用：
```bash
# 复制一份配置
mv .env.example .env
# Docker，启动！
docker compose up -d
# 更新镜像
docker compose pull
# 重新构建 PHP 的镜像
docker compose build
```

HTTP 的默认端口为 `8080/8443`，MariaDB 的为 `33060`，PHPMyAdmin 的为 `8086`，Xdebug 的为 `9003`。

PHP 的默认时区为 `Asia/Shanghai`。

## PHP-Apache
具体配置基本在 `./dockerfile` 里了，使用 `8.5`，安装 `composer`，默认使用 `php.ini-development` 配置。

PHP 安装的扩展：

- mysqli
- pdo
- pdo_mysql
- zip
- mbstring
- gd
- fileinfo
- exif
- imagick
- xdebug

进 Docker 系统的 bash：

```bash
docker compose exec www bash
```

## MariaDB
用的 LTS 线，简单配置了一些，应该可以直接用了。

## PHPMyAdmin
搬来就用，没啥要改的。喜欢用客户端的话可以试试 [HeidiSQL](https://www.heidisql.com/)，用起来还可以。

## 参考文案
- [sprintcube/docker-compose-lamp](https://github.com/sprintcube/docker-compose-lamp)
- [jersonmartinez/docker-lamp](https://github.com/jersonmartinez/docker-lamp)
- [MariaDB 官方 Docker](https://hub.docker.com/_/mariadb)
- [PHP 官方 Docker](https://hub.docker.com/_/php)
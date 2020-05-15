# CH7 SLiMS Library Management

Powered by [SLiMS](https://slims.web.id/web/)(current dependency version is on SLiMS 9 Bulian). Which required the following:
- Apache 2.4
- MySQL 5.5 or MariaDB 10.3
- PHP 7.0
- Database driver(eg. mysqli)
- PHP extensions(eg. gd, gettext, mbstring, YAZ[optional])

And required writable on the following paths:
- config
- files
- images
- repository

## Docker usage
``` bash
$ docker-compose up -d
```
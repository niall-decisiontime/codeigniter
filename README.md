# Basic Docker Web Dev Box

Basic docker box for little projects & tests. I base most of my docker boxes on this one.

##  Requirements

- This repo assumes you store your projects in  `~/Projects`.
- [Docker](https://docs.docker.com/engine/installation/) installed
- [Docker Compose](https://docs.docker.com/compose/install/) installed

## Services

- PHP-FPM 7.1
- MySQL 5.7
- NGINX 1.13

## Accessing services

Access app via `http://localhost:8080/` from your browser and connect to MySQL from your client (eg: [Sequel Pro](https://www.sequelpro.com/)) using `127.0.0.1:3306`.

To access MySQL from within your web applications you'll need to use `mysql` as host.

### Default MySQL credentials:

- **Username**: `docker`
- **Password**: `docker`
- **Database**: `docker`

## Installation / run

```bash
docker-compose up --remove-orphans
```
## Create the sessions table
```sql
CREATE TABLE IF NOT EXISTS `ci_sessions` (
        `id` varchar(128) NOT NULL,
        `ip_address` varchar(45) NOT NULL,
        `timestamp` int(10) unsigned DEFAULT 0 NOT NULL,
        `data` blob NOT NULL,
        KEY `ci_sessions_timestamp` (`timestamp`)
);
```

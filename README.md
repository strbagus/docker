# Docker Config
Container for multiple project with same environtment

## Setup php82
- folder project in `www/`
- add new vhost on `laravel.conf` for that project

### IF
- project not in `www/`. add `/path/to/project:/var/www/html/project-name` in docker compose volumes
- database is in local. use `host.docker.internal` on `DB_HOST` inside .env

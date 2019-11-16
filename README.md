# embulk samples

This repository provides an execution environment and a simple sample of embulk.

## usage

Executing the following command starts the environment.

```
$ docker-compose up -d
```

|container|version|memo|
|---------|-------|----|
|embulk   |-      |embulk execution environment(Java8,embulk,plugins)|
|mysql    |latest |-   |
|postgres |latest |-   |

Executing the following migration files for mysql and postgresql.

* `mysql/migrations/20191116_create_sample_table.sql`
* `postgresql/migrations/20191116_create_sample_table.sql`

Run the following sample command.

``` bash
# in: csv, out: csv
$ docker-compose run embulk run ./embulk/configuers/csv_to_csv_config.yml
# in: csv, out: msql
$ docker-compose run embulk run ./embulk/configuers/csv_to_mysql_config.yml
# in: mysql, out: csv
$ docker-compose run embulk run ./embulk/configuers/mysql_to_csv_config.yml
# in mysql, out: postgresql
$ docker-compose run embulk run ./embulk/configuers/mysql_to_postgres_config.yml
# in postgresql, out: csv
$ docker-compose run embulk run ./embulk/configuers/postgres_to_csv_config.yml
```

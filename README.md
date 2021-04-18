# spring-boot-autoconfig-app
Application which makes use of the pre-packaged, autoconfigured artifact.

## Run Databases

The application makes use of two separate databases.
Leading database is a Postgres 12.4 on Alpine Linux, the second database is MySql 8.0.23.

The databases are prepared in form of the provided `./docker/docker-compose.yml` file.

To run the database switch into the directory containing the file and simply use the command

`docker-compose up -d`

The -d parameter detaches the databases from the terminal.
The script creates two anonymous volumes where the data is stored.

Checking the running instances can be  done with the following command

`docker-compose ps -a`

or as plain docker command with more details

`docker ps -a` or `docker stats`

## Stop Databases

To stop the databases switch into the directory containing the file and simply use the command

`docker-compose down`

The command stops and removes resources of the containers. 

## Manage Docker Volumes

With the commands

`docker volume ls` and `docker volume inspect <VOLUME NAME>`

the volumes can be listed and inspected.

To delete all unused volumes use the command

`docker volume prune`

##  Schema Maintenance

The schema is created/updated by hibernate on application start up. 

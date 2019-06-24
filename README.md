# Gif Browsing APP

## Project setup

After clone this repo you need to initialise the sub repos using `git submodule init` and then `git submodule update`.

### Build image using docker
You can either, use docker-compose or just docker. For docker you can see the readme of the repos.

If you are going to use docker compose, just check the file `docker-compose.yml` and change the enviroment variables
for the right values. Then run
```
docker-compose up
```

#### Updated 24/06/2019

#### Notes for use

Please take in consideration the mysql container takes some time to be ready to use and the backend (api) container executes the database migrations on startup, this situation makes the backend (api) container throw error executing the migrations. It could be fixed just starting the mysql container first and waiting to be ready then executing the backend (api) container. To start the container use the command

```
docker run -d --restart unless-stopped --name mysql --hostname mysql -p 3306:3306 --env MYSQL_ROOT_PASSWORD=mysql_root --env MYSQL_DATABASE=gif_browsing_app_db mysql:5.7.26
```

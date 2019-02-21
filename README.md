# Dineshcloud/github.aksakalli/
TODO Spring Angular
Using JHipster and generator-gulp-angular.

Technologies
Spring Boot
Maven
Spring Security
Spring Security OAuth
Spring MVC REST
Spring Data JPA
PostgreSQL (Production, Development)
H2 Database Engine (Test)
Flyway Database Migration
Docker
Docker Compose
Gulp
AngularJS
...
Deploy
# Build the project
mvn package

# build the images
docker build -t todo-rest todo-rest/.
docker build -t todo-nginx todo-frontend/.

# run the containers
docker run -d --name todo-db -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=todo postgres:9.4.5
docker run -d --name todo-rest --link todo-db:todo-db todo-rest
docker run --name todo-nginx -p 8082:80 --link todo-rest:todo-rest -d todo-nginx

# or just use docker-compose
# for building and running
docker-compose up

# MongoDb composerfile
This mongodb composer file has a configuration of mongo database using docker-compose.yml

```
version: "3.9"

services:
  mongod:
    container_name: mongo1100
    image: mongo
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: test
      MONGO_INITDB_ROOT_PASSWORD: test
    deploy:
      replicas: 1
    volumes:
      - G:\Databasefiles\mongo-database\port1100:/root/data
      - G:\Databasefiles\mongo-database\port1100:/root/logs
      - ./mongod.conf:/etc/mongod.conf    
    ports:
      - 1100:27017

```

## Description
- **container_name:** it is the name of the container
- **image:** it is the image to be pulled from docker-hub
- **restart:** If something goes wrong, the database will restart
- **environment:** Those are the environment variables recognized by mongo configuration. In this section there are the user and password database;
- **deploy:** It contains the replicas configuration according the mongodb rules.
- **volumes:** Those are the local volumes that save the data locally in case the docker container will be deleted.
- **ports:** It represent the local:docker ports.


**SeeYouSoon Coders**

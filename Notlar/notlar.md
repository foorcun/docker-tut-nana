[youtube](https://www.youtube.com/watch?v=3c-iBn73dDE&ab_channel=TechWorldwithNana)

# pull mongoDB and docker express imageleri

```.sh
docker pull mongo
docker pull mongo-express
```

not: mongo-express is a web-based MongoDB admin interface written in Node. js, Express. js, and Bootstrap3.

## check images

```.sh
docker images
```

# Create Network - to connect mongoDB and mongo-express

```.sh
docker network create mongo-network
```

not: docker network create network-name

## Read networks

```.sh
docker network ls
```

# create container with run

```.sh
docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo
```

not: sondaki mongo image-name.

```.sh
docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password -e ME_CONFIG_MONGODB_SERVER=mongodb --net mongo-network --name mongo-express mongo-express
```

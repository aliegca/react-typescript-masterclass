
#####
docker pull mongo
docker pull mongo-express
docker images

# connect 2 container [ docker network ]

 docker network ls

# create network
 docker network create mongo-network

docker run -d -p 27017:27017  --network mongo-network --name mongodb \
    -e MONGO_INITDB_ROOT_USERNAME=mongoadmin \
    -e MONGO_INITDB_ROOT_PASSWORD=secret \
    mongo
##

docker run -d -p 8081:8081 --network mongo-network --name mongo-express \
    -e MONGO_INITDB_ROOT_USERNAME=mongoadmin \
    -e MONGO_INITDB_ROOT_PASSWORD=secret \
    ME_CONFIG_MONGODB_SERVER=mongodb
    mongo-express       

docker logs docker_id     
    

git add .
git commit -m "typescript is jocking here"
git push -u origin main




# deploy to ECR 
create repo on ECR
docker login for the provider 


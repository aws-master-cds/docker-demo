05 May 2024 (Sunday) 

---
app (web-api = REST API)
  - javascript (programming language) - node (runtime) - express (library/module)
  
dockerize - Dockerfile
docker build 
upload image to docker registry (docker hub) - pre-req (have an account in docker hub)

sign-up at postman (browser or download gui client)
  - to test/invoke the rest-api (web-api)

---
local machine (windows machine) - getting docker-setup is bit messy (docker desktop - licensing (free))

vs

ec2 on aws (amazon linx 2023 OS) - No gui editor - No - painful command-line - no multi-window

vs

aws cloud9 (browser based)  -- tick tick
 - ec2 - IDE 
 - security groups of ec2
 - public ip of ec2
 - docker (pre-installed)
 
---
mongo

existing db image - docker hub

1. pull that image
2. inspect the image and know the volume details, port details


container - exposing the localhost 27017


docker network create fav-network

docker run -v mongodb:/data/db -v mongo-configdb:/data/configdb --network fav-network --name mongodb --rm -d mongo

---
developer code

machine node applic (3000, 


dockerize - Dockerfile
docker build -t fav-api .

local docker image 
push to remote

docker run --name fav-api -p 3000:3000 --network fav-network --rm -d fav-api



---



two apps (to demo the docker networks)

multi-container = 2 container app

one container    - api-service (REST API express)
second container - db (mongodb - already available image)
---
it 1

as two containers 
 - connect them 
 - test
---
it 2 

use docker-compose to run the 2-container setup
test it



---
to delete unused docker objects

docker container prune
docker image prune
docker volume prune

docker image inspect mongo
docker image history mongo

--
docker hub info
github info
docker pull mongo
docker image inspect mongo # exposed port, volumes
docker image history mongo # exposed port, volumes

---
docker run -p 27017:27017 -v mongodb:/data/db -v mongo-configdb:/data/configdb --rm -d --name mongodb mongo

---
docker-compose top
docker-compose stats
docker-compose up -d   # runs the containers in the detached mode
docker-compose down 
docker-compose down -v # removes the volumes
docker-compose logs    # services/containers logs

---
docker container inspect <container-name>
docker volume inspect <volume-name>
docker image inspect <image-name>
docker network inspect <network-name>

--
docker-hub 
 - signup, create a public repository (signup with google account aws.master.cds@gmail.com, no new password)
 - security > create token

docker login 
docker tag <local-tag> <remote-tag> # docker tag fav-api awsmastercds/fav-api
docker push awsmastercds/fav-api

---
github 
  - signup (used aws.master.cds@gmail.com for signup, new password)
  - create public repository
  - profile > settings > developer settings > classic token

git init # add .gitignore file
git remote add origin https://github.com/aws-master-cds/docker-demo.git
git branch -M main
git add .
git commit -m "docker, dockerfile, docker-compose demo - MERN app"
git push --set-upstream origin main
git push

---
postman 
 - signup with aws.master.cds@gmail.com google account, no new password

--

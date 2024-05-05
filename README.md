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

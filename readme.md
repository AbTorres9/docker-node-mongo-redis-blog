https://hackmd.io/LLmIjrQBSHW_hw-0wBIt5A

docker image ls = shows images

docker run -d --name <conatiner-name> <image-name> = to run a image and name its container as well

docker rm <container-name> -f = forces container to kill even before stopping it

docker run -v <path of folder in computer>:<path of workdir in container> -d --name <conatiner-name> <image-name> = to run a image and name its container as well and with a bind volume so that whenever ther is a change the container detects it as well

ADD :ro after <path of workdir in container> so that this bind mount is read only otherwise if there is a new file created in container the same file will get created in our local machine as well.
eg docker run -v %cd%:/app:ro -p 3000:3000 -d --name node-docker-fcc nodedockerfcc

docker compose up -d --build = this forces docker compose to build a new changes and check for any changes make in the project because by default docker compose looks for the image name and it doesnt build the image every time.

docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d = order is imp if you want to run main docker file then in dev env or in prod env so add mail yml file then chain it with prod or dev yml file according to condition.

docker inspect <container name/id> = to get any info about the container like ip address etc

docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d --scale node-app=2 = This way we can scale any container to desired quantity like here we have increased node app container to 2 quantity

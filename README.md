# docker cheatsheet
---

## Connect to X11 socket spawn gui applications from container to host
---

mount: -v /tmp/.X11-unix:/tmp/.X11-unix/:ro

## Connect Sound to container to spawn sound from container to host

mount: -v /dev/snd:/dev/snd


### Using docker build
---
docker build -t test-ubuntu .

docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix test-ubuntu bash

docker images -f dangling=true | xargs docker rmi -f

docker run --rm -it -v /tmp/.X11-unix:/tmp/.X11-unix/:ro -e DISPLAY=:0 ubuntu bash


### Using docker pull
---
docker pull ubuntu:18.04
docker pull ubuntu:latest

docker run -ti -d --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix/:/tmp/.X11-unix/:ro --name nameuwant ubuntu:18.04
docker exec nameuwant useradd -m -s /bin/bash username
docker exec --user root nameuwant apt-get update && apt-get install wireshark
docker exec --user username nameuwant wireshark &

#### Connect to container
docker exec -ti nameuwant bash | sh | /bin/bash 


### Docker process / container
---
docker ps -a

docker ps -f status=running

docker ps -f status=exited

docker ps -aq | xargs docker rm -f


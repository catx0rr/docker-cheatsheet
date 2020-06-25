# docker cheatsheet
---

### Connect to X11 socket
---
docker build -t test-ubuntu .
docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix test-ubuntu bash
docker images -f dangling=true | xargs docker rmi -f


docker run --rm -it -v /tmp/.X11-unix:/tmp/.X11-unix/:ro -e DISPLAY=:0 ubuntu bash

docker ps -a
docker ps -f status=running
docker ps -f status=exited

docker ps -aq | xargs docker rm -f


# Docker for sqlite3
---

### Commands
```
docker pull ubuntu:latest

docker build -t ubuntu:sqlite3 .

docker run -ti -d -e DISPLAY=$DISPLAY -v /path/to/sqlite3/dir/:/database/ -v /tmp/.X11-unix/:/tmp/.X11-unix/:ro --name sqlite3 ubuntu:sqlite3

docker exec -ti sqlite3 /bin/bash

```

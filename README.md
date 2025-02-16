# firefox
Docker container for Firefox⁠

## Quick Start:


```bash
docker run -d \
    --name=firefox \
    -p 5000:5800 \
    -v /docker/appdata/firefox:/config:rw \
    shipanjodder/firefox
```
<hr>

## With Docker Compose:
create a file nammed `docker-compose.yml`

``` js title="docker-compose.yml"
services:
  firefox:
    build: .
    image: shipanjodder/firefox:latest
    container_name: firefox
    environment:
      - DISPLAY_WIDTH=1920
      - DISPLAY_HEIGHT=1080
      - SECURE_CONNECTION=1
      - TZ=Asia/Dhaka
    ports:
      - "5000:5800"
    volumes:
      - ./firefox-profile:/config:rw
      - ./downloads:/downloads:rw
    restart: unless-stopped
    shm_size: 2g
```

run, `docker compose up --build -d`

<br>

Browse locally: [http://localhost:5000/](http://localhost:5000/)

Docker Repository: [Docker hub](https://hub.docker.com/r/shipanjodder/firefox/)


![icon](https://raw.githubusercontent.com/Shipan-Jodder/firefox/refs/heads/main/firefox-icon.png) ![text](https://raw.githubusercontent.com/Shipan-Jodder/firefox/740e6955f3d8640830526f63031d343394a42a38/firefox-text.svg)
# Docker container for Firefox⁠

### Quick Start:


```bash
docker run -d \
    --name=firefox \
    -p 5000:5800 \
    -v /docker/appdata/firefox:/config:rw \
    shipanjodder/firefox
```
<hr>

### With Docker Compose:
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


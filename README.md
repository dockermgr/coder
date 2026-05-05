## 👋 Welcome to coder 🚀  

coder README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update coder
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/coder/volumes"
git clone "https://github.com/dockermgr/coder" "$HOME/.local/share/CasjaysDev/dockermgr/coder"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/coder/volumes/." "$HOME/.local/share/srv/docker/coder/volumes/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-coder \
--hostname coder \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-coder/volumes/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-coder/volumes/config:/config:z" \
-p 80:80 \
casjaysdevdocker/coder:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/coder
    container_name: casjaysdevdocker-coder
    environment:
      - TZ=America/New_York
      - HOSTNAME=coder
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-coder/volumes/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-coder/volumes/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/coder
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/coder" "$HOME/Projects/github/casjaysdevdocker/coder"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/coder"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  

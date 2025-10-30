# steps to setup

Use docker-compose.yml to deploy registry pull-through cache container at main Portainer server

## docker engine configuration steps

.docker/buildx/buildkitd.default.toml
Replace SERVERIP with the IP where the registry container will be deployed

place the file in any user location that will be executing build commands
examples:
/root/.docker/buildx/
/home/user/.docker/buildx

## daemon.json & registry configurations

/etc/docker/daemon.json
Replace SERVERIP with the IP where registry container will be deployed

place the updated file on any device in the /etc/docker folder that needs to use the pull through cache - even local docker engine of Portainer server

create /etc/docker/registry folder if it is not already present
update both config.json & config.yml files with the dockerhub username/password to be used under the proxy section

place both updated files on any device in the /etc/docker/registry folder that needs to use the pull through cache - even local docker engine of Portainer server

restart docker engine or restart device

## Portainer/docker compose deployment

enter username & password under proxy section of yaml

deploy yaml onto Portainer server

functionality can be verified by viewing registry logs during an image pull

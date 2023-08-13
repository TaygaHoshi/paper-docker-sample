# paper-docker-sample
This is a docker sample for a papermc server.

# Starting the Server
First, make sure you read Minecraft EULA. You can then download the docker-compose.yml file into a folder called "paper-docker-sample". Then follow these steps:

```bash
cd paper-docker-sample
mkdir -p server-data
sudo chown -R root:root server-data
sudo chmod -R 744 server-data
docker compose up -d # or docker-compose up -d
```

The server will be up in "localhost:25565".

# Configuring the Server
Using server shell:
```bash
docker attach paper
# to leave, ctrl+p > ctrl+q
```

Configuring server.properties and other files:
```bash
# stop the containers
docker compose stop # or docker-compose stop

# then you can edit files
sudo vim ./server-data/server.properties

# start the containers
docker compose start # or docker-compose start
```

To add plugins:
```bash
docker compose stop # or docker-compose stop
sudo mv /path/to/plugin/plugin.jar ./server-data/plugins/
docker compose start # or docker-compose start
```

# Inner Range Inception to MQTT
A docker container to interface Inner Range Inception with MQTT to be used with home automation like Home Assistant

## Setup Steps
1. Create a [MQTT server](https://hub.docker.com/_/eclipse-mosquitto)
2. Setup config file `configuration.yml` in `/config` directory (example below)
3. Setup docker compose file (example below)
4. Enable Home Assistant MQTT discovery if integrating with Home Assistant (optional): https://www.home-assistant.io/docs/mqtt/discovery/
5. Run the app by running `docker-compose up --build`

## Example Docker Compose File
```
version: '3'
services:
  dynalite:
    container_name: inception-mqtt
    image: matthewlarner/inception-mqtt:latest
    volumes:
      - ./config:/usr/src/app/config
    environment:
      - TZ=Australia/Sydney
    restart: always
```

## Example Config

Refer to https://github.com/matthew-larner/inception-mqtt/blob/main/configuration.yml.example

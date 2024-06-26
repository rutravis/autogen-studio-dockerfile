# Autogen Studio Docker Image

This repository contains a dockerfile which can be used to build a docker image for the Autogen Studio. The docker image can be used to run the Autogen Studio in a docker container.

## Building the docker image

To build the docker image, run the following command in the root of this repository:

```bash
docker build -t autogen-studio:latest .
```

## Running the docker image

To run the docker image, run the following command:

```bash
docker run -it --rm -p 8081:8081 autogen-studio:latest -e "OPENAI_API_KEY=your_openai_api_key"
```

The Autogen Studio will be available at http://localhost:8081.

## Runnin in Docker compose

Here is an example of a docker-compose.yaml file to load the container.

```version: "3"
services:
  autogen-studio:
    image: autogen-studio:latest
    restart: unless-stopped
    environment:
      - OPENAI_API_KEY="insert OpenAI key here"
    volumes:
      - ./data:/app/.autogenstudio
    ports:
      - 8081:8081
```

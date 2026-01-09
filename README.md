# Self-hosted AI Chat

Self host ai fast with this complete docker set up.

## How to begin

install docker if not already [docker](https://docs.docker.com/engine/install/) or [docker desktop *recommended*](https://www.docker.com/get-started/)

Start docker if not already (docker desktop likes to open it in the background, if you want to see the window find and click on the docker logo in your taskbar (mac/linux top bar, windows arrow on the bottom bar near the wifi symbol))

Download the three .yml files put them in a folder that you can find

Open a terminal/command promt and navigate to the folder with the files by typing `cd <path to the folder, copy it from finder or file explorer if needed>` press enter

now choose your set up:


### Start app with no GPU
```
docker compose up -d
```

### Start app with GPU enabled (nvidia)
```
docker compose -f enable-gpu.yml up -d
```

### Start app with image gen enabled (REQUIRES GPU)
```
docker compose -f docker-compose.yml -f enable-image-gen.yml up -d
```
*Note this doesn't enable gpu for ollama or open-webui only enables image gen with gpu you will need to use `-f enable-gpu.yml` instead of `docker-compose.yml` to enable gpu on ollama or open-webui.*

copy the command you want and press enter when ready. docker will pull all of the images it is roughly 8-15 GB so it may take a few minutes.

once `open-webui` is running you may go to [http://localhost:3000](http://localhost:3000) if you changed the port for `OPENWEBUI` inside of the .env file you will need to visit `http://localhost:{your_port}`

## Why choose this

This stack uses docker compose which lets users add new services without having to create seperate contaners. This makes it easier for somone to start their services in order all at once, and even stop them at once. Docker also is a containerized machine alike a Virtual Machine (VM); this let you delicate dedicated or dynamic amount of resources like ram cpu and storage; it also means you are not running this directly on your machine so if any issues arise you stop the container and the rest of your machine stays uneffected. 

## About the services used

### What is Open-WebUI

User-friendly AI Interface (Supports Ollama, OpenAI API, ...) from [Open-WebUI](https://github.com/open-webui/open-webui)

### What is Ollama

Ollama floating on a cloud · Cloud models are now available in Ollama. Chat & build with open models. Download Explore models. from [Ollama](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://ollama.com/&ved=2ahUKEwjNiMKwhP2RAxV6EFkFHdEvKY8QFnoECAwQAQ&usg=AOvVaw17WonOj_dIOYJACdXhdC2W)

### What is Comfyui

The most powerful and modular diffusion model GUI, api and backend with a graph/nodes interface. from []()

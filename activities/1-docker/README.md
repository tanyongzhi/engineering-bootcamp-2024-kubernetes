# Introduction to Docker
Docker is a popular platform to build containerised applications. Here is a guide that will walk you through some of the basics of Docker.

## Demo
We will be building a Docker image and running it in this demo. Here are some common commands that might be useful:
- building an image with a tag: `docker build <image name> -t <tag name>`
- running an image: `docker run <image name>`
- pushing to docker hub: `docker push <image name>`

## Challenge
Try to:
- Authenticate your Docker CLI with Docker hub by running `docker login`
- Containerise your Express app by writing a Dockerfile and building it into a Docker image. You can find a sample Node.JS dockerfile online and modify it for your own use. Use the image name `<your Docker hub account name>/engineeringbootcamp2024`
- Try running the Docker image, you might need to use the flag `-p 8080:8080` to map the container ports to the host ports
- Try sending requests to your running Docker container to test if it's working!
- Once done, push the image to Docker hub
# Nginx Configuration with Docker

This repository contains an Nginx configuration file and a Dockerfile to build a Docker image with the custom Nginx configuration.

## Nginx Configuration

The Nginx configuration file `nginx.conf` is located in the root directory of this repository. It defines a basic Nginx server that listens on port 8080.

### Endpoints

- `/`: Returns a "Hello, World!" message.
- `/unhealthy`: Returns a 503 status code indicating the service is unhealthy.

## Docker Image

The Docker image is built using the provided Dockerfile, which copies the `nginx.conf` file into the appropriate location in the Nginx container.

To build the Docker image, run the following command in the root directory of this repository:

```
docker build -t nginx-configured .
```

Once the image is built successfully, you can run a container based on the image with the following command:

```
docker run -d -p 8080:8080 nginx-configured
```

The Nginx container will be running, exposing port 8080 on the local machine.

## Accessing the Endpoints

You can access the endpoints using a web browser or tools like cURL or Postman:

- Root endpoint: [http://localhost:8080/](http://localhost:8080/)
- Unhealthy endpoint: [http://localhost:8080/unhealthy](http://localhost:8080/unhealthy)

Replace `localhost` with the appropriate host or IP if running on a remote server.

That's it! You now have an Nginx server running with the custom configuration, serving the defined endpoints.
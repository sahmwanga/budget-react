## Starting service

## Development Environemt

file used: `Dockerfile.dev`

- replace `<docker-id>` with your docker id, and `image-name` with any name you want.

```
docker build -f Dockerfile.dev -t <docker-id>/<image-name> .
```

replace `<port>` with your port, and `<image-name>` with your image name

```
docker run -it -p <port>:<port> <image-name>
```

_If you want your react image to run immediately after you make changes_

```
docker run -p <port>:<port> -v /app/node_modules -v $(pwd):/app <image-name>
```

### **You can run the image using docker-compose file**

```
docker-compose up
```

---

## Production Environment

file used: `Dockerfile`

production dockerfile define two functionalities, one is for creating react production build, and the second one is nginx configuration which copy file from base image to nginx file system.

**To start nginx on a terminal**

```
docker run -p 8080:80 <imange-name/container-id>
```

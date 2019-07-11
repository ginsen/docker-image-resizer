# Docker-Image-Resizer
Docker service to resize image on the fly.<br>
This project use [ginsen/image-resizer](https://github.com/ginsen/image-resizer.git) fork from [jimmynicol/image-resizer](https://github.com/jimmynicol/image-resizer) as engine to resize/optimize
images on-the-fly.

# Build docker image

Download this project with git and build image docker.

```bash
$ git clone https://github.com/ginsen/docker-image-resizer.git
$ cd docker-image-resizer
$ docker build -t image-resizer:1.0.0 .
```

NOTE: Don't forget the last dot.

# Run docker container

When the image docker is has build, create the docker container with your S3 environment vars and run server in 3001 tcp/port.

```bash
$ docker run -d --name server-resizer -p 3001:3001 -e AWS_ACCESS_KEY_ID={your-access-key} -e AWS_SECRET_ACCESS_KEY={your-secret-access} -e AWS_REGION={your-region} -e S3_BUCKET={your-bucket} image-resizer:1.0.0
```

NOTE: Remember replace **your-access-key**, **your-secret-access**, **your-region** and **your-bucket** with your valid
params to connect with your S3 store.

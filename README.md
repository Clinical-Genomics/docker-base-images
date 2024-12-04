# docker-base-images
A collection of useful Dockerfiles to be used as base images for more advanced Dockerfiles

### Build an image

```docker build -t <name-of-image> --platform linux/amd64 .```


### Tag an image

```docker tag <name-of-image> clinicalgenomics/<name-of-image>:<tag>```


### Push the image to ClinicalGenomics Docker Hub:

```docker push clinicalgenomics/<name-of-image>:<tag>```
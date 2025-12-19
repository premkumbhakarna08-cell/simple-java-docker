## simple-java-docker-App
## Author: Prem Kumbhakarna

This is a basic Java application build using raw 'javac' packaged and run inside a Docker container

## Project structure 

- 'src/' - Java source files 
- 'Dockerfile' - Build the Docker image

## Jenkins CI/CD Pipeline 

A Jenkins pipeline is configured to:

1. 'checkout' - the repository 
2. 'compile' - Java source using 'Javac'
3. 'Build' - A docker image 
4. 'Push' - the image to docker hub 

The pipeline build and tages the image with:
- 'premk26/simple-java-docker:Latest 

## Docker Hub

Image is push to: 'premk26/simple-java-docker:0.1

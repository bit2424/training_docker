# DOCKERFILE


> Docker can build images automatically by reading the instructions from a Dockerfile. 
> A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. 
> Using docker build users can create an automated build that executes several command-line instructions in succession.

![Dockerfile](https://geekflare.com/wp-content/uploads/2019/07/dockerfile-697x270.png)

## BASIC COMMANDS

FROM – Defines the base image to use and start the build process.

RUN – It takes the command and its arguments to run it from the image.

CMD – Similar function as a RUN command, but it gets executed only after the container is instantiated.

ENTRYPOINT – It targets your default application in the image when the container is created.

COPY – It copies the files from source to destination (inside the container).

ENV – Sets environment variables.

WORKDIR - Instruction sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile

### PRE-REQUISITES
- Docker daemon
- Basic skill bash

## PRACTICE 

We going to build a basic image, it is based Alpine OS and contains ours own Icesi page :D. We will install Apache2 and we will download Icesi page to apache server. 

1. Create a directory named "01_dockerfile"
``` mkdir 01_dockerfile```
2. Into directory make a file named Dockerfile
```
cd 01_dockerfile
nano Dockerfile
```
3. Add instruction MAINTANER (maintaner instruction set Autor field.
```
MAINTANER JSGD@DEVOPS.COM
```
4. Add instruction FROM alpine
```
FROM alpine:latest
```

5. Add command RUN for download and install APACHE2
```
RUN apk --no-cache upgrade
RUN apk add --no-cache apache2
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf
```

6. Add instruction RUN for download WGET and we can download icesi page
```
RUN apk add wget
```

7. Add next instructions 
```
RUN rm /var/www/localhost/htdocs/index.html
WORKDIR /var/www/localhost/htdocs
RUN wget -O index.html www.icesi.edu.co
```

8. Add next instructions
```
EXPOSE 80
CMD ["-D","FOREGROUND"]
ENTRYPOINT ["/usr/sbin/httpd"]
```
Bonus: Explain whats is the diference between CMD and ENTRYPOINT (+1)
Bonus2: Optimize image

9. Save Dockerfile and BUILD and RUN image (If you dont know, you can go to https://github.com/icesi-devops/training_docker :) )


## CHALLENGE

This Challege Give +5 points :) 

You should fork the next repo: https://github.com/ikermatias/todo-angular. It contains a TodoApp made in Angular.
You Should make and Dockerfile that deploy the app in a container :) !


### REFERENCES
- https://geekflare.com/dockerfile-tutorial/
- https://docs.docker.com/engine/reference/builder/

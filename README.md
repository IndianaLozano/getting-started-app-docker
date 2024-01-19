# Getting started

This repository is a sample application for users following the getting started guide at https://docs.docker.com/get-started/.

The application is based on the application from the getting started tutorial at https://github.com/docker/getting-started

```
docker build -t getting-started .
```
The docker build command uses the Dockerfile to build a new image. You might have noticed that Docker downloaded a lot of "layers". This is because you instructed the builder that you wanted to start from the node:18-alpine image. But, since you didn't have that on your machine, Docker needed to download the image.

After Docker downloaded the image, the instructions from the Dockerfile copied in your application and used yarn to install your application's dependencies. The CMD directive specifies the default command to run when starting a container from this image.

Finally, the -t flag tags your image. Think of this as a human-readable name for the final image. Since you named the image getting-started, you can refer to that image when you run a container.

The . at the end of the docker build command tells Docker that it should look for the Dockerfile in the current directory.
```
docker run -dp 127.0.0.1:3000:3000 getting-started
```
The -d flag (short for --detach) runs the container in the background. The -p flag (short for --publish) creates a port mapping between the host and the container. The -p flag takes a string value in the format of HOST:CONTAINER, where HOST is the address on the host, and CONTAINER is the port on the container. The command publishes the container's port 3000 to 127.0.0.1:3000 (localhost:3000) on the host. Without the port mapping, you wouldn't be able to access the application from the host.

El comando
```
sudo aa-remove-unknown
```
se puede utilizar para solucionar errores del tipo `Error response from daemon: cannot stop container: containerId: permission denied `

To remove a container in a single command, add force flag:
```
docker rm -f <the-container-id>
```

# Empezando 

Este repositorio es una aplicación de ejemplo para usuarios que siguen la guía de inicio en https://docs.docker.com/get-started/.

La aplicación se basa en la aplicación del tutorial de inicio en https://github.com/docker/getting-started

```
docker build -t getting-started .
```
El comando docker build utiliza el Dockerfile para construir una nueva imagen. Puede haber notado que Docker descargó muchas "capas". Esto se debe a que le indicó al constructor que quería comenzar desde la imagen node:18-alpine. Pero, dado que no la tenía en su máquina, Docker necesitó descargar la imagen.

Después de descargar la imagen, las instrucciones del Dockerfile copiaron su aplicación y utilizaron yarn para instalar las dependencias de su aplicación. La directiva CMD especifica el comando predeterminado para ejecutar al iniciar un contenedor a partir de esta imagen.

Finalmente, la bandera -t etiqueta su imagen. Piense en esto como un nombre legible por humanos para la imagen final. Dado que nombró la imagen como getting-started, puede hacer referencia a esa imagen cuando ejecuta un contenedor.

El punto . al final del comando docker build le dice a Docker que debería buscar el Dockerfile en el directorio actual.
```
docker run -dp 127.0.0.1:3000:3000 getting-started
```
La bandera -d (abreviatura de --detach) ejecuta el contenedor en segundo plano. La bandera -p (abreviatura de --publish) crea un mapeo de puertos entre el host y el contenedor. La bandera -p toma un valor de cadena en el formato HOST:CONTAINER, donde HOST es la dirección en el host y CONTAINER es el puerto en el contenedor. El comando publica el puerto 3000 del contenedor en 127.0.0.1:3000 (localhost:3000) en el host. Sin el mapeo de puertos, no podría acceder a la aplicación desde el host.

El comando
```
sudo aa-remove-unknown
```
se puede utilizar para solucionar errores del tipo `Error response from daemon: cannot stop container: containerId: permission denied `

To remove a container in a single command, add force flag:
```
docker rm -f <the-container-id>
```

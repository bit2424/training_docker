## Manual taks

1. apt update
2. apt install apache
3. apt install wget
4. service apache2 start

<nombreCUentaDockeerHub>/<nombreRepoDockerhub>

TODO:
1. Desplegar servidor web scraping icesi alpine image base
2. Analizar pesos de imagenes cuando: Tenemos varios RUN en el dockerfile y cuando tenemos un solo RUN en el docker
3. Decir las diferencias entre CMD y ENTRYPOINT


RUN apt update
RUN apt install -y wget

docker build ... 80MB

RUN apt update && / apt install -y wget

docker build --- 100MB o 50MB

PR to github.com/icesiops/sd-workshop3

WHEN: Hasta el Domingo 11:59pm 04/09/2020

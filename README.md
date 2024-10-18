# Practica-4-Network-e-Compose

## Docker network

## 1 Crear unha rede en docker

Para crear una red en docker desde la terminal utilizando el comando `docker network create red-1` para comprobar que se creo correctamente se utiliza `docker network ls`y aparecera la red creada.

## 2 Crear dous contenedores unidos a esa rede

Utilizando el comando `docker run -itd --network=red-1 busybox` se creara el contenedor unido a la red creada anteriormente *red-1*  el *-itd* la **i** hara que permita interactuar con el, la **t** asiganara una terminal al contenedor y la **d** ejecutara el contenedor en segundo plano. *Busybox* es la imagen que se usara al crearse el contenedor.

Se repetira este comando dos veces para asi obtener los dos contenedor.

## 3 Comprobar que os contenedores están na rede

Para comprobar con el comando `docker network inspect red-1` proporcionara informacion entre ella los contenedor conectados a la red.

## 4 Comprobar que os contenedores poden verse entre eles

Para comprobar primero se usara el comando `docker ps` ahi veremos los nombres de los contenedor y abrimos un contenedor, segundo con el comando `docker exec -it charming_fermat sh` una vez dentro de este contenedor haremos pin al segundo contenedor.
Resultado: --- gallant_jemison ping statistics ---
4 packets transmitted, 4 packets received, 0% packet loss
round-trip min/avg/max = 0.152/0.250/0.427 ms

## 5 Listar os contenedores conectados á rede

Para comprobar con el comando `docker network inspect red-1` proporcionara informacion entre ella los contenedor conectados a la red.

Tambien utilizando el comando `docker network inspect red-1 | jq -r '.[0].Containers[] | .Name'` no indicara solo el nombre de los comandos creados dentro de la red.

## 6 Listar as propiedades da rede

Utilizando el comando `docker network ls` se podra ver una vision general de las propiedades de la red, para profundizar se podria utilizar el comando `docker network inspect red-1`.

## 7 Crea outra rede

Se repide el primer comando utilizando otro nombre, `docker network create red-2`.

## 8 Lanza dous contenedores novos conectados a esa nova rede

Una vez creada la red utilizando el comando `docker run -itd --name=jose --network=red-2 busybox` se repetira dos veces.

## 9 Comproba as posibles conexións entre os 4 contenedores
 

Accedemos al contenedor creado, `docker exec -it manu sh` y hacemos ping al otro contenedor se ve que da envia los ping sin problema. Al hacerle ping al cotenedor de la primera red no indica que no es valido.

/ # ping chaming_fermat
ping: bad address 'chaming_fermat'
/ # 


## Docker compose:

## 1 Segue os pasos da guía de iniciación de docker-compose, e explica coas túas palabras os pasos que segues e qué fan.

Docker compose simplifica el proceso de gestionar aplicaciones con multiples contenedores, porque pertmite definir todo en un archivo YAML.

Se tiene que tener instalada docker compose, al estar trabajando con docker ya viene inluido dentro de los paquete.

# Paso1: Instar

Dentro de este paso se tiene que cumplir una serie de requisitos por ejemplo; crear una carpeta, un archivo `.py`, un archivo `.txt` y un dockerfile.

# Paso2:  Definir los servicios en un archivo Compose

Como se comento en el primer apartado con `docker-compose` simplifica el control de sus aplicaciones. En este paso se creara un archivo ỳaml` este archivo define dos servicios web y redis. El web utiliza una imagen y el redis servicio utiliza una imagen publica. 

# Paso3:  Construya y ejecute su aplicación con Compose

Con un solo comando, crea y inicia todos los servicios desde su archivo de configuración.

# Paso4:  Editar el archivo Compose para usar Compose Watch

Se utiliza para edicion del archivo `.yaml` y cada vez que se edite docker compose actualizara el codigo.

## 2 Agora que sabes algo máis de docker-compose, crea un arquivo (ou varios arquivos) de configuración que ó ser lanzados cun docker-compose up, resulten nunha rede docker á que estean conectados 3 contenedores, explica os parámetros do .yaml usado


## 3 Busca e proba 4 parámetros e configuracións diferentes que podes incluir no arquivo compose, explica qué fan. (por exemplo diferentes cousas que facer coa opción RUN)



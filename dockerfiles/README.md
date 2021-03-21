# Guía para utilizar nuestra imagen de docker

### 1. Descargar la imagen de dockerhub
Nuestra imagen se encuentra alojada en dockerhub por lo que puedes descargarla en la línea de comandos ejecutando lo siguiente:
```{bash}
docker pull diramtz/pkg:0.1
```
![descarga de la imagen desde dockerhub]("../images/docker1.png")

### 2. Construir el contenedor
Para construir tu contenedor desde la imagen que acabas de descargar y ejecutarlo en el puerto 8888, ejecuta el siguiente comando:
```
docker run -it -p 8888:8888 diramtz/pkg:0.1
```
![docker run]("../images/docker2.png")

### 3. Utilizar nuestro paquete en jupyterlab
Después de ejecutar lo anterior, en la terminal te aparecerán dos urls diferentes. Copia la dirección de ```https://127.0.0.1:8888/lab``` la cual corresponde a tu localhost y pégala en la barra de direcciones de tu navegador preferido. Al dar enter, te pedirá una contraseña. La contraseña es **qwerty**.

Después de ingresar la contraseña, te llevará a jupyterlab. En jupyterlab dirígete al directorio ```/home/miuser/``` aquí podrás crear notebooks de python y comenzar a trabajar.
![directorio en jupyterlab]("../images/docker3.png")
![directorio en jupyterlab]("../images/docker4.png")

Encontrarás que el ambiente virtual de jupyterlab ya tiene instalado nuestro paquete ```ffmaxflow``` y podrás usarlo sin ningún problema.

![ejercicio de ejemplo con ffmaxflow]("../images/docker5.png")

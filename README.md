# Practica 5 - Multithreading
## Introducción

## Explicación del código
El código desarrollado se divide en dos partes: el servidor y el simulador de clientes.

### 1. Servidor (`server.ipynb`)

## Ejecución del código 
1. Abre una terminal o línea de comandos en tu sistema.

2. Clona el repositorio con el siguiente comando:

    ```
    git clone https://github.com/202006359/Practica-5-Multithreading.git
    ```

3. Inicializa el servidor Jupyter Notebook desde Anaconda.
<img width="249" alt="image" src="https://github.com/202006359/Practica-1-UDP/assets/113789409/8347b6ac-c6fb-42b4-8620-f8b7634689c4">

  
5. Esto abrirá una ventana del navegador web con el panel de control de Jupyter Notebook. Desde aquí, dirigite a la proyecto Practica-5-Multithreading y picha en la carpeta "Apartado1.1". A continuación, abre el archivo "server.ipynb" y "client.ipynb".  

6. Ejecuta el código del servidor en Jupyter Notebook ejecutando todas las celdas de código en "server.ipynb". Selecciona el numero de puerto donde quieres escuchar los mensajes TCP, e.g. 40000. No puede ser menor de 1024 ni mayor que 65535.

7. Ejecuta el código del cliente en Jupyter Notebook ejecutando todas las celdas de código en "client.ipynb". Introduzca la direccion del servidor: localhost. A continuación, le pedirá que ingrese el numero de puerto, este debe de ser el mismo que el seleccionado en el apartado 6, e.g. 40000.

8. El codigo del "cliente.ipynb" en realidad es un simulador de clientes, el funcionamiento es muy sencillo. Una vez hechos los paso 6 y 7, le preguntará por el nombre de un cliente. Una vez escrito el nombre del cliente, escribirá el mensaje que mandara ese cliente. Seguidamente, le volverá a preguntar por el nombre de otro cliente y por el mensaje que quiere enviar. El proceso se repite de forma indefinida hasta que introduce la palabra "exit" al preguntarle por el nombre de un cliente.

9. Una vez introducidos los nombres de los clientes y sus correspondientes mensajes, empezará el intercambio de mensajes entre clientes y servidor.

**Para ejecutar el apartado 1.2 de la práctica es exactamente el mismo proceso, salvo que en el paso 5 abrimos la carperta Apartado1.2 en vez de la carpeta Apartado1.1**

## Capturas de pantalla (Apartado 1.1 & Apartado 1.2)
### Apartado 1.1
#### Servidor
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/52ab0952-24f8-40d3-a513-5f47ca13dab9">

#### Emulador de clientes.
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/fc98bf45-5c52-4b19-a061-4e8e0bf4190a">

### Apartado 1.2
#### Servidor
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/d1d37ad4-48a8-45d5-92c1-d6d14d96fceb">


#### Emulador de clientes.
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/8afd2c96-bad0-419f-bcda-e65fb320fc29">




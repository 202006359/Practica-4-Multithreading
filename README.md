# Practica 5 - Multithreading
## Introducción
El objetivo de esta práctica es mejorar los mecanismos de comunicación entre cliente y servidor implementados en las prácticas anteriores utilizando multithreading.

## Explicación del código
El código desarrollado se divide en dos partes: el Apartado 1.1 y Apartado 1.2. Ambos cuentan con un servidor y un simulador de clientes.

### Apartado 1.1
#### 1. Servidor (`server.ipynb`)
1. **Importación de módulos y definición de funciones:**
   - Se importan los módulos necesarios (`socket`, `sys`, `traceback`, `threading`).
   - Se define la función `main()` que inicia la ejecución del servidor.
   - Se define la función `start_server()` que configura y pone en marcha el servidor.
   - Se define la función `get_valid_port()` que solicita al usuario un número de puerto válido.
   - Se define la función `client_thread()` que maneja las conexiones de los clientes.

2. **Función `main()`:**
   - Llama a la función `start_server()` para iniciar el servidor.

3. **Función `start_server()`**:
   - Configura el socket del servidor y lo pone a la escucha en el puerto especificado por el usuario.
   - Acepta conexiones entrantes de clientes y lanza una hilo (`thread`) para manejar cada conexión.

4. **Función `get_valid_port()`**:
   - Solicita al usuario un número de puerto válido en el rango especificado.

5. **Función `client_thread()`**:
   - Recibe los datos enviados por el cliente.
   - Divide el mensaje en el identificador del cliente y el mensaje en sí.
   - Imprime el mensaje recibido del cliente.
     **Problema -> La impresión por pantalla se ve afectada por la propia concurrencia de los hilos. Se soluciona en el Apartado 1.2**
   - Envía una respuesta de vuelta al cliente.

#### 2. Simulador de clientes (`client.ipynb`)
1. **Importación de módulos y definición de funciones:**
   - Se importan los módulos necesarios (`socket`, `sys`, `threading`).
   - Se define la función `main()` que inicia la ejecución del cliente.
   - Se define la función `send_message()` que se encarga de enviar mensajes al servidor.

2. **Función `main()`:**
   - Solicita al usuario la dirección IP del servidor y el puerto al que se conectará.
   - Iterativamente, solicita al usuario nombres de cliente y mensajes a enviar.
   - Crea una hilo (`thread`) para cada mensaje introducido por el usuario y llama a la función `send_message()`.

3. **Función `send_message()`**:
   - Intenta establecer una conexión con el servidor usando el socket.
   - Envía el mensaje al servidor y espera una respuesta.
   - Imprime un mensaje indicando si el mensaje se envió correctamente.
   - Imprime la respuesta recibida del servidor.
   - Cierra la conexión con el servidor.

### Apartado 1.2
#### 1. Servidor (`server.ipynb`)
1. **Importación de módulos y definición de funciones:**
   - Se importan los módulos necesarios (`socket`, `sys`, `traceback`, `threading`).
   - Se define `print_lock` como un objeto de bloqueo (`Lock`) de threading.
     **Objeto clave para solucinar el problema de impresión del Apartado 1.1, lo usaremos en cada impresión invocada dentro de un hilo.**
   - Se define la función `main()` que inicia la ejecución del servidor.
   - Se define la función `start_server()` que configura y pone en marcha el servidor.
   - Se define la función `get_valid_port()` que solicita al usuario un número de puerto válido.
   - Se define la función `client_thread()` que maneja las conexiones de los clientes.

2. **Función `main()`:**
   - Llama a la función `start_server()` para iniciar el servidor.

3. **Función `start_server()`**:
   - Configura el socket del servidor y lo pone a la escucha en el puerto especificado por el usuario.
   - Acepta conexiones entrantes de clientes y lanza una hilo (`thread`) para manejar cada conexión.

4. **Función `get_valid_port()`**:
   - Solicita al usuario un número de puerto válido en el rango especificado.

5. **Función `client_thread()`**:
   - Recibe los datos enviados por el cliente.
   - Divide el mensaje en el identificador del cliente y el mensaje en sí.
   - Imprime el mensaje recibido del cliente.
     **Solución -> La impresión por pantalla se realizan con print locks**
     <img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/3e1bd8a5-0651-458f-b9ef-b8efa32d0a1a">

   - Envía una respuesta de vuelta al cliente.

#### 2. Simulador de clientes (`client.ipynb`)
1. **Importación de módulos y definición de funciones:**
   - Se importan los módulos necesarios (`socket`, `sys`, `threading`).
   - Se define `print_lock` como un objeto de bloqueo (`Lock`) de threading.
     **Objeto clave para solucinar el problema de impresión del Apartado 1.1, lo usaremos en cada impresión invocada dentro de un hilo.**
   - Se define la función `main()` que inicia la ejecución del cliente.
   - Se define la función `send_message()` que se encarga de enviar mensajes al servidor.

2. **Función `main()`:**
   - Solicita al usuario la dirección IP del servidor y el puerto al que se conectará.
   - Iterativamente, solicita al usuario nombres de cliente y mensajes a enviar.
   - Crea una hilo (`thread`) para cada mensaje introducido por el usuario y llama a la función `send_message()`.

3. **Función `send_message()`**:
   - Intenta establecer una conexión con el servidor usando el socket.
   - Envía el mensaje al servidor y espera una respuesta.
   - Imprime un mensaje indicando si el mensaje se envió correctamente.
   - Imprime la respuesta recibida del servidor.
   - Cierra la conexión con el servidor.
   - Destacar el uso de print_lock ya que será llamada por distintos hilos.
     <img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/b15de057-68d4-4a6b-b3f8-f77475877037">


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

*Para ejecutar el apartado 1.2 de la práctica es exactamente el mismo proceso, salvo que en el paso 5 abrimos la carperta Apartado1.2 en vez de la carpeta Apartado1.1*

## Capturas de pantalla (Apartado 1.1 & Apartado 1.2)
### Apartado 1.1
#### Servidor
*Se observa que los mensajes de los clientes NO han seguido el orden correcto de impresión*
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/52ab0952-24f8-40d3-a513-5f47ca13dab9">

#### Emulador de clientes
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/fc98bf45-5c52-4b19-a061-4e8e0bf4190a">

### Apartado 1.2
#### Servidor
*Se observa que los mensajes de los clientes SI han seguido el orden correcto de impresión*
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/d1d37ad4-48a8-45d5-92c1-d6d14d96fceb">

#### Emulador de clientes.
<img width="595" alt="image" src="https://github.com/202006359/Practica-5-Multithreading/assets/113789409/8afd2c96-bad0-419f-bcda-e65fb320fc29">




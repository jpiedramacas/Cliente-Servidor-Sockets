
---

# Práctica de Comunicación Cliente-Servidor en AWS con Sockets TCP

Este proyecto tiene como objetivo proporcionar una práctica paso a paso para configurar una comunicación cliente-servidor utilizando sockets TCP en Amazon Web Services (AWS). A través de esta práctica, aprenderás a configurar instancias EC2, implementar un servidor y un cliente en Python, y experimentar con la comunicación entre instancias EC2 en la nube de AWS.

## Instrucciones

### 1. Configuración de la Instancia EC2

- Inicia sesión en tu cuenta de AWS.
- Navega hasta el servicio EC2.
- Haz clic en "Launch Instance" para iniciar el proceso de creación de una nueva instancia EC2.
- Selecciona una AMI (Amazon Machine Image). Por ejemplo, puedes elegir una AMI de Ubuntu.
- Elige el tipo de instancia deseado, configura la red, el almacenamiento y otras opciones según tus preferencias.
- En la sección de "Security Group", asegúrate de configurar un grupo de seguridad que permita el tráfico TCP en el puerto 8080.
- Revisa y confirma tu configuración, luego haz clic en "Launch" para iniciar la instancia EC2.

### 2. Elección de Roles

- Cada alumno debe elegir si desea ser el servidor o el cliente.
- Una vez que hayan elegido, deben buscar un compañero de trabajo que haya elegido el rol opuesto.

### 3. Implementación del Servidor o Cliente

#### Servidor:

- Conéctate a tu instancia EC2 utilizando SSH.
- Crea un nuevo archivo Python llamado `server.py`.
- Implementa el servidor en `server.py` según tus necesidades.

#### Cliente:

- Conéctate a tu instancia EC2 utilizando SSH.
- Crea un nuevo archivo Python llamado `client.py`.
- Implementa el cliente en `client.py` según tus necesidades.

### 4. Ejecución y Prueba

#### Para el Servidor:

En la instancia EC2 que actuará como servidor, ejecuta el siguiente comando para iniciar el servidor:

```sh
python3 server.py
```

#### Para el Cliente:

En la instancia EC2 que actuará como cliente, ejecuta el siguiente comando para iniciar el cliente:

```sh
python3 client.py
```

Sigue las instrucciones en pantalla para ejecutar y probar tu aplicación cliente-servidor en AWS.

Este proyecto proporciona una práctica valiosa para comprender los conceptos de comunicación cliente-servidor y familiarizarse con el entorno de AWS. ¡Diviértete experimentando con la comunicación en la nube!

--- 

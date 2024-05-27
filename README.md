# Práctica de Comunicación Cliente-Servidor en AWS con Sockets TCP

Este proyecto consiste en una práctica de comunicación cliente-servidor utilizando sockets TCP en Amazon Web Services (AWS). El objetivo es configurar una instancia EC2 en AWS y implementar un servidor y un cliente en Python para establecer comunicación entre ellos. Los participantes experimentarán con la comunicación entre instancias EC2 en la nube.

## Instrucciones

### 1. Configuración de la Instancia EC2

- Inicia sesión en tu cuenta de AWS.
- Navega hasta el servicio EC2.
- Haz clic en "Launch Instance" para iniciar el proceso de creación de una nueva instancia EC2.
- Selecciona una AMI (Amazon Machine Image), como Ubuntu.
- Elige el tipo de instancia deseado, configura la red, el almacenamiento y otras opciones según tus preferencias.
- En la sección de "Security Group", asegúrate de configurar un grupo de seguridad que permita el tráfico TCP en el puerto 8080.
- Revisa y confirma tu configuración, luego haz clic en "Launch" para iniciar la instancia EC2.

### 2. Elección de Roles

- Cada participante debe elegir si desea ser el servidor o el cliente.
- Encuentra un compañero de trabajo que haya elegido el rol opuesto.

### 3. Implementación del Servidor o Cliente

#### Para el Servidor:

- Conéctate a tu instancia EC2 utilizando SSH.
- Crea un nuevo archivo Python llamado `server.py`.
- Copia el siguiente código en `server.py`:

```python
import socket

HOST = '0.0.0.0' 
PORT = 8080

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT)) 
    s.listen(1) 
    print('Esperando conexiones entrantes...') 
    conn, addr = s.accept() 
    with conn: 
        print('Conexión entrante desde:', addr) 
        while True: 
            data = conn.recv(1024) 
            if not data: 
                break 
            print('Mensaje recibido del cliente:', data.decode()) 
            response = input('Escribe tu mensaje al cliente: ') 
            conn.sendall(response.encode())
```

#### Para el Cliente:

- Conéctate a tu instancia EC2 utilizando SSH.
- Crea un nuevo archivo Python llamado `client.py`.
- Copia el siguiente código en `client.py`:

```python
import socket 

HOST = 'XXXXXXXX' 
PORT = 8080 

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s: 
    s.connect((HOST, PORT)) 
    while True: 
        message = input('Escribe tu mensaje al servidor: ') 
        s.sendall(message.encode()) 
        data = s.recv(1024) 
        print('Respuesta del servidor:', data.decode()) 
```

### 4. Ejecución y Prueba

#### Para el Servidor:

- En la instancia EC2 que actuará como servidor, ejecuta el siguiente comando para iniciar el servidor:

```sh
python3 server.py
```

#### Para el Cliente:

- En la instancia EC2 que actuará como cliente, ejecuta el siguiente comando para iniciar el cliente:

```sh
python3 client.py
```

Sigue las instrucciones en pantalla para enviar mensajes entre el cliente y el servidor. El cliente enviará un mensaje al servidor y recibirá una respuesta. Este proyecto proporciona una introducción práctica a la comunicación cliente-servidor utilizando sockets TCP en AWS.

# Sistema P2P con Microservicios para Compartición de Archivos

## ST0263: Tópicos Especiales en Telemática, 2024-2
### Universidad EAFIT

**Nombre del Estudiante:** Simon Betancur Bedoya  
**Correo Electrónico:** sbetancurb@eafit.edu.co
**Profesor:** Edwin Montoya

### Descripción del Proyecto

Este proyecto implementa un sistema P2P (Peer-to-Peer) para la compartición distribuida de archivos utilizando microservicios. El sistema se basa en una red P2P estructurada utilizando Chord/DHT para la localización de recursos y permite la comunicación entre nodos a través de API REST, gRPC, y MOM (Message-Oriented Middleware) con RabbitMQ.

### Arquitectura del Sistema

El sistema está compuesto por los siguientes componentes:

1. **Nodos P2P:** Cada nodo actúa como un servidor y cliente, implementando microservicios que permiten la compartición de archivos.
2. **Portmapper:** Gestiona la lista de nodos en la red, verificando su estado y facilitando la comunicación entre nodos.
3. **Microservicios:**
   - **DHT gRPC Service:** Mantiene la estructura de la red P2P y localiza los recursos.
   - **Index Service:** Lista los archivos disponibles en un nodo.
   - **Upload Service:** Permite la carga de archivos en un nodo.
   - **Download Service:** Facilita la descarga de archivos desde un nodo.
   - **MOM Service:** Maneja la comunicación asíncrona entre nodos utilizando RabbitMQ.

### Requisitos

- **Python 3.8+**
- **RabbitMQ** (para el manejo de MOM)
- **Bibliotecas Python:** FastAPI, gRPC, pika (RabbitMQ client), requests, uvicorn, entre otros.

### Instalación

1. **Clonar el repositorio:**

   ```bash
   git clone https://github.com/sbetancurb/sbetancurb-st0263.git
   cd sbetancurb-st0263
   
### Ejecucion

Para ejecutar el proyecto sigue los siguientes pasos:
1. Iniciar el RabbitMQ en el computador
2. Abrir 3 terminales diferentes, una para ejecutar el main.py, otra para ejecutar el portmapper y otra para ejecutar el cliente
3. En la terminal 1 ejecutar el siguiente comando:
   ```bash
   python main.py
4. En la terminal 2 ejecutar el siguiente comando:
   ```bash
   uvicorn portmapper:app --host 127.0.0.1 --port 8000
5. En la terminal 3 ejecutar el siguiente comando:
   ```bash
   python client.py

# Proyecto de Microservicios en NestJS

## Descripción
Este proyecto es una aplicación basada en microservicios construida con **NestJS**, diseñada para demostrar la arquitectura de microservicios, facilitando la escalabilidad y el mantenimiento. Cada microservicio es responsable de una funcionalidad específica, lo que permite un desarrollo más modular y colaborativo.

## Funcionalidades
La aplicación se compone de los siguientes microservicios:

- **Autenticación Microservicio**: Maneja el registro de usuarios y la autenticación mediante JWT (JSON Web Tokens). Este servicio asegura que solo los usuarios autenticados tengan acceso a funcionalidades sensibles.

- **Microservicio de Productos**: Permite la gestión de productos, incluyendo operaciones CRUD (Crear, Leer, Actualizar y Eliminar). Este microservicio actúa como la fuente principal de datos para la información de los productos.

- **Microservicio de Pedidos**: Se encarga de la creación y gestión de pedidos. Este servicio se comunica con el microservicio de productos para verificar la disponibilidad de los mismos antes de completar un pedido.

- **Microservicio de Pagos**: Gestiona el procesamiento de pagos de los pedidos. Este microservicio se integra con plataformas de pago para garantizar transacciones seguras y eficientes.

- **Gateway del Cliente**: Actúa como un punto de entrada para todas las solicitudes de los clientes. Este microservicio redirige las solicitudes a los microservicios correspondientes y gestiona la comunicación entre ellos.

## Tecnologías Utilizadas
- **NestJS**: Framework para construir aplicaciones del lado del servidor eficientes y escalables, que utiliza TypeScript.
- **PostgreSQL**: Sistema de gestión de bases de datos relacional que se utiliza para almacenar datos de la aplicación.
- **MongoDB**: Base de datos NoSQL utilizada para almacenar datos que no requieren un esquema rígido.
- **SQLite**: Base de datos ligera utilizada para almacenamiento temporal o pruebas.
- **NATS**: Sistema de mensajería que permite la comunicación asíncrona entre microservicios.
- **Webhooks**: Mecanismo para que las aplicaciones reciban información en tiempo real a través de notificaciones de eventos.
- **Docker**: Facilita la contenedorización de los microservicios, lo que permite un desarrollo y despliegue más sencillo y consistente en diferentes entornos.
- **Kubernetes**: Plataforma de orquestación de contenedores que gestiona el despliegue, escalado y operaciones de aplicaciones en contenedores.
- **Google Cloud (GCloud)**: Proporciona la infraestructura en la nube para alojar y ejecutar los microservicios.
- **CI/CD**: Integración y despliegue continuos que permiten automatizar el ciclo de vida del desarrollo de software.
- **Git Submodules**: Permiten manejar cada microservicio como un repositorio independiente dentro del repositorio principal.

## Estructura del Proyecto
La estructura del proyecto está organizada en submódulos, donde cada microservicio se aloja en su propio repositorio. Esto permite un manejo más sencillo de cada componente y fomenta la independencia en el desarrollo. Aquí hay un resumen de los submódulos incluidos:

1. **[Autenticación Microservicio](https://github.com/TrujiDev/authentication-microservice)**: Gestiona la autenticación y autorización de los usuarios.
2. **[Microservicio de Productos](https://github.com/TrujiDev/product-microservice)**: Permite la gestión de productos dentro de la aplicación.
3. **[Microservicio de Pedidos](https://github.com/TrujiDev/order-microservice)**: Se encarga de manejar los pedidos de los clientes.
4. **[Microservicio de Pagos](https://github.com/TrujiDev/payment-microservice)**: Procesa los pagos de los pedidos de manera segura.
5. **[Gateway del Cliente](https://github.com/TrujiDev/client-gateway)**: Punto de entrada para las solicitudes del cliente, gestionando la comunicación entre microservicios.
6. **[Launcher de Productos](https://github.com/TrujiDev/products-app-launcher)**: Facilita la inicialización y gestión de la aplicación.

## Instalación
Para instalar y ejecutar el proyecto, sigue estos pasos:

### 1. Clonar el Repositorio Principal
Clona el repositorio donde deseas añadir el submódulo:
```bash
git clone <main_repository_url>
cd <main_repository_name>
```

### 2. Inicializar y Actualizar Submódulos Existentes
Si el repositorio principal ya tiene submódulos, inicialízalos y actualízalos:
```bash
git submodule update --init --recursive
```

### 3. Ejecutar Cada Microservicio
Cada microservicio tiene su propio conjunto de dependencias y debe ser ejecutado de manera independiente. Navega a cada submódulo y ejecuta el siguiente comando:
```bash
npm install
npm run start
```

## Mantenimiento de Submódulos
### Inicializar y Actualizar Submódulos al Clonar el Repositorio
Cuando alguien clona el repositorio por primera vez, debe ejecutar el siguiente comando para inicializar y actualizar los submódulos:
```bash
git submodule update --init --recursive
```

### Actualizar Referencias de los Submódulos
Para actualizar los submódulos a sus últimas versiones remotas, utiliza:
```bash
git submodule update --remote
```

## Importante
Al trabajar en un repositorio que contiene submódulos, siempre actualiza y haz push en el submódulo primero y luego en el repositorio principal. Hacerlo al revés puede causar pérdida de referencias de los submódulos en el repositorio principal, lo que resultará en conflictos que deberán ser resueltos.

## Contribuciones
Las contribuciones son bienvenidas. Si deseas contribuir a este proyecto, sigue estos pasos:
1. Haz un fork del repositorio.
2. Crea tu feature branch (`git checkout -b feature/AmazingFeature`).
3. Haz un commit de tus cambios (`git commit -m 'Add some AmazingFeature'`).
4. Haz push a la branch (`git push origin feature/AmazingFeature`).
5. Abre un Pull Request.

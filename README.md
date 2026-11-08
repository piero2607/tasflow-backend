# TaskFlow Backend

API REST de TaskFlow, una aplicación para gestionar proyectos y tareas en equipos pequeños. Este repositorio tiene solo el backend. El frontend está en [taskflow-frontend](https://github.com/piero2607/taskflow-frontend).

Es el proyecto final del ciclo de Desarrollo de Aplicaciones Web (DAW), curso 2026-2027.

## Estado

En desarrollo.

## Qué hace

- Registro e inicio de sesión de usuarios.
- Gestión de proyectos y de sus miembros.
- Gestión de tareas con responsable, prioridad, fecha límite y estado.
- Control de permisos según el rol del usuario en cada proyecto: propietario, miembro o usuario registrado sin participación.

Los permisos se comprueban aquí, en el backend, para que no se puedan saltar con peticiones directas a la API.

## Tecnologías

- Java
- Spring Boot
- MongoDB

## Arquitectura

El backend sigue una arquitectura hexagonal, que separa la lógica de negocio de los elementos externos.

- Dominio: entidades principales y reglas de negocio.
- Casos de uso: operaciones como crear proyectos, gestionar tareas o cambiar su estado.
- Puertos: interfaces por las que se comunican las partes de la aplicación.
- Adaptadores: conectan la lógica interna con lo externo, como la API REST de Spring Boot y MongoDB.

## Requisitos

- JDK (la versión que use el proyecto)
- MongoDB, en local o en un servicio en la nube
- Maven (o el wrapper `mvnw` incluido en el proyecto)

## Instalación y ejecución

```bash
git clone https://github.com/piero2607/taskflow-backend.git
cd taskflow-backend
./mvnw spring-boot:run
```

La API queda en http://localhost:8080.

## Configuración

La conexión a MongoDB se configura en `src/main/resources/application.properties`:

```
spring.data.mongodb.uri=mongodb://localhost:27017/taskflow
```

No subas a GitHub contraseñas ni claves. Si usas una base de datos con credenciales, pásalas por variables de entorno.

## Pruebas

```bash
./mvnw test
```

## Equipo

- Piero Yovera Anaya (backend)
- Mar Bellver Alecreu (frontend, en [taskflow-frontend](https://github.com/piero2607/taskflow-frontend))

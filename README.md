# **ForoHub**
ForoHub es una  API REST que utiliza Spring, que proporciona funcionalidades para gestionar tópicos en un foro de ayuda o soporte técnico.

## Configuración del entorno de desarrollo
- Java JDK: versión 17 en adelante 
- Maven: versión 4 en adelante
- Spring Boot: versión 3 en adelante. Dependencias para agregar al crear el proyecto con Spring Initializr:
Lombok, Spring Web, Spring Boot DevTools, Spring Data JPA, Flyway Migration, MySQL Driver, Validation, Spring Security 
- MySQL: versión 8 en adelante 
- IDE (Entorno de desarrollo integrado) IntelliJ
- Para interactuar con la API, puedes usar herramientas como Insomnia o Postman

## Características
- Crear un nuevo tópico
- Mostrar todos los tópicos creados
- Mostrar un tópico específico
- Actualizar un tópico
- Eliminar un tópico


## Clona el repositorio:
Copiar código
git clone https://github.com/calegriam/forohub

cd forohub

## Diagrama de Base de Datos

Necesitarás utilizar una base de datos MySQL en funcionamiento para almacenar la información de la aplicación.
Para crear un tópico necesitan las siguientes informaciones:
- - id
- - título
- - mensaje
- - fecha de creación
- - status (estado del tópico)
- - autor
- - curso

Crea una base de datos llamada foro_hub.

Actualiza la configuración de la base de datos en src/main/resources/application.properties:
- spring.datasource.url=jdbc:mysql://localhost:3306/foro_hub
- spring.datasource.username=tuusuario
- spring.datasource.password=tupassword


## Endpoints

```http
 Autenticación
- Registra un nuevo usuario:
POST /auth/register
{
    "nombre": "Juan Perez",
    "correo_electronico": "juan.perez@example.com",
    "contrasena": "password123"
} 

- Tópicos
POST /topicos
{
    "titulo": "Nuevo Tópico",
    "mensaje": "Este es un nuevo mensaje de tópico.",
    "autor": "Juan Perez",
    "curso": "Spring Boot"
}

- Obtener Todos los Tópicos
PUT /topicos/{id}
{
    "titulo": "Tópico Actualizado",
    "mensaje": "Este es un mensaje de tópico actualizado.",
    "autor": "Juan Perez",
    "curso": "Spring Boot"
}

- Actualizar Tópico
PUT /topicos/{id}
{
    "titulo": "Tópico Actualizado",
    "mensaje": "Este es un mensaje de tópico actualizado.",
    "autor": "Juan Perez",
    "curso": "Spring Boot"
}

- Eliminar Tópico
DELETE /topicos/{id}

# ForoHub 🚀

**ForoHub** es una API desarrollada con Spring Boot para gestionar foros de discusión en línea. Permite crear, leer, actualizar y eliminar (CRUD) tópicos de discusión.

## 📑 Características principales
- Gestión de tópicos de discusión (CRUD).
- Seguridad con **Spring Security** y autenticación JWT.
- Base de datos MySQL con migraciones gestionadas por Flyway.
- Documentación con Swagger (opcional).

## ⚙️ Tecnologías usadas
- **Java 17**
- **Spring Boot 3.2.3**
- **Spring Security**
- **JWT (JSON Web Token)**
- **Flyway para migraciones**
- **MySQL**

## 🚀 Instalación y ejecución

### 1. Clonar el repositorio:
```bash
git clone https://github.com/TU_USUARIO/forohub.git
cd forohub
```

### 2. Configurar la base de datos:
Crea un archivo application.properties en src/main/resources/ con las siguientes propiedades:
```bash
spring.datasource.url=jdbc:mysql://localhost:3306/forohub
spring.datasource.username=root
spring.datasource.password=root
spring.jpa.hibernate.ddl-auto=none
jwt.secret=TU_CLAVE_SECRETA
jwt.expiration=3600000
```

### 3. Ejecutar el proyecto con Maven:
```bash
mvn spring-boot:run
```
La aplicación estará disponible en http://localhost:8080.

## 🔐 Seguridad y Autenticación
El acceso a los endpoints está protegido mediante JWT.
Para autenticarte, envía una solicitud POST a ```/auth/login``` con las siguientes credenciales:
```bash
{
  "username": "admin",
  "password": "admin123"
}
```
Recibirás un token de acceso que debes incluir en cada solicitud como:
```bash
Authorization: Bearer <TOKEN>
```

## 🛠️ Endpoints principales:
POST ```/auth/login``` 	Autenticación de usuario
GET ```/topicos``` Obtener todos los tópicos
POST ```/topicos``` Crear un nuevo tópico
PUT ```/topicos/{id}``` Actualizar un tópico
DELETE ```/topicos/{id}``` Eliminar un tópico

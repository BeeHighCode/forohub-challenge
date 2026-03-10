# 🌐 ForoHub API

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.3-green)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue)
![JWT](https://img.shields.io/badge/JWT-Auth-yellow)
![License](https://img.shields.io/badge/License-Proprietary-red)

API REST de foro técnico con **Spring Boot 3**, **Spring Security (JWT)** y **OpenAPI**; robusta y documentada.

---

## 📋 Tabla de contenidos

- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Endpoints](#-endpoints)
- [Configuración](#-configuración)
- [JWT](#-jwt)
- [Cómo ejecutar](#-cómo-ejecutar)
- [Autoría](#-autoría)

---

## ✨ Características

- ✅ Autenticación JWT con tokens de 2 horas
- ✅ CRUD completo de Tópicos
- ✅ Documentación OpenAPI / Swagger UI
- ✅ Validaciones con Bean Validation
- ✅ Migraciones de BD con Flyway
- ✅ Manejo global de errores
- ✅ Variables de entorno para configuración segura

---

## 🛠️ Tecnologías

| Tecnología | Versión |
|---|---|
| Java | 17 |
| Spring Boot | 3.3 |
| Spring Security | 6 |
| MySQL | 8.0 |
| Flyway | Migrations |
| JWT (Auth0) | 4.x |
| SpringDoc OpenAPI | 2.x |

---

## 🔗 Endpoints

### Autenticación
| Método | Ruta | Descripción | Acceso |
|---|---|---|---|
| `POST` | `/login` | Obtener token JWT | Público |

### Tópicos
| Método | Ruta | Descripción | Acceso |
|---|---|---|---|
| `GET` | `/topicos` | Listar tópicos (paginado) | 🔒 Token |
| `GET` | `/topicos/{id}` | Detalle de un tópico | 🔒 Token |
| `GET` | `/topicos/filter` | Filtrar por curso y año | 🔒 Token |
| `POST` | `/topicos` | Crear tópico | 🔒 Token |
| `PUT` | `/topicos/{id}` | Actualizar tópico | 🔒 Token |
| `DELETE` | `/topicos/{id}` | Eliminar tópico | 🔒 Token |

---

## ⚙️ Configuración

Crea un archivo `.env` o configura las variables de entorno:

```properties
DB_DATABASE_URL=jdbc:mysql://localhost:3306/forohub_db
TU_USUARIO=root
TU_PASSWORD=tu_password
JWT_SECRET=tu_secreto_jwt
🔐 JWT
json
POST /login
{
  "login": "usuario@email.com",
  "contrasena": "123456"
}
Token válido por 2 horas. Úsalo en el header:

text
Authorization: Bearer <token>
🚀 Cómo ejecutar
Clona el repositorio

Configura las variables de entorno

Crea la base de datos: CREATE DATABASE forohub_db;

Ejecuta el proyecto — Flyway crea las tablas automáticamente

Accede a Swagger UI: http://localhost:8080/swagger-ui/index.html

📐 Estructura del proyecto
text
src/
├── main/
│   ├── java/com/aluraCursos/ForoHub/
│   │   ├── controller/     # Autenticación, Tópicos, Respuestas
│   │   ├── domain/
│   │   │   ├── curso/      # Entidad Curso
│   │   │   ├── topico/     # Entidad Tópico
│   │   │   ├── usuario/    # Entidad Usuario
│   │   │   └── dto/        # Records DTO
│   │   ├── infra/
│   │   │   ├── errores/    # Manejo de errores
│   │   │   ├── security/   # JWT, Filtros, Config
│   │   │   └── springdoc/  # Configuración OpenAPI
│   │   └── repository/     # Repositorios JPA
│   └── resources/
│       ├── application.properties
│       └── db/migration/   # Scripts Flyway
└── test/
🗺️ Roadmap
 Refresh tokens

 Administración de usuarios/roles vía endpoints

 Tests de integración (RestAssured / Testcontainers)

 Perfil Docker (compose: app + MySQL)

🔥 Autoría
Desarrollado por BeeHighCode
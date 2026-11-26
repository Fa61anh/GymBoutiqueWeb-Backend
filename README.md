# GymBoutique Backend — IronStrong Fitness API REST

API RESTful desarrollada en **Java 21** y **Spring Boot 4** para la gestión integral de tienda deportiva, planes de membresía, inventario y emisión de boletas electrónicas de **IronStrong Fitness** (Evaluación Parcial N° 3 — DSY1104 Desarrollo Fullstack II).

---

## Tecnologías Utilizadas

* **Lenguaje:** Java 21
* **Framework Backend:** Spring Boot 4 (Spring Web, Spring Data JPA, Spring Security)
* **Base de Datos:** PostgreSQL (`gymboutique`)
* **Seguridad y Autenticación:** JSON Web Tokens (JWT) + encriptación de contraseñas con BCrypt
* **Documentación API:** OpenAPI 3 / Swagger UI (`springdoc-openapi`)
* **Gestor de Dependencias:** Maven Wrapper (`mvnw`)

---

## Modelo de Base de Datos Relacional

El sistema persiste la información en PostgreSQL mediante 5 entidades relacionales:

1. **`usuario`**: Almacena los usuarios registrados (`id`, `nombre`, `correo`, `password` encriptado y `rol`: `ADMIN`, `VENDEDOR`, `CLIENTE`).
2. **`categoria`**: Clasifica el catálogo (`Suplementos`, `Accesorios`, `Membresías`).
3. **`producto`**: Gestiona artículos físicos y planes de suscripción (`id`, `name`, `price`, `stock`, `description`, `image`, `brand`, `categoria_id`).
4. **`boleta`**: Registra las ventas realizadas (`id`, `fecha`, `total`, `estado`, `usuario_id`).
5. **`detalle_boleta`**: Detalle de ítems por boleta (`id`, `boleta_id`, `producto_id`, `cantidad`, `precio_unitario`, `subtotal`).

---

## Requisitos Previos

* **JDK 21** instalado y configurado en las variables de entorno (`JAVA_HOME`).
* **PostgreSQL** en ejecución en el puerto `5432` con una base de datos creada llamada **`gymboutique`**.
* Configurar credenciales de base de datos en `src/main/resources/application.properties` (por defecto usuario `postgres` y contraseña `postgres`).

---

## Instalación y Ejecución

1. Clonar el repositorio:
   ```bash
   git clone [https://github.com/TU_USUARIO/gymboutique-backend.git](https://github.com/TU_USUARIO/gymboutique-backend.git)
   cd gymboutique-backend

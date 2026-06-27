# Configuración del entorno local

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir | Equipo: DevOps

## Objetivo

Definir los requisitos y pasos necesarios para preparar el entorno de desarrollo local, permitiendo a cualquier integrante del equipo ejecutar la plataforma de forma consistente.

---

## Requisitos de software

Antes de iniciar, se recomienda contar con las siguientes herramientas:

| Herramienta | Versión recomendada |
|-------------|---------------------|
| Git | 2.40 o superior |
| Docker | Última versión estable |
| Docker Compose | Última versión estable |
| Java JDK | 21 |
| Maven | 3.9 o superior |
| Node.js | 20 LTS |
| Visual Studio Code o IntelliJ IDEA | Última versión |

---

## Clonar el repositorio

```bash
git clone <url-del-repositorio>
cd gestion-horarios-sena
```

---

## Variables de entorno

Cada microservicio debe contar con un archivo de configuración (`.env`) que incluya la información necesaria para su ejecución.

Ejemplo:

```env
SERVER_PORT=8080
DB_HOST=localhost
DB_PORT=5432
DB_NAME=horarios
DB_USER=usuario
DB_PASSWORD=contraseña
JWT_SECRET=********
```

Las credenciales sensibles no deben almacenarse en el repositorio.

---

## Ejecución de servicios

Los microservicios pueden ejecutarse de forma independiente durante el desarrollo.

Ejemplo con Maven:

```bash
mvn spring-boot:run
```

O mediante Docker Compose:

```bash
docker compose up
```

---

## Verificación

Antes de comenzar el desarrollo se recomienda comprobar que:

- Todos los microservicios inician correctamente.
- Las bases de datos están disponibles.
- El API Gateway responde correctamente.
- La autenticación funciona mediante JWT.
- La comunicación entre servicios es correcta.

---

## Buenas prácticas

- Mantener actualizadas las dependencias del proyecto.
- No subir archivos `.env` al repositorio.
- Utilizar ramas independientes para nuevas funcionalidades.
- Ejecutar pruebas antes de realizar un commit.
- Sincronizar frecuentemente el repositorio con la rama principal.

---

## Resultado esperado

Al finalizar la configuración, el entorno local permitirá desarrollar, ejecutar y probar los microservicios de la plataforma de Gestión de Horarios SENA de manera uniforme para todos los integrantes del equipo.
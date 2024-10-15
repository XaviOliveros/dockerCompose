Aquí te dejo un ejemplo de **README** que puedes incluir en tu proyecto para que otras personas sepan cómo descargar y usar las imágenes de Docker de **SonarQube** y **PostgreSQL**.

---

# SonarQube + PostgreSQL Docker Setup

Este proyecto contiene la configuración necesaria para ejecutar **SonarQube** con una base de datos **PostgreSQL** utilizando **Docker Compose**.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalados los siguientes componentes:

- **Docker**: [Instalar Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Instalar Docker Compose](https://docs.docker.com/compose/install/)

## Instrucciones

Sigue estos pasos para poner en marcha el entorno de SonarQube con PostgreSQL.

### 1. Clonar este repositorio

Clona este repositorio en tu máquina local:

```bash
git clone https://github.com/tu-usuario/sonarqube-postgres-docker.git
cd sonarqube-postgres-docker
```

### 2. Configurar Docker Compose

El archivo `docker-compose.yml` ya está configurado para descargar las imágenes de **SonarQube** y **PostgreSQL** desde Docker Hub.

### 3. Levantar los contenedores

Para levantar los servicios de **SonarQube** y **PostgreSQL**, ejecuta el siguiente comando en la terminal desde el directorio donde se encuentra el archivo `docker-compose.yml`:

```bash
docker-compose up
```

Esto descargará las imágenes necesarias y levantará los contenedores. SonarQube estará disponible en la siguiente URL:

```
http://localhost:9000
```

### 4. Iniciar sesión en SonarQube

Una vez que el contenedor de SonarQube esté listo, accede a la URL `http://localhost:9000` en tu navegador. Inicia sesión con las credenciales por defecto:

- **Usuario**: `admin`
- **Contraseña**: `admin`

Se recomienda cambiar la contraseña de administrador después del primer inicio de sesión.

### 5. Detener los contenedores

Cuando hayas terminado de usar SonarQube, puedes detener los contenedores ejecutando:

```bash
docker-compose down
```

Este comando detendrá y eliminará los contenedores, pero mantendrá los datos de la base de datos en el volumen para su reutilización en futuras ejecuciones.

## Actualización de imágenes

Si necesitas actualizar las imágenes de Docker, puedes ejecutar:

```bash
docker-compose pull
docker-compose up --force-recreate
```

Esto descargará las últimas versiones de las imágenes y recreará los contenedores.

## Estructura del proyecto

```plaintext
sonarqube-postgres-docker/
├── docker-compose.yml  # Configuración de los servicios SonarQube y PostgreSQL
├── README.md           # Este archivo con las instrucciones
```

## Notas adicionales

- Los datos de la base de datos **PostgreSQL** se almacenan en el volumen `db-data` para persistencia entre ejecuciones.
- Puedes personalizar el archivo `docker-compose.yml` si necesitas cambiar configuraciones como puertos, credenciales o versiones de imágenes.

## Recursos

- [SonarQube Documentation](https://docs.sonarqube.org/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Docker Documentation](https://docs.docker.com/)

---

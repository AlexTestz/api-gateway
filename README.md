# API Gateway - Pet Host

Este proyecto es un **API Gateway** para el sistema Pet Host, encargado de enrutar y orquestar las peticiones entre los diferentes microservicios del ecosistema (usuarios, clientes, mascotas, etc).

---

## Tecnologías Utilizadas

- **Lenguaje:** Python
- **Framework:** FastAPI
- **Cliente HTTP:** httpx

---

## Estilo de Arquitectura

- **RESTful API:** Todos los endpoints siguen el estilo REST para la comunicación entre servicios.
- **Microservicios:** El API Gateway actúa como punto de entrada único para varios microservicios independientes.

---

## Patrones de Diseño

- **KISS (Keep It Simple, Stupid):** El código es sencillo y directo, evitando complejidad innecesaria.
- **DRY (Don't Repeat Yourself):** Se reutilizan funciones y configuraciones para evitar duplicidad.
- **SOLID:** Se aplican principios básicos de diseño orientado a objetos para mantener el código mantenible y escalable.

---

## Arquitectura

- **N-Capas:** Separación clara entre rutas, lógica de negocio y configuración.
- **API Gateway:** Centraliza la entrada de peticiones y delega a los microservicios correspondientes.

---

## Seguridad

- **JWT (JSON Web Token):** Se utiliza para la autenticación y autorización de usuarios en los endpoints protegidos.
- **CORS (Cross-Origin Resource Sharing):** Configurado para permitir solicitudes desde orígenes permitidos y proteger el acceso a la API.

---

---

## Endpoints Principales

- `/api/users/` - Gestión de usuarios (registro, login, validación de token, cambio de contraseña)
- `/api/clients/` - Gestión de clientes (crear, listar, actualizar, eliminar)
- `/api/pets/` - Gestión de mascotas (crear, listar, actualizar, eliminar)

---

## Variables de Entorno

Configura las URLs de los microservicios en el archivo de configuración o variables de entorno:

- `REGISTER_USER_URL`
- `LOGIN_USER_URL`
- `VALIDATE_TOKEN_URL`
- `CHANGE_PASSWORD_URL`
- `CREATE_CLIENT_URL`
- `GET_CLIENT_URL`
- `UPDATE_CLIENT_URL`
- `DELETE_CLIENT_URL`
- `CREATE_PET_URL`
- `GET_PET_URL`
- `UPDATE_PET_URL`
- `DELETE_PET_URL`

---

## Docker

### Construir la imagen

```bash
docker build -t api-gateway .
```

### Ejecutar el contenedor

```bash
docker run -d -p 8000:8000 --env-file .env api-gateway
```

Asegúrate de tener el archivo `.env` con las variables de entorno necesarias.

---

## Ejecución Local

```bash
uvicorn src.main:app --reload --host 0.0.0.0 --port 8000
```

---

## Notas

- Este API Gateway es fácilmente extensible para agregar nuevos microservicios.
- El manejo de errores y validaciones se realiza de forma centralizada para mantener la coherencia en las respuestas.

---

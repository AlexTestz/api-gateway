# 🐾 API Gateway - Pet Host

This project is an **API Gateway** for the Pet Host system, responsible for routing and orchestrating requests between various microservices such as users, clients, and pets.

---

## 🛠️ Technologies Used

- **Language:** Python  
- **Framework:** FastAPI  
- **HTTP Client:** httpx

---

## 🧩 Architecture Style

- **RESTful API:** All endpoints follow RESTful standards for communication.  
- **Microservices:** The API Gateway acts as the single entry point to several independent services.

---

## 🎯 Design Patterns

- **KISS (Keep It Simple, Stupid):** Simple and direct code with no unnecessary complexity.  
- **DRY (Don’t Repeat Yourself):** Functions and configurations are reused to avoid duplication.  
- **SOLID:** Object-oriented design principles ensure the code is maintainable and scalable.

---

## 🏗️ Internal Architecture

- **N-Layered:** Clear separation of routes, business logic, and configuration.  
- **API Gateway Pattern:** Centralizes all external requests and delegates them to the respective microservices.

---

## 🔐 Security

- **JWT (JSON Web Token):** Used to secure endpoints requiring authentication and authorization.  
- **CORS:** Configured to allow requests from specific origins and secure API access.

---

## 🚀 Main Endpoints

- `/api/users/` – User management (register, login, token validation, password change)  
- `/api/clients/` – Client management (create, list, update, delete)  
- `/api/pets/` – Pet management (create, list, update, delete)

---

## 🌐 Environment Variables

Make sure to configure the following environment variables:

```env
REGISTER_USER_URL=
LOGIN_USER_URL=
VALIDATE_TOKEN_URL=
CHANGE_PASSWORD_URL=
CREATE_CLIENT_URL=
GET_CLIENT_URL=
UPDATE_CLIENT_URL=
DELETE_CLIENT_URL=
CREATE_PET_URL=
GET_PET_URL=
UPDATE_PET_URL=
DELETE_PET_URL=


## Docker

### build the docker image

```bash
docker build -t api-gateway .
```

### Ejecutar el contenedor

```bash
docker run -d -p 8000:8000 api-gateway
```

---

## Local execute

```bash
uvicorn src.main:app --reload --host 0.0.0.0 --port 8000
```

---

## Notes

- This API Gateway is easily extensible to add new microservices.
- Error handling and validation are performed centrally to maintain consistency in responses.

---
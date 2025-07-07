## ✅ **Step 2: System Design & Architecture Planning**

This is where tech teams turn business requirements into a **blueprint** of how the system will be built.

---

### 🎯 Goal of Step 2:

> Define **how** the system will work internally:

* Microservices breakdown
* Database design
* API contracts
* Technology stack
* Security architecture
* Communication patterns
* DevOps toolchain

---

## 🔧 Step 2 — Detailed Tasks

### 1. 🧱 **Define Microservices Architecture**

Break the app into microservices based on **bounded context** (Domain-Driven Design):

| Microservice                | Responsibilities                   |
| --------------------------- | ---------------------------------- |
| `user-service`              | Auth, registration, profile, roles |
| `appointment-service`       | Booking/rescheduling/cancel        |
| `doctor-service`            | Schedule, availability             |
| `patient-service`           | Medical records, history           |
| `billing-service`           | Invoice, discounts, tax, insurance |
| `pharmacy-service`          | Inventory, medicine ordering       |
| `notification-service`      | Email/SMS alerts                   |
| `audit-service`             | Log all user/system actions        |
| `api-gateway`               | Route all requests                 |
| `config-server`             | Centralized configuration          |
| `discovery-server (Eureka)` | Service registry & discovery       |

---

### 2. 🗃️ **Database Design (ERD & Normalization)**

Create an **ER Diagram** for each microservice DB — normalized up to 3NF.

Each service has its **own database** (database-per-service pattern).

Examples:

* `patient-service` → `patients`, `medical_records`
* `appointment-service` → `appointments`, `doctor_availability`
* `billing-service` → `invoice`, `invoice_items`, `insurance`

Use tools like:

* Draw\.io / dbdiagram.io / DBeaver for ERD
* Flyway for DB migration management

---

### 3. 🔌 **API Contracts (OpenAPI / Swagger Spec)**

Define API specs **before** development — like a contract between frontend & backend.

Use OpenAPI YAML or Postman collection with:

| API                 | Method | Description      |
| ------------------- | ------ | ---------------- |
| `/api/appointments` | `POST` | Book appointment |
| `/api/users/login`  | `POST` | Login            |
| `/api/bills/{id}`   | `GET`  | Get bill by ID   |

Tools:

* Swagger Editor
* Stoplight
* Postman

---

### 4. 🧰 **Tech Stack Finalization**

| Layer            | Technology                                        |
| ---------------- | ------------------------------------------------- |
| Backend          | Spring Boot 3.4, Spring Security, Spring Data JPA |
| Auth             | JWT, OAuth (optional), RBAC                       |
| Communication    | REST + Kafka                                      |
| DB               | PostgreSQL (prod), H2 (dev/test), Redis (cache)   |
| Frontend         | React + Tailwind/Material UI + Axios              |
| Containerization | Docker + Docker Compose                           |
| API Gateway      | Spring Cloud Gateway                              |
| Discovery        | Eureka                                            |
| Config           | Spring Cloud Config Server                        |
| Tracing          | Zipkin                                            |
| Logs             | ELK or plain file logging                         |

---

### 5. 🔐 **Security Design**

* JWT structure (include roles in claims)
* Spring Security config per service
* Secure endpoints using annotations like `@PreAuthorize`
* CORS config for frontend

---

### 6. 🧪 **Testing Strategy**

* Unit testing: JUnit + Mockito
* Integration testing: Testcontainers / WebTestClient
* Frontend: React Testing Library / Jest
* API testing: Postman / Newman
* Load testing (optional): JMeter / K6

---

### 7. 🚀 **DevOps Plan (CI/CD)**

* GitHub Actions / Jenkins
* Dockerfiles for each service
* Docker Compose for local development
* Git branching strategy (`main`, `dev`, `feature/xyz`)
* Create `README.md` and `.env` templates
* GitHub Projects board for task management

---

### 8. 🗂️ **Create Initial Repo Structure**

```
/medisync360
├── backend/
│   ├── user-service/
│   ├── doctor-service/
│   ├── patient-service/
│   ├── billing-service/
│   ├── ...
├── frontend/
│   ├── src/
│   └── public/
├── config-server/
├── discovery-server/
├── api-gateway/
├── docker-compose.yml
├── docs/
│   ├── SRS.md
│   ├── ERD.drawio
│   └── API-Specs.yaml
```

---

### ✅ Output of Step 2 (Deliverables)

| Asset                                  | Description              |
| -------------------------------------- | ------------------------ |
| ✅ Microservice list & responsibilities | Clear domain separation  |
| ✅ ER diagrams (normalized)             | One per service          |
| ✅ API Contract                         | Swagger/Postman          |
| ✅ Technology Stack                     | Finalized toolchain      |
| ✅ Security Architecture                | JWT + RBAC design        |
| ✅ Docker Setup Plan                    | Ready for containers     |
| ✅ GitHub Structure                     | Repos & branches defined |

---


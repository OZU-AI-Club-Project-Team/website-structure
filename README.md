# API Design & Database Schema

This repository contains the **database schema** (Prisma) and the **API
contract** (OpenAPI) for the upcoming backend of the OZU AI Project Club Website
project.\
The goal is to follow a **design-first** approach: define the data
structures and the API behavior before implementing the backend.

------------------------------------------------------------------------

## 📦 Files

### **1. `prisma.schema`**

Defines the **entire PostgreSQL data model** using Prisma ORM.\
It includes all entities such as:

-   Users & Team Members\
-   Ideas & Presentations\
-   Projects & Members\
-   Applications & Feedback\
-   Auth codes\
-   Enums for roles, statuses, work areas, etc.

This schema represents the **source of truth** for the database
structure.

------------------------------------------------------------------------

### **2. `openapi.yaml`**

A complete **OpenAPI 3.0 specification** describing:

-   All public endpoints\
-   Request/response formats\
-   Authentication flows\
-   Full schemas matching the Prisma models

This file serves as the **API contract** and can be used for:

-   Documentation (Swagger / Redoc)\
-   Mock servers\
-   Code generation (backend stubs or frontend SDKs)

------------------------------------------------------------------------

## 🧪 Running the Fake (Mock) API --- *No backend required*

You can run a **fully working fake API** based on `openapi.yaml` using
Prism.

### **1. Install Prism CLI**

``` bash
npm install -g @stoplight/prism-cli
```

### **2. Start the mock server**

``` bash
prism mock openapi.yaml
```

### **3. The API is now available at**

    http://127.0.0.1:4010

### **4. Example requests**

    GET /project
    GET /project/1
    GET /idea
    GET /application/3
    GET /presentation/2

Prism automatically generates **fake JSON responses** that follow the
OpenAPI contract---perfect for frontend development and early
integration testing.
# API Design & Database Schema

This repository contains the **database schema** (Prisma) and the **API contract** (OpenAPI) for the upcoming backend of the OZU AI Project Club Website project.  
The goal is to follow a **design-first** approach: define the data structures and the API behavior before implementing the backend.

---

## 📁 Project Structure

```
.
├── docs
│   ├── index.html
│   └── openapi.yaml
├── README.md
└── schema.prisma
```

- **schema.prisma** → PostgreSQL database schema  
- **docs/openapi.yaml** → API contract  
- **docs/index.html** → Local Swagger UI viewer  

---

## 📦 Files

### **1. `schema.prisma`**
Defines the **complete database model** using Prisma ORM.

Contains entities such as:
- Users & Team Members  
- Projects & Members  
- Ideas & Presentations  
- Applications & Feedback  
- Auth verification codes  
- Enums (roles, statuses, work areas, etc.)

---

### **2. `openapi.yaml`**
The full **API contract** describing:

- Endpoints  
- Request/response bodies  
- Authentication flows  
- Component schemas aligned with the Prisma models  

Used for:
- API documentation (Swagger / Redoc)  
- Mock server generation  
- Code generation (backend stubs or frontend SDKs)

---

## 🧪 Running the Fake (Mock) API — *No backend required*

You can run a fully functional **mock REST API** using Prism.

### **1. Install Prism CLI**
```bash
npm install -g @stoplight/prism-cli
```

### **2. Start the mock API**
```bash
prism mock docs/openapi.yaml
```

### **3. Mock API will be available at**
```
http://127.0.0.1:4010
```

### **4. Example Requests**
```
GET /project
GET /idea/1
GET /application/5
GET /presentation/3
```

Prism generates fake JSON responses that strictly follow your OpenAPI spec.

---

## 📘 Viewing the API Documentation (Local Swagger UI)

Your project includes a ready‑to‑use Swagger UI page.

### **1. Folder Structure**
```
docs/
  index.html
  openapi.yaml
```

### **2. Start a local static server**
```bash
npx serve docs
```

### **3. Open in browser**
```
http://localhost:3000
```

You will see a fully interactive Swagger UI:

- Tree of endpoints  
- Parameters and schemas  
- Live examples  
- Try-it-out interface  
# Project Repository

## ⚙️ Backend (Django + DRF + Database)

The backend is built using **Django** and **Django REST Framework**, providing a robust, scalable, and API-driven system for managing the complete lifecycle of quality defects.

---

### 🚀 Core Capabilities

* 🔗 **REST API Architecture**

  * Fully RESTful APIs for defects, root cause analysis, and corrective actions
  * Clean separation between frontend and backend

* 🧠 **Workflow Enforcement Logic**

  * Prevents invalid transitions:

    * Cannot move to *In Analysis* without root cause
    * Cannot move to *Actions In Progress* without actions
    * Cannot close defect unless all actions are completed

* 🧾 **Strong Validation**

  * Required field validation
  * Consistent date format (YYYY-MM-DD)
  * Backend-level error handling (400 responses)

---

### 🧩 Data Models (Database Design)

The backend uses a **relational database (SQLite)** with well-structured models:

* 🐞 **Defect**

  * Title, description, severity, priority
  * Status (Open → In Analysis → Actions In Progress → Closed)
  * Area, owner, due date, timestamps

* 🧠 **Root Cause (5-Why)**

  * Stores Why1 → Why5
  * Root cause summary
  * Immediate containment actions

* ✅ **Corrective Actions**

  * Multiple actions per defect
  * Owner, due date, status tracking

* 📜 **Status History**

  * Tracks all workflow transitions for audit

---

### 🔗 Relationships

* One Defect → Multiple Corrective Actions
* One Defect → One Root Cause Analysis
* One Defect → Multiple Status History entries

---

### ⚡ Key Backend Features

* 📊 **Dashboard APIs**

  * Provides aggregated metrics:

    * Total defects
    * Open / Closed
    * Overdue actions

* ⏰ **Overdue Logic**

  * Detects actions past due date
  * Calculates delay (days overdue)

* 📥 **CSV Export API**

  * Generates downloadable reports
  * Supports audit and reporting needs

* 🌱 **Demo Data Seeding**

  * Generates 20+ realistic defects
  * Includes mixed statuses, severities, overdue cases
  * Pre-populated root cause & corrective actions

---

### 🛠️ Database & Migrations

* Uses **SQLite** for development/demo
* Managed via Django migrations
* Includes repair command for migration sync issues

```bash
python manage.py repair_sqlite_migrations
python manage.py migrate
python manage.py seed_demo_data
```

---

### 🔐 Reliability & Integrity

* Enforced foreign key relationships
* Prevents incomplete or inconsistent data
* Structured API responses for frontend integration

---

### 🔗 Integration

* Seamlessly connected with React frontend
* Uses REST APIs for real-time data flow
* Supports scalable architecture

---

### 💡 Why This Backend Stands Out

* Not just CRUD → full **workflow-driven system**
* Enforces **real-world quality processes**
* Supports **audit, reporting, and analytics**
* Designed for **scalability and production readiness**

---

🔥 *This backend ensures structured defect tracking, accurate root cause analysis, and complete corrective action management.*

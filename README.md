# ⚖️ IURIS — Legal Case Management System

> **Software that adapts to your workflow — not the other way around.**

[![Java EE](https://img.shields.io/badge/Java_EE-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.java.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com)

---

## 📌 About

**IURIS** is a legal case management platform built between **2016 and 2017**, currently in **active production use** by a law firm. It was designed with one core principle: the software adapts to how each team works, not the other way around.

Whether you're a solo attorney, a small firm, or a large legal team, IURIS scales to your process without forcing you to change it.

> ⚠️ IURIS was not originally designed to be bilingual. Some parts of the interface may appear in Spanish and English simultaneously.

---

## ✨ Features

- 📂 Flexible case management with unlimited custom stages per case, each with tasks, notes, events, files and a full audit timeline
- 🔐 Granular per-user access control — define who edits, who reads, and delegate administrative tasks without exposing sensitive data
- ☁️ Microsoft 365 integration via Graph API — files stored in OneDrive/SharePoint with encoded folder names and user-level permissions synchronized between IURIS and SharePoint
- 📄 Case-type document template banks — open a case and minimum required documents load automatically
- 👥 Contact groups per case — all relevant parties visible at a glance
- 💰 Per-case financial tracking — budget estimation, income/expense records and future billing date management
- 📅 Shared calendar with event scheduling, attendee management and administrative delegation
- 📊 Consolidated reporting on cases, stages, tasks and financials
- 🕵️ Vertical audit timeline per case stage showing every action, by whom, and when
- 🎓 In-app help module with video guides for key workflows

---

## 🏗️ Architecture

IURIS is built as a Java EE enterprise application packaged as an **EAR**, composed of three modules: the EJB module handling all business logic and persistence via JPA/EclipseLink, the web module exposing the JSF interface, and the EAR module orchestrating the deployment.

Business logic is exposed through **REST services**, designed with future decoupling from JSF in mind. Authentication and authorization are managed internally with role-based access control, where permissions are defined at the user level and propagated to file operations in SharePoint.

File storage is handled through the **Microsoft Graph API** — when a case is created, IURIS automatically provisions an encoded folder structure in OneDrive/SharePoint tied to the user's Microsoft account, keeping documents organized, secure, and accessible online without local copies.

**RabbitMQ** acts as a message broker between IURIS and the Microsoft Graph API, ensuring that file operations are not lost in case of connectivity failures — guaranteeing eventual consistency between the application and the cloud storage layer.

---

## 🛠️ Stack

| Layer | Technology |
|---|---|
| Backend | Java 8, Java EE, EJB, Spring Boot 2.7, Spring Security 5 |
| Frontend | JSF 2.3, PrimeFaces 8, PrettyFaces |
| Persistence | JPA / EclipseLink |
| Database | PostgreSQL |
| Cache / Sessions | Redis |
| Async Messaging | RabbitMQ |
| Server | WildFly 18 |
| Reports | JasperReports |
| Observability | Grafana, Prometheus, Loki* |
| Deploy | Docker, Railway, GitHub Actions CI/CD |

*Observability stack configured locally. Not deployed in demo environment due to Railway free tier limitations.*

---

## 🌐 Live Demo

🌐 Live demo available — explore the full feature set with the credentials below.

[![Live Demo](https://img.shields.io/badge/Live_Demo-7B2FBE?style=for-the-badge&logo=railway)](https://iuris-porfolio.up.railway.app/login)

**Demo credentials — user:** `demo` **/ password:** `demo`

---

## 🚀 Roadmap

- [ ] 🎨 UI modernization — React + PrimeReact + Tailwind CSS
- [ ] ☕ Backend migration to Java 21 + Spring Boot 3 + Spring Security 6
- [ ] 🤖 AI-powered legal assistant — RAG architecture combining an LLM with case-specific context retrieved from a Qdrant vector database. Attorneys and staff will interact with cases through a natural language chat interface — querying case status, retrieving documents, creating tasks or scheduling events conversationally. The assistant is exposed via MCP, with the AI layer implemented in Python
- [ ] 📁 Google Workspace integration
- [ ] 📱 Mobile-friendly responsive redesign

---

## 📸 Screenshots

> *(Coming soon)*

---

## 📄 License

Private project. Source code not publicly available.
Developed and maintained by the author. Currently in active production use by a law firm.

This deployment is a **demo environment** intended to showcase technical capabilities.

---

## 📬 Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Peter%20Campos-0077B5?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/peter-campos)
[![Email](https://img.shields.io/badge/Email-peter.campos.leon%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:peter.campos.leon@gmail.com)


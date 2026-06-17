<div align="center">

# 🎓 MITS NbN Portal: Campus Operating System

![One-Desk Logo](https://img.shields.io/badge/MITS-One--Desk-blue?style=for-the-badge&logo=graduation-cap&logoColor=white)

**The Official Centralized Administrative Portal for Madhav Institute of Technology & Science (MITS)**

[![React](https://img.shields.io/badge/React-18.2.0-61DAFB?style=for-the-badge&logo=react)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18.0.0+-43853D?style=for-the-badge&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-7.0-4EA94B?style=for-the-badge&logo=mongodb)](https://mongodb.com/)
[![Redis](https://img.shields.io/badge/Redis-7.0-DC382D?style=for-the-badge&logo=redis)](https://redis.io/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)




## 🚀 Live Demo

<div align="center">

[![Live Demo](https://img.shields.io/badge/Live%20Portal-View%20Project-green?style=for-the-badge&logo=globe)](https://nbn.mitsgwalior.in)

</div>

---

</div>

<div>

## 📋 Table of Contents

- [🌟 Project Overview](#-project-overview)
- [🎯 Key Features](#-key-features)
- [🏗️ System Architecture](#️-system-architecture)
- [🛠️ Tech Stack](#️-tech-stack)
- [👥 User Roles & RBAC](#-user-roles--rbac)
- [🚀 Quick Start](#-quick-start)
- [📦 Installation](#-installation)
- [🔧 Configuration](#-configuration)
- [🔐 Security Features](#-security-features)
- [📈 Analytics & Reporting](#-analytics--reporting)
- [👨‍💻 Developer](#-developer)

---
</div>

## 🌟 Project Overview

<div align="center">

**MITS One-Desk** is a mission-critical, enterprise-grade application that revolutionizes campus administration by digitizing the entire lifecycle of student clearances, certifications, and institutional analytics.

### 🎯 Mission
> *"Replacing fragmented, paper-based processes with a high-performance, real-time digital ecosystem built on modern web technologies."*

</div>

### 📊 **What does One-Desk Manage?**

- **📄 Document Management** - Multi-stage approval workflows for NOC, No-Dues, and Bonafide Certificates
- **🎓 Alumni Services** - Post-graduation requests, document management, and exit surveys
- **🏢 Placement Integration** - Company directory, offer letter verification, and internship domains
- **📊 Advanced Analytics** - Real-time statistics, department-wise metrics, and performance reporting

---

## 🎯 Key Features

<div>

### 🎓 **Student & Administrative Services**
- **📄 Automated Clearances** - 6-stage sequential multi-department approval pipeline for No-Dues
- **📜 Instant Certificates** - Dynamic PDF generation with tamper-proof QR code verification
- **💼 NOC Management** - Conditional routing and multi-stage verification from T&P Office to HOD
- **👥 Batch Management** - Student grouping, progression tracking, and mass communications

### ⚡ **Real-Time Ecosystem**
- **🔄 Instant Sync** - WebSocket-powered live status tracking across all dashboards
- **🔔 Notification Engine** - Automated email alerts and in-app notifications
- **🚀 High Availability** - Redis caching layer for near-instant dashboard rendering

### 📊 **Enterprise Analytics**
- **📈 Department Dashboards** - Visualize request volumes, completion rates, and bottlenecks
- **📋 Placement Stats** - Track internship distribution, tier-based companies, and domains
- **📑 Custom Reports** - Export data in multiple formats for accreditation and auditing

### 🔐 **Advanced Security**
- **🔑 SSO Integration** - Secure Google OAuth 2.0 with domain restriction
- **🛡️ RBAC Authorization** - 10+ distinct user roles with fine-grained permission control
- **🔒 Document Security** - Encrypted cloud storage, virus scanning, and unique certificate hashes

</div>

---

## 🏗️ System Architecture

<div align="center">

### 🎯 **Distributed Architecture**

```mermaid
graph TB
    subgraph "Client Layer"
        A[React App] -->|WebSocket| B[Socket.IO Server]
        A -->|REST APIs| C[API Gateway]
    end
    
    subgraph "Middleware Layer"
        C --> D[Auth & RBAC]
        C --> E[Rate Limiting]
    end
    
    subgraph "Service Layer"
        D --> F[Clearance Engine]
        D --> G[Certificate Generator]
        D --> H[Analytics Service]
    end
    
    subgraph "Data & Persistence"
        F --> I[(MongoDB)]
        H --> J[(Redis Cache)]
        G --> K[Cloud Storage]
    end
    
    subgraph "External Services"
        C -.-> L[Google OAuth]
        G -.-> M[Puppeteer / Headless Chrome]
        F -.-> N[Nodemailer]
    end
```

### 🔄 **Multi-Stage Approval Pipeline (No-Dues)**

```mermaid
stateDiagram-v2
    [*] --> Submitted
    Submitted --> Coordinator_Review
    Coordinator_Review --> Library_Clearance
    Library_Clearance --> Hostel_Clearance
    Hostel_Clearance --> Lab_Clearance
    Lab_Clearance --> T&P_Clearance
    T&P_Clearance --> General_Office
    General_Office --> Accounts
    Accounts --> Certificate_Generated
    Certificate_Generated --> [*]
```

</div>

---

## 🛠️ Tech Stack

<div align="center">

### 🎨 **Frontend Technologies**

| Technology | Purpose | Badge |
|------------|---------|-------|
| **React** | UI Framework | ![React](https://img.shields.io/badge/React-18-61DAFB?style=flat&logo=react) |
| **Vite** | Build Tool | ![Vite](https://img.shields.io/badge/Vite-5-646CFF?style=flat&logo=vite) |
| **Tailwind CSS** | Styling | ![Tailwind](https://img.shields.io/badge/Tailwind-3-38B2AC?style=flat&logo=tailwind-css) |
| **Framer Motion**| Animations | ![Framer](https://img.shields.io/badge/Framer_Motion-12-0055FF?style=flat&logo=framer) |
| **Socket.IO** | Real-time | ![Socket.IO](https://img.shields.io/badge/Socket.IO-Client-010101?style=flat&logo=socket.io) |

### ⚙️ **Backend Technologies**

| Technology | Purpose | Badge |
|------------|---------|-------|
| **Node.js** | Runtime | ![Node.js](https://img.shields.io/badge/Node.js-18+-43853D?style=flat&logo=node.js) |
| **Express.js**| Framework | ![Express](https://img.shields.io/badge/Express-4-000000?style=flat&logo=express) |
| **MongoDB** | Database | ![MongoDB](https://img.shields.io/badge/MongoDB-7-4EA94B?style=flat&logo=mongodb) |
| **Redis** | Cache Layer | ![Redis](https://img.shields.io/badge/Redis-7-DC382D?style=flat&logo=redis) |
| **Puppeteer** | PDF Gen | ![Puppeteer](https://img.shields.io/badge/Puppeteer-PDF-40B5A4?style=flat&logo=puppeteer) |

</div>

---

## 👥 User Roles & RBAC

<div align="center">

### 🔐 **Granular Access Control**

| Role | Core Responsibilities | Access Level |
|------|-----------------------|--------------|
| **👨‍🎓 Student** | Submit requests, download certificates, exit surveys | Limited |
| **👨‍🏫 HOD** | Approve department requests, view analytics | Departmental |
| **📋 Coordinator** | Screen batch requests, manage students | Batch Level |
| **💼 T&P Office** | Manage NOCs, placements, company directories | Departmental |
| **🏫 Library/Hostel/Lab** | Verify specific clearances in the No-Dues pipeline | Specialized |
| **💰 Accounts** | Final financial clearance | Specialized |
| **👨‍💼 Admin/Registrar** | Full system configuration, global analytics | Complete |

</div>

---

## 🚀 Quick Start

<div align="center">

### ⚡ **One-Command Setup**

```bash
# Clone the repository
git clone https://github.com/Amit-akm-22/MITS-One-Desk.git
cd MITS-One-Desk

# Install dependencies and start development servers
npm install
npm run dev
```

</div>

---

## 📦 Installation

### 📋 **Step-by-Step Installation**

#### 1. **Clone Repository**
```bash
git clone https://github.com/Amit-akm-22/MITS-One-Desk.git
cd MITS-One-Desk
```

#### 2. **Install Dependencies**
```bash
# Backend
cd backend
npm install

# Frontend
cd ../frontend
npm install
```

#### 3. **Environment Configuration**
Create `.env` in the `backend` and `frontend` directories based on the configuration guide below.

#### 4. **Database & Cache**
```bash
# Ensure MongoDB is running
mongod

# Ensure Redis is running
redis-server
```

#### 5. **Start Application**
```bash
# Terminal 1: Backend
cd backend
npm run dev

# Terminal 2: Frontend
cd frontend
npm run dev
```

---

## 🔧 Configuration

### 🔐 **Backend Variables (`backend/.env`)**
```bash
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/mits-onedesk

REDIS_HOST=localhost
REDIS_PORT=6379

JWT_SECRET=your_super_secret_jwt_key
GOOGLE_CLIENT_ID=your_google_client_id

MAIL_USER=your_email@gmail.com
MAIL_PASS=your_app_password

FRONTEND_URL=http://localhost:5173
```

### 🖥️ **Frontend Variables (`frontend/.env.local`)**
```bash
VITE_API_BASE_URL=http://localhost:5000/api
VITE_SOCKET_URL=http://localhost:5000
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

---

## 🔐 Security Features

<div align="center">

| Feature | Implementation | Purpose |
|---------|----------------|---------|
| **JWT & OAuth** | HttpOnly Cookies + Bearer Tokens | Secure Session Management |
| **QR Verification** | Cryptographic hashes on PDFs | Anti-Forgery measure |
| **CORS & Rate Limiting** | Express middleware | DDoS & Scraping protection |
| **File Scanning** | Multer validation | Malicious upload prevention |

</div>

---

## 📈 Analytics & Reporting

<div align="center">

- **Real-time Dashboards:** Leveraging Redis for instantaneous metric aggregations.
- **Placement Insights:** Deep tracking of student internships grouped by company, tier, and domain.
- **Workflow Bottlenecks:** Tracking average clearance times per department to optimize campus operations.

</div>

---

## 👨‍💻 Developer

<div align="center">

<table>
<tr>
<td align="center" width="270px">
<img src="https://github.com/Amit-akm-22.png" width="100px;" alt="Amit Vishwakarma"/><br />
<sub><b>Amit Manmode</b></sub><br />
<sub>Full-Stack Developer</sub><br />
<br/>
<a href="https://github.com/Amit-akm-22">
  <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a><br/>
<a href="https://www.linkedin.com/in/amit-manmode-0975ab280">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>
</td>
</table>

> *"Building scalable systems to empower educational institutions through technology."*

</div>

<div align="center">

**🎓 Made with ❤️ for MITS Gwalior**

[![One-Desk](https://img.shields.io/badge/MITS-One--Desk-blue?style=for-the-badge&logo=graduation-cap)](https://github.com/Amit-akm-22/MITS-One-Desk)

**🌟 Star this repository if you find it helpful!**

</div>
gazers)
[![GitHub Forks](https://img.shields.io/github/forks/Amit-akm-22/MITS-One-Desk?style=social)](https://github.com/Amit-akm-22/MITS-One-Desk/network/members)
[![GitHub License](https://img.shields.io/github/license/Amit-akm-22/MITS-One-Desk)](https://github.com/Amit-akm-22/MITS-One-Desk/blob/main/LICENSE)

---

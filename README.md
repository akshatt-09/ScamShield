# 🛡️ ScamShield AI

### AI-Assisted Scam Detection & Risk Analysis Platform

ScamShield AI is a full-stack security platform designed to help users identify potentially fraudulent **messages, screenshots, and URLs**.

It combines **deterministic security checks** with **AI-assisted analysis** to provide users with understandable risk assessments, explanations, and actionable insights.

> **Detect → Explain → Protect**

---

## ✨ Features

### 🔍 Multi-Input Analysis

* Analyze suspicious text messages
* Upload and analyze screenshots
* Perform safe static URL analysis
* Extract URLs from messages
* Detect suspicious patterns and phishing indicators

### 🧠 AI-Assisted Risk Analysis

* Risk score
* Risk level
* Classification
* Confidence information
* Threat assessment and explanation

### 🔐 Authentication & Security

* JWT-based authentication
* Protected API routes
* Password hashing with bcrypt
* Request validation
* Rate limiting
* Helmet security headers
* CORS configuration
* Environment-based secret management

### 📊 Dashboard & History

* Analysis statistics
* Previous analysis history
* User-specific analysis records
* Dashboard overview
* Persistent analysis results

---

## 🏗️ Architecture

```text
                    ┌──────────────────┐
                    │   User / Browser │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ React + Vite     │
                    │    Frontend      │
                    └────────┬─────────┘
                             │
                        REST / HTTPS
                             │
                             ▼
                    ┌──────────────────┐
                    │ Node.js +        │
                    │ Express Backend  │
                    └───────┬───┬──────┘
                            │   │
                    ┌───────┘   └────────┐
                    ▼                    ▼
            ┌──────────────┐     ┌─────────────────┐
            │ PostgreSQL   │     │ AI Intelligence │
            │ + Prisma     │     │    Service      │
            └──────────────┘     └────────┬────────┘
                                          │
                                          ▼
                                   ┌─────────────┐
                                   │ AI Provider │
                                   └─────────────┘
```

The application separates the **frontend, backend, database, and AI intelligence service** into dedicated layers.

---

## 🧠 Analysis Pipeline

```text
User Input
    ↓
Input Validation
    ↓
Content Preparation
    ↓
┌──────────────────────┐
│ Deterministic Checks │
│         +            │
│   AI Analysis        │
└──────────┬───────────┘
           ↓
    Risk Assessment
           ↓
    Result Validation
           ↓
       Database
           ↓
        History
```

AI responses are validated before being used as application results, while AI failures and invalid responses are handled as controlled application errors.

---

## 🛠️ Tech Stack

### Frontend

* React
* Vite
* Tailwind CSS
* React Router DOM
* Axios
* Recharts
* Framer Motion
* Lucide React

### Backend

* Node.js
* Express.js
* Prisma ORM
* PostgreSQL
* JWT
* bcryptjs
* Multer
* Helmet
* CORS
* express-rate-limit

### AI Layer

* Node.js
* Zod
* Configured AI Provider

The technologies above are documented as the project's frontend, backend, and AI stack.

---

## 📂 Project Structure

```text
ScamShield/
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── routes/
│   │   └── services/
│   ├── prisma/
│   └── package.json
│
├── ai-intelligence/
│   ├── src/
│   │   ├── config/
│   │   ├── providers/
│   │   ├── prompts/
│   │   ├── risk/
│   │   ├── schemas/
│   │   └── services/
│   └── package.json
│
├── docker-compose.yml
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have:

* Node.js
* npm
* PostgreSQL

Docker can also be used for the containerized setup.

### 1. Clone the Repository

```bash
git clone <repository-url>
cd ScamShield
```

### 2. Install Dependencies

**Frontend**

```bash
cd frontend
npm install
```

**Backend**

```bash
cd ../backend
npm install
```

**AI Intelligence Service**

```bash
cd ../ai-intelligence
npm install
```

### 3. Configure Environment Variables

Create the required environment files:

```text
backend/.env
ai-intelligence/.env
```

Configure the database, authentication, AI provider, and service URLs using the variables provided in the project's `.env.example` files.

### 4. Setup Database

```bash
npx prisma generate
npx prisma migrate dev
```

### 5. Start Services

**AI Service**

```bash
cd ai-intelligence
npm run dev
```

Runs on:

```text
6100
```

**Backend**

```bash
cd backend
npm run dev
```

Runs on:

```text
5000
```

**Frontend**

```bash
cd frontend
npm run dev
```

Runs on:

```text
5173
```

---

## 🔒 Security

ScamShield follows a defense-in-depth approach combining deterministic security checks with AI-assisted analysis.

Security controls include:

* JWT authentication
* Password hashing
* Protected routes
* Input validation
* File type and size validation
* Rate limiting
* Helmet security headers
* CORS configuration
* Sanitized API errors
* Server-side AI credentials
* Environment-based secrets

Screenshot uploads currently support **PNG, JPEG/JPG, and WEBP**, with a maximum size of **10 MB**.

---

## ⚠️ Disclaimer

ScamShield AI is a **risk-assessment and decision-support tool**, not a definitive cybersecurity authority.

AI-generated results may be incorrect. A high-risk result does not prove that content is malicious, and a low-risk result does not guarantee that content is safe.

Always independently verify suspicious communications and never share passwords, OTPs, payment credentials, or other sensitive information solely because an automated system reports low risk.

---

## 🔮 Future Improvements

Planned improvements include:

* Advanced URL intelligence
* Domain reputation integration
* Multilingual scam detection
* Improved OCR pipelines
* Expanded threat-intelligence sources
* More detailed explainability
* Enhanced analytics
* Automated security testing
* Monitoring and observability

These are planned improvements and are not represented as currently implemented features.

---

## 👥 Team

### ScamShield AI — CodeStorm 2026: FutureForge

**Team Size:** 4 Developers

| Role                        | Responsibility           |
| --------------------------- | ------------------------ |
| Full-Stack / Backend        | Backend & API            |
| Frontend                    | UI & Frontend            |
| AI / Intelligence           | AI Analysis              |
| Database / DevOps / Testing | Infrastructure & Testing |

---

## 🎯 Project Goal

> **Detect → Explain → Protect**

ScamShield AI aims to make suspicious online content easier to understand by combining security checks, AI-assisted analysis, and clear risk explanations.

---

### Built for CodeStorm 2026 — FutureForge 🛡️

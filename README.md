# 🦁 Beast AI Initiative — Khan Chacha MRMS

### Non-Technical Students → Production-Ready Full Stack App Using AI as a Co-Programmer

<br/>

> **"You don't need to be a programmer to build one. You need to understand what you're building — and have the right AI partner beside you."**
> — Raushan Ranjan, MCT & Iconic Corporate Trainer, Koenig Solutions

---

## What This Programme Is

**Beast AI Initiative** is a live enterprise training programme designed and delivered by **Raushan Ranjan**, Microsoft Certified Trainer (MCT) at **Koenig Solutions**, Noida.

The programme teaches **non-technical professionals** — analysts, operations managers, project coordinators, and business teams — how to build a complete, production-ready mobile application from scratch using **Claude AI as an AI pair-programmer** (vibe coding). No prior programming experience required.

By the end of the programme, every student has:

- A fully functional **Flutter mobile app** running on Android, iOS, and Windows
- A **Node.js REST API** with 8 endpoints connecting the app to a real database
- A **PostgreSQL database** with a production-grade schema, seeded with real data
- A clear understanding of how to **migrate real Google Sheets data** into the database
- Knowledge of **environments, app export, and security** before going live

---

## The Client App — Khan Chacha MRMS

The app built during this programme is a real-world use case: a **Maintenance Request Management System (MRMS)** for **Khan Chacha**, a multi-outlet restaurant chain operating across Delhi NCR.

Khan Chacha previously managed maintenance requests through Google Forms → Google Sheets. The Beast AI Initiative replaces that with a proper app — role-based login, real-time request tracking, outlet-level dashboards, status history, and image attachments.

### App Screens

| Screen | Role | What it does |
|--------|------|--------------|
| Login | All | Role-based authentication (manager / staff) |
| Dashboard | All | Status counts (Open / Pending / Closed), recent requests |
| Request List | All | Filter, search, pull-to-refresh, swipe-to-delete |
| Detail | All | Full request view, status update with history log |
| New/Edit Request | Manager | Create or edit a request with image attachment |

### User Roles

| Role | Account | Outlet |
|------|---------|--------|
| Manager | manager / manager123 | Connaught Place (OUT-01) |
| Staff | staff / staff123 | Lajpat Nagar (OUT-02) |

---

## Programme Structure

| Day | Topic | What Students Build |
|-----|-------|---------------------|
| **Day 1** | Flutter Foundations | First app, widgets, hot reload, first Claude Code prompts |
| **Day 2** | Full App + Prompting Patterns | All 5 screens, role-based auth, animations, image picker |
| **Day 3** | Real Database — PostgreSQL | Schema design, 3-table structure, seeded data, Flutter ↔ DB |
| **Day 4** | API Layer — Node.js + Express | REST API with 8 endpoints, Flutter switches to HTTP calls |
| **Day 5** | Build, Export & Deploy | APK/IPA export, AWS deployment, security checklist |

---

## Tech Stack

```
Flutter (Dart)          → Mobile & desktop app — Android, iOS, Windows
Node.js + Express       → REST API layer — 8 endpoints, runs on AWS
PostgreSQL              → Relational database — local dev → AWS RDS
Claude Code             → AI pair-programmer — every prompt documented
http (Dart package)     → Flutter HTTP client
pg (npm package)        → Node.js PostgreSQL client
dotenv + cors           → API configuration and security
```

### Architecture

```
User's Device (Android / iOS / Windows)
  └── Flutter App (khan_chacha_mrms/)
        └── ApiService.dart
              │ HTTP / JSON over HTTPS
              ▼
          Node.js API (khan_chacha_api/) — AWS EC2
              ├── routes/requests.js   GET/POST/PUT/PATCH/DELETE
              ├── routes/auth.js       POST /auth/login
              ├── routes/dashboard.js  GET /dashboard/counts
              └── db/connection.js     pg Pool
                    │ PostgreSQL wire protocol
                    ▼
              AWS RDS — PostgreSQL
                    ├── outlets
                    ├── users
                    └── maintenance_requests
```

---

## Training Handbooks

All session content is published as interactive HTML handbooks. Each handbook has tabbed navigation, copy-to-clipboard Claude Code prompts, architecture diagrams, and Q&A sections built from real session questions.

| File | Content | Tabs |
|------|---------|------|
| `index.html` | Programme landing page — all sessions, timeline, tech stack | — |
| `day1.html` | Flutter Foundations | 11 tabs |
| `day2.html` | Full App Build + Prompting Patterns | 11 tabs |
| `full-app-guide.html` | Complete 5-screen MRMS — step-by-step + capstone | 4 tabs |
| `day3.html` | PostgreSQL On-Premises + Go-Live Supabase | 14 tabs |
| `day4.html` | API Layer — Node.js + Express | 10 tabs |
| `pre-launch-guide.html` | Sheets Migration · Environments · App Export · Security | 4 tabs |

### What makes these handbooks different

- **Why-before-how** — every concept is explained in plain English before any code appears
- **Claude Code prompts** — every build step is a copy-paste prompt, not a tutorial to follow blindly
- **Real errors documented** — Q&A sections capture actual errors from live sessions and their fixes
- **Capstone prompts** — each day includes a single large prompt that builds the entire day's work in one shot, alongside the step-by-step version
- **Raushan's teaching philosophy** — built around "Why Before How", the approach that has worked across 40+ enterprise organisations and 25+ countries

---

## Project Structure

```
khan_chacha_mrms/            ← Flutter app
├── lib/
│   ├── main.dart
│   ├── models/
│   │   ├── maintenance_request.dart
│   │   └── user_account.dart
│   ├── screens/
│   │   ├── login_screen.dart
│   │   ├── dashboard_screen.dart
│   │   ├── request_list_screen.dart
│   │   ├── detail_screen.dart
│   │   └── request_form_screen.dart
│   ├── services/
│   │   ├── api_service.dart      ← HTTP calls to Node.js API
│   │   ├── auth_service.dart     ← Login gatekeeper
│   │   └── navigation_service.dart
│   └── widgets/
│       └── request_card.dart
├── db/
│   ├── schema.sql               ← PostgreSQL schema
│   └── seed.sql                 ← Seed data
└── pubspec.yaml

khan_chacha_api/             ← Node.js REST API
├── server.js                ← Entry point
├── .env                     ← Credentials (never committed)
├── routes/
│   ├── requests.js          ← CRUD for maintenance requests
│   ├── auth.js              ← Login endpoint
│   └── dashboard.js         ← Status counts
└── db/
    └── connection.js        ← PostgreSQL pool
```

---

## API Endpoints

| Method | Endpoint | What it does |
|--------|----------|--------------|
| `GET` | `/api/requests` | Fetch all requests (with outlet + user JOIN) |
| `GET` | `/api/requests?outlet_id=OUT-01` | Fetch by outlet (for staff role) |
| `GET` | `/api/requests/:id` | Fetch single request |
| `POST` | `/api/requests` | Create new request |
| `PUT` | `/api/requests/:id` | Update all fields |
| `PATCH` | `/api/requests/:id/status` | Update status + append history |
| `DELETE` | `/api/requests/:id` | Delete a request |
| `POST` | `/api/auth/login` | Authenticate user |
| `GET` | `/api/dashboard/counts` | Status counts (GROUP BY) |

---

## Running Locally

### Prerequisites

- Flutter SDK (latest stable)
- Node.js v18+
- PostgreSQL 14+
- Claude Code (`npm install -g @anthropic-ai/claude-code`)

### API Server

```bash
cd khan_chacha_api
npm install
cp .env.example .env        # fill in your PostgreSQL credentials
npm run dev                 # starts on http://localhost:3000
```

### Database Setup

```bash
psql -U postgres -c "CREATE DATABASE khan_chacha;"
psql -U kc_app -d khan_chacha -f db/schema.sql
psql -U kc_app -d khan_chacha -f db/seed.sql
```

### Flutter App

```bash
cd khan_chacha_mrms
flutter pub get
flutter run -d windows      # or -d emulator / -d chrome
```

> **Note:** The API must be running before launching the Flutter app. Change `_baseUrl` in `lib/services/api_service.dart` to match your run target (see Day 4 handbook for platform-specific URLs).

---

## About the Trainer

**Raushan Ranjan** is an Iconic Corporate Trainer and Microsoft Certified Trainer (MCT) at **Koenig Solutions**, Noida, where he manages a team of four MCTs and delivers enterprise ILT/VILT training across **25+ countries**.

He is also the founder of **RR Skillverse** ([rrskillverse.in](https://rrskillverse.in)) — an independent EdTech platform — and co-founder of **The Soft Grid**, a D2C apparel and corporate gifting brand.

### Training Specialisations

- Azure, Power Platform, Microsoft 365
- .NET / Blazor / Clean Architecture
- AI Engineering (Azure OpenAI, Claude, Copilot Studio)
- Flutter / Mobile Development
- Graphics Programming (OpenGL / Vulkan)

### Enterprise Delivery Highlights

- **40+ Microsoft certifications** held
- **11+ years** in education, **4+ years** in enterprise ILT/VILT
- **40+ organisations** trained including sovereign governments, central banks, and Fortune 500 enterprises
- **Global client roster:** Central Bank of Nigeria, World Bank Group, US Navy, Finance Ministry Riyadh, DEWA, GOSI, UN Italy, Paris Saint-Germain FC, and many more
- Delivered sessions across the Middle East, Europe, Africa, and South Asia

### Teaching Philosophy — "Why Before How"

Every session Raushan delivers follows one principle: students must understand *why* something works before they learn *how* to implement it. This is especially critical in AI-assisted development — you cannot responsibly use a tool you don't understand. The Beast AI Initiative is built entirely on this philosophy.

---

## AI Agents Built by Raushan (Separate from this Programme)

As part of the **Koenig AI Agents** and **RR Skillverse** initiatives, Raushan has built and deployed:

| Agent | What it does | Stack |
|-------|-------------|-------|
| **RRPULSE** | Microsoft ecosystem update scanner | Azure App Service, Python |
| **Ask SOT** | Internal Koenig SOT chatbot with auth gate | FastAPI, ChromaDB, MongoDB Atlas |
| **AI Academy** | Microsoft certification learning portal with on-demand AI-generated lessons | Azure OpenAI, Next.js |
| **KiteKonnect** | Client connection and engagement tool | Node.js, Azure |
| **SMI Agent** | Social media intelligence tool | Python, Azure OpenAI |
| **AI Tools Hub** | Internal portal consolidating all agents | React, Azure |

---

## Programmes & Platforms

| Platform | Link |
|----------|------|
| RR Skillverse | [rrskillverse.in](https://rrskillverse.in) |
| Koenig Solutions | [koenig-solutions.com](https://www.koenig-solutions.com) |
| GitHub | [github.com/raushan1107](https://github.com/raushan1107) |
| Email | raushanr1107@gmail.com |

---

## Brand

```
Primary teal:   #00c2e0
Deep teal:      #0082A0
Dark navy:      #0d1117
Amber:          #f59e0b
Orange:         #e88c1f

Typography:
  Headings:  Space Grotesk
  Body:      Inter
  Code:      IBM Plex Mono / JetBrains Mono
```

---

## Licence

This training material is proprietary content created for Koenig Solutions enterprise training delivery and RR Skillverse programmes.

The **Khan Chacha MRMS** application code built during sessions is available to enrolled students for learning and portfolio purposes.

---

<div align="center">

**Beast AI Initiative** · Khan Chacha MRMS Training Programme · 2026

Built with ❤️ by [Raushan Ranjan](https://rrskillverse.in) · Koenig Solutions × RR Skillverse

*Turning non-technical professionals into confident app builders — one Claude Code prompt at a time.*

</div>

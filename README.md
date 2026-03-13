<div align="center">

# 🏛️ York REM

### Student Enrolment Portal — Redesigned

A ground-up redesign of York University's Registration & Enrolment Module,<br/>
reimagining the student portal as a modern, unified academic platform.

<br/>

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Recharts](https://img.shields.io/badge/Recharts-8884d8?style=for-the-badge&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)

<br/>

> ⚠️ **Work in Progress** — What you see here is the completed frontend design.<br/>
> The backend (Supabase, real York API integration, and persistence) is currently in development.

<br/>

![Designed for](https://img.shields.io/badge/Designed_for-York_University_Students-C8102E?style=flat-square)
![Supports](https://img.shields.io/badge/🇨🇦_Supports-Canadian_Domestic_Tuition-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Frontend_Complete_|_Backend_In_Progress-orange?style=flat-square)

</div>

---

## 🚦 Project Status

This repository currently contains the **fully designed and functional frontend**. The app lets students search and filter 130+ real York courses, enrol/drop with a live cart, track degree progress, view financial breakdowns, browse scholarships, find campus jobs, and discover research positions — all running client-side.

The **backend is still in development** and will be built using:

- 🟢 **Supabase** — PostgreSQL database, authentication, and realtime subscriptions
- 🔗 **York Course API** — real course catalog data via Yoki / York Open Data
- ⚡ **Vercel** — deployment and edge functions
- More tools to be added as the backend takes shape

Once connected, the backend will power real data persistence, live seat tracking, and multi-session enrolment state behind the UI you see today.

---

## 🎯 Who Is This For?

This tool is designed for **York University students** frustrated with the current REM system — a fragmented, outdated interface that forces them to bounce between multiple disconnected portals for basic academic tasks.

The idea is simple: **one portal for everything**. Enrol in courses, check your finances, plan your budget, find scholarships, browse campus jobs, and track your degree — all without leaving the app.

---

## ❌ The Problem

York's current system suffers from:

| Issue | Impact |
|---|---|
| **Fragmented workflows** | Students bounce between REM, financial services, degree audit, and career portals |
| **Cluttered interface** | Too many nav elements competing for attention — students can't find what they need |
| **Poor course discovery** | Weak search/filter, no real-time seat tracking, no conflict detection |
| **No financial integration** | Tuition estimates, budgeting, and scholarships don't exist in the same ecosystem |
| **Missing career tools** | Jobs, research positions, and work-study listings scattered across separate systems |

---

## ✅ The Solution

York REM (Redesigned) consolidates every core student workflow into a **single, modern web application** with a clean 3-column enrolment layout, a slim icon-rail sidebar, and secondary features organized under a "More Services" hub.

---

## 🧩 Features

### 📚 Core Academic Tools

- **Course Enrolment** — search, filter, and enrol in 130+ real York courses across 12 departments
- **3-Column Layout** — filters (left) → course grid (center) → enrolment cart (right) — nothing else competing
- **Real-Time Seat Tracking** — live capacity bars with Open / Near Full / Full indicators
- **Weekly Timetable** — visual schedule grid that populates automatically as courses are added
- **Degree Progress Ring** — SVG circular progress showing credits completed vs. required (120 cr)
- **Course Detail Modals** — full info panel with prerequisites, instructor, format, pricing, and enrolment status

### 💰 Financial Planning

- **Financial Account** — charges breakdown (tuition, student services, health & dental, tech fees) with payment tracking
- **Budget Dashboard** — category-level spending bars, pie chart allocation, monthly trend charts (Recharts), and financial aid tracking
- **Tuition Estimation** — real-time totals that update live as courses are added or dropped

### 🏆 Grants, Aid & Awards

- **Scholarship Finder** — browse funding with type filtering (Merit, Need-Based, Identity, Research)
- **Save & Bookmark** — save awards to review and apply later
- **Eligibility + deadlines** displayed per award

### 💼 Career & Research

- **Internal Job Board** — on-campus work-study, part-time, and full-time positions with wages and deadlines
- **Research Opportunities** — faculty-led undergraduate research positions with PI contact, stipend, and spot availability

### 🎨 Platform Design

- **64px Icon Rail Sidebar** — 5 core nav items replacing the original 20+ item sidebar
- **"More Services" Hub** — budget, scholarships, jobs, research, and student life pages under one clean sub-nav
- **Dark / Light Mode** — full theme system with warm token palettes
- **Toast Notifications** — success, warning, and error feedback on all actions
- **API-Driven Architecture** — simulated backend with async fetching, ready to swap in real endpoints

---

## ⚙️ Tech Stack

<div align="center">

| Layer | Technology |
|:---:|:---:|
| **Frontend** | React 18 (Hooks, Functional Components) |
| **Language** | JavaScript ES6+ |
| **Styling** | CSS-in-JS (inline styles + design token system) |
| **Charts** | Recharts |
| **Icons** | Lucide React |
| **Typography** | Epilogue + Fraunces (Google Fonts) |
| **Data Layer** | Simulated REST API with async fetch |

</div>

### 🔜 Planned Stack

<div align="center">

| Layer | Technology |
|:---:|:---:|
| **Database** | Supabase (PostgreSQL) |
| **Auth** | Supabase Auth (Passport York SSO simulation) |
| **Course Data** | York Open Data / Yoki Course API |
| **Hosting** | Vercel |
| **Realtime** | Supabase Realtime (seat tracking) |

</div>

---

## 📐 Design Decisions

### Why the slim icon rail?

> The original sidebar had 20+ nav items visible at all times. For a student enrolling in courses, most of those links are irrelevant noise. The icon rail keeps the 4 critical workflows one click away and groups everything else under "More" — **progressive disclosure** over information overload.

### Why the 3-column enrolment layout?

> Course enrolment is the highest-traffic workflow in any university portal. The layout is intentionally rigid: **filters → results → cart**. Each column has one job. No top nav bar, no status strip, no announcements banner fighting for attention during the most important task of the semester.

### Why no top tab bar?

> The v1 had 9 tabs (Courses, Schedule, Exams, Degree, Finances, Budget, Scholarships, Jobs, Research). That's too many contexts for one toolbar. The **icon rail + More page** pattern keeps the primary flow clean and secondary features accessible but tucked away.

---

## 📂 Architecture

```
york-rem/
├── src/
│   ├── App.jsx                  # Root — login + app shell
│   ├── api/
│   │   ├── courses.js           # Course fetch, search, filter
│   │   ├── enrolment.js         # Enrol / drop / waitlist
│   │   ├── student.js           # Profile, degree audit
│   │   └── finance.js           # Tuition, charges, aid
│   ├── components/
│   │   ├── Layout/
│   │   │   ├── IconRail.jsx     # 64px sidebar
│   │   │   └── SubHeader.jsx    # Back-arrow sub-page headers
│   │   ├── Enrol/
│   │   │   ├── FilterPanel.jsx  # Left — dept, term, format, level
│   │   │   ├── CourseGrid.jsx   # Center — card grid
│   │   │   ├── CartPanel.jsx    # Right — enrolment cart
│   │   │   └── CourseModal.jsx  # Detail overlay
│   │   ├── Schedule/
│   │   ├── Degree/
│   │   ├── Finance/
│   │   └── More/
│   ├── data/                    # Structured mock datasets
│   ├── hooks/                   # useTheme, useToast
│   └── styles/tokens.js         # Design tokens
├── public/
├── package.json
└── README.md
```

> **Note:** The current build ships as a single-file React component for rapid prototyping. The architecture above represents the target modular structure.

---

## 📊 Course Data

The platform includes **130+ structured courses** modeled after York's real catalog:

<div align="center">

| Field | Example |
|:---:|:---:|
| Code | `EECS 2030` |
| Title | Advanced Object-Oriented Programming |
| Instructor | Dr. S. Kim |
| Credits | 3 |
| Schedule | Tue/Thu · 13:00–14:30 |
| Format | Hybrid |
| Term | Winter 2026 |
| Faculty | Lassonde |
| Price | $1,015 |
| Capacity | 105 |
| Enrolled | 86 |

</div>

**12 departments:** ACTG · ADMS · BIOL · CHEM · ECON · EECS · FILM · HIST · KINE · MATH · POLS · PSYC

**Pricing:** ~$1,015 per 3-credit course · ~$2,030 per 6-credit course (York domestic estimates)

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/mzkmajlish/york-rem.git
cd york-rem

# Install dependencies
npm install

# Start development server
npm run dev
```

### Quick Start

1. Open the app in your browser
2. Sign in with **any username and password** (auth is simulated)
3. Browse courses, use filters, enrol from the card grid
4. Check Schedule, Degree progress, and Financial Account
5. Explore Budget, Scholarships, Jobs, and Research under **More**

---

## 🗺️ Roadmap

- [x] Course catalog — 130+ structured York courses
- [x] 3-column enrolment layout (filters / grid / cart)
- [x] Real-time seat tracking and status indicators
- [x] Tuition estimation with live cart totals
- [x] Budget dashboard with Recharts visualizations
- [x] Scholarship finder with bookmarking
- [x] Internal job board with type filtering
- [x] Research opportunities with PI contact
- [x] Degree progress ring with credit tracking
- [x] Weekly timetable view
- [x] Dark / light theme system
- [x] Simulated API layer with async data fetching
- [ ] Supabase backend integration (PostgreSQL + Auth)
- [ ] Real York course API connection
- [ ] Schedule conflict detection
- [ ] Prerequisite chain validation
- [ ] Course ratings and professor reviews
- [ ] Waitlist queue management
- [ ] Export schedule to Google Calendar / iCal
- [ ] Push notifications for seat openings
- [ ] Mobile-responsive layout
- [ ] Accessibility audit (WCAG 2.1 AA)

---

## 🤝 Contributing

This is an open-source concept project. Contributions are welcome — especially from York students who understand the pain points firsthand.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/schedule-export`)
3. Commit your changes (`git commit -m 'Add iCal export'`)
4. Push to the branch (`git push origin feature/schedule-export`)
5. Open a Pull Request

---

## ⚠️ Disclaimer

This project is an **independent concept redesign** and is **not affiliated with, endorsed by, or connected to York University** or its official systems. All course data is structured mock data based on publicly available catalog information. No real student data is used or accessed.

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">

**Built by [Md Zihan Khan Majlish](https://github.com/mzkmajlish)**

Schulich School of Business · York University<br/>
Finance, Economics & Computer Science — Year 2

<br/>

![Made with](https://img.shields.io/badge/Made_with-☕_and_frustration_with_REM-C8102E?style=flat-square)

</div>

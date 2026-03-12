# York REM — Student Enrolment Portal (Redesign)

> A ground-up redesign of York University's Registration & Enrolment Module (REM), reimagining the student portal as a modern, unified academic platform.

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript&logoColor=black)
![Recharts](https://img.shields.io/badge/Recharts-2.x-8884d8)
![License](https://img.shields.io/badge/License-MIT-green)

---

## The Problem

York University's current REM system is widely regarded by students as one of the most frustrating academic tools they have to use. The interface is fragmented, visually outdated, and forces students to juggle multiple disconnected systems for tasks that should be seamless — enrolling in courses, checking finances, finding campus jobs, and tracking degree progress.

Common pain points include:

- **Fragmented workflows** — students bounce between REM, Student Financial Services, degree audit tools, and separate career portals to complete basic academic planning
- **Cluttered UI** — too many navigation elements competing for attention; students can't find what they need
- **Poor course discovery** — no real-time seat tracking, weak search/filter, and no schedule conflict detection
- **No financial integration** — tuition estimates, budgeting tools, and scholarship discovery don't exist in the same ecosystem
- **Missing career tools** — campus jobs, research opportunities, and work-study positions live in separate, hard-to-find systems

## The Solution

York REM (Redesigned) is a concept project that consolidates every core student workflow into a single, modern web application. It demonstrates what York's student portal _could_ look like if it were built from scratch with current UI/UX standards and a student-first design philosophy.

---

## Features

### Core Academic Tools

- **Course Enrolment** — search, filter, and enrol in 130+ real York courses across 12 departments with real-time seat availability, enrolment capacity bars, and waitlist indicators
- **3-Column Enrolment Layout** — focused UX with filters on the left, course catalog in the center, and an enrolment cart on the right — nothing else competing for attention
- **Timetable View** — visual weekly schedule grid that populates automatically as courses are added
- **Degree Progress Tracker** — SVG progress ring showing credits completed, enrolled, and remaining against the 120-credit degree requirement
- **Course Detail Modals** — click any course card for full details including prerequisites, instructor, schedule, format, pricing, and enrollment status

### Financial Planning

- **Financial Account** — charges breakdown (tuition, student services, health & dental, tech fees) with payment tracking
- **Budget Dashboard** — semester expense tracker with category-level spending bars, pie chart allocation view, monthly trend charts (Recharts), and financial aid tracking (OSAP, scholarships, work-study projections)
- **Tuition Estimation** — real-time tuition totals that update as courses are added/dropped from the enrolment cart

### Grants, Aid & Awards

- **Scholarship Finder** — browse 6+ scholarships and bursaries with type filtering (Merit, Need-Based, Identity, Research)
- **Save & Bookmark** — save scholarships to review/apply later
- **Eligibility info and deadlines** displayed per award

### Career & Research

- **Internal Job Board** — on-campus and university-related positions including work-study, part-time, and full-time roles with wage estimates, hour requirements, and application deadlines
- **Research Opportunities** — faculty-led undergraduate research positions across CS, Economics, Biology, Engineering, and Social Sciences with PI contact info, stipend details, and spot availability

### Platform Design

- **Slim Icon Rail Navigation** — 64px sidebar with 5 core icons (Enrol, Schedule, Degree, Account, More) replacing the bloated 20+ item sidebar of the original
- **"More Services" Hub** — budget tools, scholarships, jobs, research, and student life pages all organized under a single clean sub-navigation page
- **Dark / Light Mode** — full theme system with warm token palettes for both modes
- **Toast Notifications** — success, warning, and error feedback for all user actions
- **API-Driven Architecture** — simulated backend layer with realistic latency, structured database schema, and async data fetching ready to swap in real endpoints

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 18 (Functional Components, Hooks) |
| **Language** | JavaScript (ES6+) |
| **Styling** | CSS-in-JS (inline style objects, theme token system) |
| **Charts** | Recharts (Bar, Pie, Responsive containers) |
| **Icons** | Lucide React |
| **Typography** | Epilogue (body) + Fraunces (display) via Google Fonts |
| **Data Layer** | Simulated REST API with async fetch, structured mock DB |
| **State** | React `useState`, `useMemo`, `useCallback` |

### Planned / In Progress

| Layer | Technology |
|---|---|
| **Backend** | Supabase (PostgreSQL + Auth + Realtime) |
| **Course API** | York University Open Data / Yoki Course API |
| **Auth** | Passport York SSO simulation → Supabase Auth |
| **Hosting** | Vercel |

---

## Architecture

```
york-rem/
├── src/
│   ├── App.jsx                  # Root component — login + app shell
│   ├── api/
│   │   ├── courses.js           # Course catalog fetch, search, filter
│   │   ├── enrolment.js         # Enrol / drop / waitlist operations
│   │   ├── student.js           # Student profile, degree audit
│   │   └── finance.js           # Tuition, charges, aid
│   ├── components/
│   │   ├── Layout/
│   │   │   ├── IconRail.jsx     # 64px slim sidebar navigation
│   │   │   └── SubHeader.jsx    # Back-arrow sub-page headers
│   │   ├── Enrol/
│   │   │   ├── FilterPanel.jsx  # Left column — dept, term, format, level
│   │   │   ├── CourseGrid.jsx   # Center — course card grid
│   │   │   ├── CourseCard.jsx   # Individual course card
│   │   │   ├── CartPanel.jsx    # Right column — enrolment cart
│   │   │   └── CourseModal.jsx  # Detail modal overlay
│   │   ├── Schedule/
│   │   │   └── Timetable.jsx    # Weekly grid view
│   │   ├── Degree/
│   │   │   └── ProgressRing.jsx # SVG degree progress
│   │   ├── Finance/
│   │   │   ├── Account.jsx      # Charges + payments
│   │   │   └── Budget.jsx       # Spending tracker + charts
│   │   ├── More/
│   │   │   ├── Scholarships.jsx
│   │   │   ├── Jobs.jsx
│   │   │   ├── Research.jsx
│   │   │   └── Profile.jsx
│   │   └── ui/
│   │       ├── Toast.jsx
│   │       ├── MiniChip.jsx
│   │       └── FilterSection.jsx
│   ├── data/
│   │   ├── catalog.js           # York course catalog (structured mock)
│   │   ├── scholarships.js
│   │   ├── jobs.js
│   │   └── research.js
│   ├── hooks/
│   │   ├── useTheme.js          # Dark / light mode management
│   │   └── useToast.js          # Toast notification system
│   └── styles/
│       └── tokens.js            # Design tokens — colors, spacing, radii
├── public/
├── package.json
└── README.md
```

> **Note:** The current build ships as a single-file React component for rapid prototyping. The architecture above represents the target modular structure for production.

---

## Course Data

The platform uses a structured mock dataset modeled after York University's real course catalog. Each course entry includes:

| Field | Example |
|---|---|
| Course Code | `EECS 2030` |
| Title | Advanced Object-Oriented Programming |
| Instructor | Dr. S. Kim |
| Credits | 3 |
| Schedule | Tue/Thu · 13:00–14:30 |
| Format | Hybrid |
| Term | Winter 2026 |
| Faculty | Lassonde |
| Capacity | 105 |
| Enrolled | 86 |
| Price | $1,015 |
| Prerequisites | EECS 1022 or equivalent |

**12 departments covered:** ACTG, ADMS, BIOL, CHEM, ECON, EECS, FILM, HIST, KINE, MATH, POLS, PSYC, SOCI

**Pricing model:** ~$1,015 per 3-credit course, ~$2,030 per 6-credit course (based on York domestic undergraduate tuition estimates).

---

## Design Decisions

### Why the slim icon rail?

The original sidebar had 20+ navigation items visible at all times. For a student trying to enrol in courses, most of those links are irrelevant noise. The icon rail keeps the 4 most critical workflows (Enrol, Schedule, Degree, Account) one click away, and groups everything else under "More." This follows the principle of progressive disclosure — show what's needed now, reveal the rest on demand.

### Why the 3-column enrolment layout?

Course enrolment is the single highest-traffic workflow in any university portal. The layout is intentionally rigid: filters → results → cart. Each column has one job. There's no top nav bar, no status strip, no announcements banner fighting for the student's attention during the most important task of the semester.

### Why not a top tab bar?

The v1 design had 9 tabs across the top (Courses, Schedule, Exams, Degree, Finances, Budget, Scholarships, Jobs, Research). That's too many contexts for one toolbar. A student enrolling in courses doesn't need to see "Research Opportunities" in their peripheral vision. The icon rail + More page pattern solves this by keeping the primary flow clean and the secondary features accessible but tucked away.

---

## Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn

### Installation

```bash
# Clone the repository
git clone https://github.com/mdzihan/york-rem.git
cd york-rem

# Install dependencies
npm install

# Start development server
npm run dev
```

### Quick Start

1. Open the app in your browser
2. Sign in with any username and password (authentication is simulated)
3. Browse the course catalog, use filters, and enrol in courses
4. Check your Schedule, Degree progress, and Financial Account
5. Explore Budget, Scholarships, Jobs, and Research under "More"

---

## Roadmap

- [x] Course catalog with 130+ structured York courses
- [x] 3-column enrolment layout (filters / courses / cart)
- [x] Real-time seat tracking and enrolment status
- [x] Tuition estimation and financial account view
- [x] Budget dashboard with charts
- [x] Scholarship finder with bookmarking
- [x] Internal job board with type filtering
- [x] Research opportunities with PI contact
- [x] Degree progress ring with credit tracking
- [x] Weekly timetable view
- [x] Dark / light theme system
- [x] Simulated API layer with async data fetching
- [ ] Supabase backend integration (PostgreSQL + Auth)
- [ ] Real York course API connection (Yoki / Open Data)
- [ ] Schedule conflict detection
- [ ] Prerequisite chain validation
- [ ] Course ratings and professor reviews
- [ ] Waitlist queue management
- [ ] Export schedule to Google Calendar / iCal
- [ ] Push notification system for seat openings
- [ ] Mobile-responsive layout
- [ ] Accessibility audit (WCAG 2.1 AA)

---

## Contributing

This is an open-source concept project. Contributions are welcome — especially from York students who understand the pain points firsthand.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/schedule-export`)
3. Commit your changes (`git commit -m 'Add iCal export for timetable'`)
4. Push to the branch (`git push origin feature/schedule-export`)
5. Open a Pull Request

---

## Disclaimer

This project is an **independent concept redesign** and is not affiliated with, endorsed by, or connected to York University or its official systems. All course data is structured mock data based on publicly available catalog information. No real student data is used or accessed.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

<p align="center">
  <strong>Built by <a href="https://github.com/mdzihan">Zihan M.</a></strong><br/>
  Schulich School of Business · York University<br/>
  Finance, Economics & Computer Science — Year 2
</p>

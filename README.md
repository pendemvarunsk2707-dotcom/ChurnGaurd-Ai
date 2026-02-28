# ChurnGuard AI

**AI-Powered Customer Churn Prediction & Revenue Leakage Detection System**

ChurnGuard AI is a premium, enterprise-grade SaaS platform that helps revenue teams predict customer churn before it happens and detect revenue leakage in real time. Built for CMOs, Revenue Heads, SaaS Founders, and Enterprise Sales Directors.

---

## Live Demo

> Deployed on the Internet Computer (ICP) via [Caffeine AI](https://caffeine.ai)

---

## Features

### Landing Page
- Conversion-focused hero with animated statistics
- Problem section with industry churn data
- Feature showcase (6 core capabilities)
- 3-step "How It Works" flow
- Enterprise testimonials
- 3-tier pricing (Starter / Growth / Enterprise)
- Request Demo modal with backend form submission
- Start Free Trial modal with plan pre-selection

### Authenticated Dashboard
- **Overview Panel** -- Key metrics (Total Customers, Churn Risk %, Revenue Leakage %, Revenue Impact) + interactive monthly trend line chart
- **Churn Prediction Module** -- Customer table with churn probability %, color-coded risk levels (Low / Medium / High), and risk filters
- **Revenue Leakage Detection** -- Bar chart breakdown (billing errors, failed renewals, discount abuse, fraud signals) + AI explanation panel
- **Customer 360 Profiles** -- Click any customer to view engagement score, purchase history, risk probability, and action recommendations
- **AI Insights Sidebar** -- Real-time strategic recommendations and predictive alerts

### Extra Features
- Dark / Light theme toggle
- Role-based access control (Admin / Analyst / Executive)
- CSV export
- Real-time notifications bell
- Fully responsive (desktop, tablet, mobile)

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, TypeScript, Tailwind CSS |
| Routing | TanStack Router |
| Charts | Recharts |
| Animations | Framer Motion |
| UI Components | shadcn/ui |
| Backend | Motoko (Internet Computer) |
| Auth | Internet Identity (ICP) |
| Deployment | Internet Computer Protocol (ICP) |

---

## Project Structure

```
churnguard-ai/
├── src/
│   ├── backend/
│   │   └── main.mo                  # Motoko backend canister
│   └── frontend/
│       ├── index.html
│       ├── index.css                # OKLCH design tokens + global styles
│       ├── tailwind.config.js
│       └── src/
│           ├── App.tsx              # Router setup
│           ├── main.tsx             # Entry point
│           ├── pages/
│           │   ├── LandingPage.tsx
│           │   ├── LoginPage.tsx
│           │   └── DashboardPage.tsx
│           ├── components/
│           │   ├── RequestDemoModal.tsx
│           │   ├── StartTrialModal.tsx
│           │   └── dashboard/
│           │       ├── OverviewPanel.tsx
│           │       ├── ChurnPredictionPanel.tsx
│           │       ├── RevenueLeakagePanel.tsx
│           │       ├── CustomersPanel.tsx
│           │       ├── CustomerModal.tsx
│           │       └── AIInsightsSidebar.tsx
│           ├── hooks/
│           │   ├── useQueries.ts
│           │   ├── useActor.ts
│           │   └── useInternetIdentity.ts
│           └── context/
│               └── ThemeContext.tsx
├── dfx.json                         # ICP project config
├── package.json
└── README.md
```

---

## Backend API (Motoko)

### Public (no auth required)
| Function | Description |
|---|---|
| `submitDemoRequest(DemoRequest)` | Store a demo request from the landing page |
| `submitTrialSignup(TrialSignup)` | Store a free trial signup |

### Authenticated Users
| Function | Description |
|---|---|
| `getCustomers()` | List all customers with churn data |
| `getCustomerById(id)` | Get a single customer profile |
| `getDashboardMetrics()` | Fetch overview metrics |
| `getRevenueLeakage()` | Get revenue leakage breakdown |
| `getMonthlyTrends()` | Fetch monthly churn + revenue trends |
| `getAIInsights()` | Get AI strategic recommendations |

### Admin Only
| Function | Description |
|---|---|
| `saveCustomer(Customer)` | Add or update a customer record |
| `initializeData()` | Seed the canister with sample data |
| `getDemoRequests()` | View all submitted demo requests |
| `getTrialSignups()` | View all trial signups |

---

## Data Models

```motoko
Customer {
  id, name, email, plan,
  engagementScore,      // 0–100
  churnProbability,     // 0–100
  riskLevel,            // "Low" | "Medium" | "High"
  lastActivity,
  revenueImpact,
  purchaseCount,
  role
}

DemoRequest { name, workEmail, companyName, companySize, message }
TrialSignup  { name, workEmail, companyName, plan }
```

---

## Design System

- **Base**: Deep charcoal / midnight black background
- **Accents**: Electric blue + neon purple gradients
- **Color system**: OKLCH tokens via Tailwind CSS
- **Effects**: Glassmorphism, soft glow shadows, smooth micro-animations
- **Typography**: Inter / system display fonts

---

## STLC (Software Testing Life Cycle)

| Phase | Scope |
|---|---|
| Requirement Analysis | All 4 dashboard panels, landing page, modals, auth |
| Test Planning | UI, functional, integration, role-based access |
| Test Case Design | 10+ critical test cases per module |
| Test Environment | Deployed draft URL (Chrome, Firefox, Safari) |
| Test Execution | Manual testing with pass/fail logging |
| Defect Reporting | Steps to reproduce + expected vs actual |
| Test Closure | Stakeholder sign-off after all critical bugs fixed |

---

## Business Model

ChurnGuard AI is designed for direct B2B sales to SaaS companies. Suggested revenue paths:

- **Per-seat SaaS licensing** (Starter $299/mo · Growth $799/mo · Enterprise custom)
- **White-label licensing** for companies wanting their own brand
- **Productized consulting** -- onboarding + setup as a managed service
- **App marketplace royalties** via Caffeine AI App Market (coming soon)

---

## Built With

- [Caffeine AI](https://caffeine.ai) -- Full-stack ICP app builder
- [Internet Computer Protocol](https://internetcomputer.org) -- Decentralized cloud hosting
- [Internet Identity](https://identity.ic0.app) -- Passwordless authentication

---

## License

MIT License. See `LICENSE` for details.

---

*Last updated: February 2026*

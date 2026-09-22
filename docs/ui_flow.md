# ui_flow.md

<!--
This file is generated/re-written by the UI/UX Designer.
Context sources: docs/architecture.md + AGENTS_FRONTEND.md
Defines screens, navigation, user flows, UI interactions, and responsive states.
-->

## 1. Screen Inventory & Route Map
<!--
List all pages/screens, URL routes, and access levels (Public / Guest / Auth / Admin):

- `/` -> Landing / Home Page (Public)
- `/login` -> Login Page (Guest only)
- `/dashboard` -> Main Dashboard (Auth required)
-->

---

## 2. User Journey & Navigation Flows
<!--
Describe key interaction flows and step-by-step user journeys:

### Flow A: User Registration & Onboarding
1. User visits `/register`, fills in form (Name, Email, Password).
2. Clicks "Daftar".
3. Success: Redirects to `/verify-email` or `/dashboard`.
4. Error: Displays inline field errors with clear feedback.
-->

---

## 3. Screen State Definitions
<!--
Define behavior across 4 essential UI states:

### [Screen Name]: e.g., Dashboard
- **Initial / Loading State**: Skeleton shimmer placeholder cards.
- **Empty State**: Friendly illustration + "Belum ada data" + Call-to-action button.
- **Success State**: Populated metrics, interactive data table with pagination.
- **Error State**: Toast error alert with "Gagal memuat data. [Coba Lagi]" retry button.
-->

---

## 4. Required Data per Screen (Feed to API Designer)
<!--
Summarize the exact data required by each screen so the API Designer can build matching endpoints:

### [Screen Name]: e.g., Dashboard
- Requires: `user.profile` (name, avatar, role)
- Requires: `metrics.summary` (total_sales, active_users)
- Requires: `orders.recent` (list of latest 5 orders)
-->

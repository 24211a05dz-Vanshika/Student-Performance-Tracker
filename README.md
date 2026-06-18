# Scholar — Student Performance Tracker

A premium, fully-responsive SaaS dashboard for tracking student performance, built
with **React 18 + TypeScript + Vite**, **Tailwind CSS**, **shadcn/ui**-style
primitives, **React Router**, **TanStack Query**, **React Hook Form + Zod**, and
**Recharts**.

> No backend required — the app ships with a mock service layer that persists to
> `localStorage`, so you can run it instantly.

## Demo credentials

```
Email:    admin@scholar.app
Password: password123
```

(There is an **Autofill** button on the login screen.)

## Getting started

```bash
npm install
npm run dev      # start the dev server at http://localhost:5173
```

Other scripts:

```bash
npm run build      # type-check + production build
npm run preview    # preview the production build
npm run typecheck  # strict TypeScript check
```

> Requires Node 18+.

## Features

- **Auth** — email/password login with Zod validation, show/hide password,
  remember-me, loading & error states, success toasts, and a logout confirmation modal.
- **Students** — create, edit, delete, view, search (debounced) and paginate.
- **Marks** — record/update Midterm, Final and Quarterly scores (0–100, validated).
- **Analytics** — animated Recharts bar charts, summary metric cards, a leaderboard
  and auto-generated performance insights.
- **UX** — skeleton loaders everywhere, empty states, error states with retry,
  toast notifications, confirm dialogs and an error boundary.
- **Layout** — fixed collapsible sidebar (desktop), drawer nav (mobile), sticky header.
- **Design** — glassmorphism, gradients, soft shadows, micro-interactions, dark mode,
  and full responsiveness from mobile to ultrawide.

## Architecture

```
src/
├── app/            # App root
├── routes/         # Router config + Protected/Public route guards
├── pages/          # Route-level pages
├── layouts/        # Auth & Dashboard layouts
├── components/
│   ├── ui/         # shadcn-style primitives (button, dialog, select, …)
│   ├── forms/      # RHF-bound form controls (FormInput, FormSelect, …)
│   ├── charts/     # Recharts wrappers
│   └── shared/     # App-level building blocks (StatsCard, DataTable, …)
├── hooks/          # React Query hooks + utilities
├── services/       # Mock API layer (auth, students, marks, analytics)
├── providers/      # App, Auth & Toast providers
├── validations/    # Zod schemas
├── types/          # Shared TypeScript types
├── constants/      # Query keys, nav items, enums, design tokens
├── lib/            # cn(), query client, toast
└── utils/          # Pure helpers (formatting)
```

### Resetting demo data

Clear the `spt::*` keys in `localStorage` (or run `localStorage.clear()` in the
browser console) to restore the seeded students and marks.

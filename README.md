# 💰 Finance Control

> **Self-Hosted, Privacy-First Personal Finance Web Application**  
> Built with React 19, Vite, TypeScript, Tailwind CSS, shadcn/ui, and Dexie.js (IndexedDB).

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-Strict-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

---

## 🌟 Overview

**Finance Control** is an open-source, privacy-focused financial dashboard and budgeting application. Unlike traditional finance tools, **your data never leaves your browser**. Everything is persisted locally using browser-native **IndexedDB** via **Dexie.js**, giving you complete data sovereignty and zero tracking.

### ✨ Key Differentiators
- 🛡️ **100% Privacy & Local-First:** No cloud tracking, no third-party telemetry. Data lives safely inside your browser.
- ⚡ **60fps High-Performance Ledger:** Powered by **TanStack Table v8** and **TanStack Virtual** to seamlessly navigate 10,000+ transactions without UI freezes.
- 🎯 **Integer Cents Standard (P0):** Eliminates IEEE 754 floating-point rounding errors (`0.1 + 0.2 != 0.3`) by doing all ledger arithmetic in integer cents.
- 🔥 **FIRE (Financial Independence, Retire Early) Command Center:** Project future wealth with the 4% Safe Withdrawal Rule and custom compounding scenarios.
- 💎 **Modern Glassmorphism UI:** Built with Tailwind CSS, custom design tokens, dark/light theme support, and accessible **shadcn/ui** primitives.
- 📥 **CSV Ingestion & Automation Rules:** Drag-and-drop bank statement parser with deduplication hashes and dynamic auto-categorization.

---

## 🏗️ System Architecture

The complete system architecture diagram is documented in [`docs/architecture.drawio`](docs/architecture.drawio).

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ 1. PRESENTATION & VIEWS                                                     │
│    App Shell ─── Ledger DataGrid ─── Analytics/FIRE ─── Budgets & Rules    │
├─────────────────────────────────────────────────────────────────────────────┤
│ 2. DESIGN SYSTEM & CORE UTILITIES                                           │
│    shadcn/ui Primitives ─── Tailwind (Glassmorphism) ─── Integer Cents Math │
├─────────────────────────────────────────────────────────────────────────────┤
│ 3. STATE & DATA INGESTION                                                  │
│    TanStack Query v5 (Optimistic UI) ─── CSV Ingestion ─── Rules Engine     │
├─────────────────────────────────────────────────────────────────────────────┤
│ 4. LOCAL-FIRST PERSISTENCE                                                  │
│    Dexie.js Client ─── IndexedDB (Browser Engine) ─── 1-Click Backup Export │
└─────────────────────────────────────────────────────────────────────────────┘
```

> 💡 *To view or edit the architecture diagram online, you can open [`docs/architecture.url`](docs/architecture.url) or use the VS Code Draw.io Integration extension.*

---

## 🗺️ Roadmap & Sprints

The implementation is broken down into 6 sequential phases. Full task breakdown is available in [`docs/roadmap.drawio`](docs/roadmap.drawio).

- **Phase 1: Foundations & Design System Setup**
  - Tooling (Vite + React 19 + TypeScript Strict + Path Aliases `@/*`)
  - Tailwind CSS Glassmorphism tokens & Dark/Light mode theme provider
  - shadcn/ui & Radix UI Primitives integration
- **Phase 2: Data Modeling & Local-First Storage**
  - Integer Cents standard and domain models (`Account`, `Transaction`, `Category`)
  - Dexie.js (IndexedDB) database schema & realistic mock seeder
  - TanStack Query v5 custom hooks (`useTransactions`, `useAccounts`, `useSummary`)
- **Phase 3: App Shell, Navigation & Metric Cards**
  - Responsive Glassmorphism Sidebar & Mobile Drawer
  - Global Date Range Picker & Currency switcher
  - Cumulative Layout Shift (CLS = 0) Skeleton metric cards
- **Phase 4: High-Performance Ledger & Virtual Grid**
  - TanStack Table v8 setup (Sorting, Resizing, Column Visibility)
  - TanStack Virtual 60fps scrolling for thousands of records
  - URL SearchParams multi-filtering (`nuqs`) & Optimistic CRUD mutations
- **Phase 5: Financial Analytics & FIRE Engine**
  - Recharts Cashflow bar chart & category expense breakdown
  - Monthly budget gauges with overspending alerts
  - FIRE 4% rule calculator and compounding projections
- **Phase 6: Ingestion Engine & Production Hardening**
  - Drag-and-drop CSV parser with SHA-256 transaction fingerprinting
  - Client-side automation rules engine
  - 1-Click JSON database backup/restore & accessibility (a11y) audit

---

## 🛠️ Tech Stack

| Category | Technology |
| :--- | :--- |
| **Framework & Language** | React 19, Vite, TypeScript (Strict) |
| **Styling & UI System** | Tailwind CSS, shadcn/ui (Radix UI Primitives), Lucide React |
| **Local Database** | Dexie.js (IndexedDB) |
| **Data Fetching & Cache**| TanStack Query v5 (React Query) |
| **Data Grid & Table** | TanStack Table v8, TanStack Virtual |
| **Charts & Analytics** | Recharts |
| **Form & Validation** | React Hook Form, Zod |
| **URL State** | nuqs |
| **Date & Math** | date-fns, Intl.NumberFormat |

---

## 👥 Contributors

- **Reshad Mammadov** ([@resad505](https://github.com/resad505)) — Frontend Architecture, UI/UX, Glassmorphism Design System & Accessibility.
- **Possible** ([@Possible-o](https://github.com/Possible-o)) — Data Modeling, Dexie.js Storage, TanStack Query Hooks & Data Ingestion Logic.

---

## 📄 License

This project is open-source under the [MIT License](LICENSE).

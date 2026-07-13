# ⚛️ React JS Learning Roadmap

A complete, structured roadmap to learn React from scratch — focused on problem solving, component thinking, real-world projects, and becoming capable of building applications independently. Concept-first, project-driven, no fluff.

---

# 🎯 Goal

Master React well enough to:

* Build real-world, production-style applications independently
* Understand component architecture and state deeply
* Work confidently with hooks, routing, and APIs
* Manage complex state without getting lost
* Become internship and interview ready

---

# ❌ What to Skip (Don't Waste Time)

| Topic                          | Reason                                |
| ------------------------------ | -------------------------------------- |
| Class Components (deep dive)   | Functional + Hooks is the modern way   |
| `componentDidMount` etc.       | Replaced by `useEffect`                |
| Redux (too early)              | Learn Context + hooks first            |
| Create React App               | Deprecated, use Vite instead           |
| PropTypes                      | Use TypeScript instead                 |
| jQuery-style DOM manipulation  | React handles the DOM for you          |
| Next.js (too early)            | Master plain React first               |
| Excessive theory before coding | Learn by building                      |
| Styled Components / CSS-in-JS (early) | Plain CSS/Tailwind is enough at first |
| Testing (too early)            | Wait until app-building is comfortable |
| Server-side rendering (early)  | Client-side React first                |

---

# 📅 Phase 1 — JavaScript Prerequisites

> **Goal:** Be fluent enough in modern JavaScript that React syntax never feels confusing.

---

## Block 1: Modern JS Essentials

* [ ] `let` vs `const` vs `var`
* [ ] Arrow Functions
* [ ] Template Literals
* [ ] Destructuring (Objects & Arrays)
* [ ] Spread & Rest Operators
* [ ] Default Parameters
* [ ] Ternary Operator

### Practice

* Rewrite old `var`/`function` code using modern syntax
* Destructuring drills on sample objects

---

## Block 2: Arrays & Objects

* [ ] `map()`
* [ ] `filter()`
* [ ] `reduce()`
* [ ] `find()`
* [ ] `some()` / `every()`
* [ ] `forEach()`
* [ ] Object methods (`Object.keys`, `Object.values`, `Object.entries`)

### Practice

* Todo Filter Logic
* Cart Total Calculator
* Data Transformer (array of objects → new shape)

---

## Block 3: Asynchronous JavaScript

* [ ] Callbacks (concept only)
* [ ] Promises
* [ ] `async` / `await`
* [ ] `fetch()` API
* [ ] Error Handling (`try/catch`)
* [ ] JSON parsing

### Practice

* Fetch a public API and log the data
* Weather Fetcher (console-based)

---

## Block 4: Modules & Tooling

* [ ] ES Modules (`import` / `export`)
* [ ] npm Basics
* [ ] Node.js (just enough to run tools)
* [ ] Vite Setup
* [ ] Browser DevTools (Console, Network, Elements)

---

## ✅ Phase 1 Project

### JS-Only Mini App

Features:

* Fetch data from a public API
* Filter/search the data
* Render it into the DOM manually (no React yet)

---

# 📅 Phase 2 — React Fundamentals

> **Goal:** Understand how React thinks — components, JSX, props, and state.

---

## Block 5: React Basics

* [ ] What Problem React Solves
* [ ] Virtual DOM (concept)
* [ ] JSX Syntax
* [ ] JSX Expressions & Rendering
* [ ] Components (Function Components)
* [ ] Component Composition
* [ ] Fragments
* [ ] Rendering Lists (`key` prop)
* [ ] Conditional Rendering

### Practice

* Greeting Card Component
* List Renderer (render an array of items)
* Simple Profile Card

---

## Block 6: Props

* [ ] Passing Props
* [ ] Props Destructuring
* [ ] Default Props
* [ ] Children Prop
* [ ] Prop Drilling (concept + problem)

### Practice

* Reusable Button Component
* Product Card Component
* Nested Component Tree

---

## Block 7: State & Events

* [ ] `useState`
* [ ] Updating State Correctly (no direct mutation)
* [ ] Event Handling (`onClick`, `onChange`, etc.)
* [ ] Controlled Inputs
* [ ] Multiple State Variables vs Object State
* [ ] Lifting State Up

### Practice

* Counter App
* Toggle Switch
* Simple Form (controlled inputs)
* Login Form Validation

---

## Block 8: Styling in React

* [ ] Plain CSS Files
* [ ] CSS Modules
* [ ] Inline Styles
* [ ] Conditional Class Names
* [ ] Tailwind CSS Basics

---

## ✅ Phase 2 Project

### Todo List App

Features:

* Add / delete / edit todos
* Mark as complete
* Filter (all / active / completed)
* Styled with CSS or Tailwind

---

# 📅 Phase 3 — Hooks & Component Patterns

> **Goal:** Go beyond basic state — manage side effects, refs, and reusable logic properly.

---

## Block 9: useEffect

* [ ] Why Side Effects Exist
* [ ] `useEffect` Syntax
* [ ] Dependency Array Rules
* [ ] Cleanup Functions
* [ ] Fetching Data on Mount
* [ ] Avoiding Infinite Loops

### Practice

* Data Fetcher Component
* Live Search (debounced API calls)
* Window Resize Listener

---

## Block 10: useRef & useMemo/useCallback

* [ ] `useRef` for DOM Access
* [ ] `useRef` for Persisting Values
* [ ] `useMemo`
* [ ] `useCallback`
* [ ] When (and When Not) to Optimize

### Practice

* Auto-Focus Input on Load
* Expensive Calculation Memoizer
* Stopwatch/Timer App

---

## Block 11: Context API

* [ ] Why Context Exists (solving prop drilling)
* [ ] `createContext`
* [ ] `useContext`
* [ ] Context Provider Pattern
* [ ] Combining Context with `useReducer`

### Practice

* Theme Switcher (Light/Dark)
* Auth Context (logged in/out state)

---

## Block 12: useReducer

* [ ] When to Use Reducer over State
* [ ] Reducer Function Structure
* [ ] Actions & Dispatch
* [ ] Combining with Context for Global State

### Practice

* Cart Reducer
* Complex Form State Manager

---

## Block 13: Custom Hooks

* [ ] Why Custom Hooks
* [ ] Extracting Reusable Logic
* [ ] Naming Conventions (`useSomething`)
* [ ] Building Your Own Hook Library

### Practice

* `useFetch` Hook
* `useLocalStorage` Hook
* `useDebounce` Hook

---

## ✅ Phase 3 Project

### Notes App with Theme & Local Storage

Features:

* Add/edit/delete notes
* Persist notes using `useLocalStorage` custom hook
* Dark/Light theme via Context
* Debounced search

---

# 📅 Phase 4 — Routing & Forms

> **Goal:** Build multi-page apps and handle real forms properly.

---

## Block 14: React Router

* [ ] Installing React Router
* [ ] `BrowserRouter`, `Routes`, `Route`
* [ ] `Link` vs `NavLink`
* [ ] Dynamic Routes (`:id` params)
* [ ] `useParams`
* [ ] `useNavigate`
* [ ] Nested Routes
* [ ] Protected Routes (auth guard)
* [ ] 404 / Not Found Pages

### Practice

* Multi-Page Portfolio Site
* Blog with Dynamic Post Pages

---

## Block 15: Forms (Properly)

* [ ] Controlled vs Uncontrolled Forms
* [ ] Form Validation (manual)
* [ ] React Hook Form Basics
* [ ] Validation Libraries (Zod/Yup — concept level)
* [ ] Handling File Inputs
* [ ] Multi-Step Forms

### Practice

* Signup Form with Validation
* Multi-Step Registration Wizard

---

## ✅ Phase 4 Project

### Blog Platform (Frontend Only)

Features:

* Home, Post Detail, Create Post pages
* Routing with dynamic post IDs
* Form to create/edit posts
* Client-side validation

---

# 📅 Phase 5 — State Management at Scale

> **Goal:** Handle state in larger applications without chaos.

---

## Block 16: Global State Management

* [ ] Limits of Context API at Scale
* [ ] Zustand Basics
* [ ] Redux Toolkit Basics
* [ ] Store, Slices, Actions
* [ ] When to Choose Which Tool

### Practice

* Shopping Cart with Zustand
* Todo App with Redux Toolkit

---

## Block 17: Server State (Data Fetching Done Right)

* [ ] Problems with Manual `useEffect` Fetching
* [ ] React Query / TanStack Query Basics
* [ ] Caching & Refetching
* [ ] Loading & Error States
* [ ] Mutations (`useMutation`)
* [ ] Optimistic Updates

### Practice

* Post List with React Query
* Comment Section with Optimistic Updates

---

## ✅ Phase 5 Project

### E-Commerce Product Catalog

Features:

* Product list fetched via React Query
* Cart managed with Zustand/Redux
* Filters, search, and pagination
* Checkout summary page

---

# 📅 Phase 6 — Real-World React

> **Goal:** Learn the practices professional React codebases actually use.

---

## Block 18: Performance & Optimization

* [ ] Re-render Behavior (why components re-render)
* [ ] `React.memo`
* [ ] Code Splitting (`React.lazy`, `Suspense`)
* [ ] Virtualization for Long Lists
* [ ] Avoiding Prop Drilling with Composition

---

## Block 19: TypeScript with React

* [ ] Why TypeScript Matters
* [ ] Typing Props
* [ ] Typing State & Hooks
* [ ] Typing Events
* [ ] Generic Components (basics)

---

## Block 20: Working with Backend & Auth

* [ ] REST API Integration Patterns
* [ ] Environment Variables
* [ ] JWT-based Auth Flow
* [ ] Storing Tokens Safely
* [ ] Axios vs Fetch
* [ ] Error Boundaries

---

## Block 21: Testing

* [ ] Why Testing Matters
* [ ] Vitest / Jest Basics
* [ ] React Testing Library
* [ ] Testing Components
* [ ] Testing Hooks
* [ ] Mocking API Calls

---

## Block 22: Deployment

* [ ] Production Build (`vite build`)
* [ ] Environment Configs
* [ ] Deploying to Vercel/Netlify
* [ ] CI Basics (optional)

---

## ✅ Phase 6 Projects

* Authenticated Task Manager (JWT + backend API)
* Movie Search App (TypeScript + React Query)
* Dashboard with Charts & Protected Routes

---

# 📅 Phase 7 — Next.js (Bonus Phase)

> **Goal:** Learn the most in-demand React framework once core React is solid.

---

## Block 23: Next.js Basics

* [ ] File-based Routing
* [ ] Server Components vs Client Components
* [ ] `getStaticProps` / `getServerSideProps` (or App Router equivalents)
* [ ] API Routes
* [ ] Image Optimization
* [ ] Metadata & SEO Basics

---

## ✅ Phase 7 Project

### Full-Stack Blog with Next.js

Features:

* Server-rendered post pages
* API routes for CRUD
* Auth-protected admin dashboard

---

# 📅 Phase 8 — Portfolio Projects

> **Goal:** Build projects worthy of GitHub, resumes, and internships.

* [ ] Personal Portfolio Website
* [ ] E-Commerce Store (Frontend + API)
* [ ] Real-Time Chat App (with WebSockets)
* [ ] Kanban Board (Drag & Drop)
* [ ] Movie/Recipe Discovery App
* [ ] Expense Tracker Dashboard
* [ ] Social Media Feed Clone
* [ ] SaaS Landing Page + Auth Flow

---

# 📊 Overall Progress

| Phase | Topic                        | Status         |
| ----- | ----------------------------- | -------------- |
| 1     | JavaScript Prerequisites      | 📋 Planned     |
| 2     | React Fundamentals            | 📋 Planned     |
| 3     | Hooks & Component Patterns    | 📋 Planned     |
| 4     | Routing & Forms               | 📋 Planned     |
| 5     | State Management at Scale     | 📋 Planned     |
| 6     | Real-World React              | 📋 Planned     |
| 7     | Next.js (Bonus)               | 📋 Planned     |
| 8     | Portfolio Projects            | 📋 Planned     |

---

# 🔥 Recommended Project Order

1. JS-Only Mini App
2. Todo List App
3. Notes App with Theme & Local Storage
4. Multi-Page Portfolio Site
5. Blog Platform (Frontend Only)
6. Shopping Cart with Zustand
7. E-Commerce Product Catalog
8. Authenticated Task Manager
9. Movie Search App
10. Dashboard with Charts & Protected Routes
11. Full-Stack Blog with Next.js
12. Real-Time Chat App
13. Kanban Board
14. SaaS Landing Page + Auth Flow

---

# ❓ Common Doubts You'll Hit (and When You'll Resolve Them)

| Doubt                                                   | Resolved In |
| -------------------------------------------------------- | ----------- |
| "Why does my component re-render so much?"               | Block 18    |
| "When do I use `useEffect` vs just computing a value?"    | Block 9     |
| "Context vs Redux vs Zustand — which do I actually need?" | Block 16    |
| "Why is my state not updating immediately?"               | Block 7     |
| "Controlled vs uncontrolled inputs — does it matter?"      | Block 15    |
| "Do I need TypeScript to get a job?"                       | Block 19    |
| "When should I learn Next.js?"                              | Phase 7     |
| "How do real apps handle login/auth?"                       | Block 20    |
| "Why is my `useEffect` running twice?"                       | Block 9     |
| "How do I know if my app is 'production ready'?"              | Block 22    |

---

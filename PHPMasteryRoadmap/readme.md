 # PHP Mastery Roadmap — Zero to Job-Ready

*A structured, no-fluff study plan covering everything that actually gets tested in PHP backend developer interviews and used on the job — from absolute basics to production-grade full-stack skills.*

**Author's context:** Built for someone who already knows HTML/CSS/JS/React and has shipped one real PHP + MySQL project (a full-stack voting system with auth, sessions, and CRUD). This plan fills the gaps between "can build a working app" and "can pass a backend interview and survive a real codebase."

---

## How to Use This Roadmap

- Work top to bottom — each phase assumes the previous one is solid.
- Every phase ends with a **checkpoint project** — don't move on until you've built it without copy-pasting from tutorials.
- Budget: roughly **10–12 weeks** at 1–2 hours/day for someone starting from your level (you can likely compress Phase 1–2 since you already know basic PHP/MySQL).
- Track progress by checking off `[ ]` boxes as you go.

---

## Phase 0: Environment & Tooling (2–3 days)

- [ ] Install PHP 8.3+ (not an old 7.x version — 8.x syntax and features are what jobs expect now)
- [ ] Install Composer (PHP's package manager — non-negotiable, every real project uses it)
- [ ] Set up a proper local environment: Laragon, XAMPP, or Docker (Docker is worth learning early if you're targeting modern teams)
- [ ] Set up VS Code with PHP Intelephense extension, or PhpStorm if you want a full IDE
- [ ] Learn basic Git workflow if not already fluent: branches, commits, `.gitignore`, pull requests

**Why this matters:** Composer and PHP 8+ syntax are assumed knowledge in every modern job posting. Skipping this phase is the #1 reason self-taught PHP devs get filtered out early.

---

## Phase 1: Core PHP Language (1.5–2 weeks)

You've used PHP already, so treat this as filling gaps and formalizing what you know.

### 1.1 Syntax Fundamentals
- [ ] Variables, data types, type juggling vs. strict types (`declare(strict_types=1)`)
- [ ] Operators, including spaceship (`<=>`) and null coalescing (`??`, `??=`)
- [ ] Control structures: if/else, switch, match (PHP 8's `match` expression — commonly asked in interviews)
- [ ] Loops: for, while, foreach, and when to use each

### 1.2 Functions
- [ ] Function declarations, default/named arguments, variadic functions (`...$args`)
- [ ] Return types and type declarations (`function foo(int $x): string`)
- [ ] Anonymous functions and closures — especially `use ($var)` by value vs. by reference
- [ ] Arrow functions (`fn($x) => $x * 2`)
- [ ] First-class callable syntax (PHP 8.1+)

### 1.3 Arrays (heavily tested in interviews)
- [ ] Indexed vs. associative vs. multidimensional arrays
- [ ] Core array functions: `array_map`, `array_filter`, `array_reduce`, `array_merge`, `usort`
- [ ] Destructuring with `list()` / `[$a, $b] = $array`
- [ ] Spread operator in arrays (`[...$arr1, ...$arr2]`)

### 1.4 Strings
- [ ] String functions you'll use constantly: `str_contains`, `str_starts_with`, `explode`/`implode`, `trim`, `sprintf`
- [ ] Heredoc and Nowdoc syntax
- [ ] Regular expressions with `preg_match`, `preg_replace` (know the basics, not mastery)

### 1.5 Error Handling
- [ ] `try`/`catch`/`finally`, throwing custom exceptions
- [ ] Difference between `Exception` and `Error` hierarchies
- [ ] Creating custom exception classes

**Checkpoint Project:** A command-line PHP script (no framework) that reads a CSV of data, processes it with array functions, handles malformed rows with exceptions, and outputs a summary report.

---

## Phase 2: Object-Oriented PHP (2 weeks)

This is where most self-taught PHP developers are weakest — and where interviews focus hardest.

- [ ] Classes, properties, methods, constructors, `__construct`
- [ ] Visibility: `public`, `private`, `protected` — and *why* it matters (encapsulation)
- [ ] Static properties/methods vs. instance ones
- [ ] Inheritance (`extends`) and method overriding
- [ ] Abstract classes vs. interfaces — know exactly when to use each (classic interview question)
- [ ] Traits (PHP's way of doing multiple "inheritance" of behavior)
- [ ] Magic methods: `__construct`, `__toString`, `__get`/`__set`, `__call` (know they exist, don't overuse them)
- [ ] Namespaces and autoloading (`PSR-4`, and how Composer's autoloader works)
- [ ] Enums (PHP 8.1+) — increasingly common in modern codebases
- [ ] Readonly properties (PHP 8.1+)

### Design Principles That Actually Get Asked About
- [ ] SOLID principles — be able to explain each one with a PHP example, not just recite the acronym
- [ ] Dependency Injection — what it is, why constructor injection is preferred over creating dependencies inline
- [ ] Basic design patterns: Singleton (and why it's often discouraged), Factory, Repository, Strategy

**Checkpoint Project:** Refactor your Digital Voting System's PHP logic into proper classes — e.g., a `Voter` class, an `Election` class, a `VoteRepository` class — replacing loose procedural functions with OOP structure.

---

## Phase 3: Working With Databases Properly (1.5 weeks)

You've used MySQL with prepared statements already — this phase makes that knowledge rigorous.

- [ ] PDO vs. MySQLi — know both exist, but **default to PDO** (more flexible, supports multiple DB drivers)
- [ ] Prepared statements — you've done this, now understand *why* they prevent SQL injection at the protocol level, not just "because tutorials say so"
- [ ] Transactions: `beginTransaction`, `commit`, `rollBack` — critical for anything involving money, votes, or multi-step writes
- [ ] Database relationships: one-to-one, one-to-many, many-to-many (and how to model many-to-many with a pivot table)
- [ ] Indexes — what they are, when they help, when they hurt write performance
- [ ] N+1 query problem — what it is and how to avoid it (extremely common interview question)
- [ ] Basic query optimization: `EXPLAIN`, avoiding `SELECT *`

**Checkpoint Project:** Add a proper migrations folder (plain SQL files, versioned) to your Voting System repo, and rewrite one feature (e.g., vote casting) to use a database transaction so a failure can't leave partial data.

---

## Phase 4: Modern PHP Practices & Composer Ecosystem (1 week)

- [ ] Composer deep dive: `composer.json`, `composer.lock`, semantic versioning, autoload configuration
- [ ] PSR standards overview — at minimum know PSR-4 (autoloading) and PSR-12 (coding style) exist and why standards matter in teams
- [ ] Environment variables and `.env` files (using `vlucas/phpdotenv` or framework equivalents) — **never hardcode credentials again**
- [ ] Dependency management: adding, updating, and understanding what a `vendor/` folder is
- [ ] Basic unit testing with PHPUnit — writing your first test, assertions, test doubles/mocks (even basic familiarity puts you ahead of most junior candidates)

**Checkpoint Project:** Take one class from your refactored Voting System (Phase 2) and write PHPUnit tests for it — at least 5 test cases covering normal input, edge cases, and expected failures.

---

## Phase 5: A Real Framework — Laravel (2.5–3 weeks)

Almost every PHP job posting asks for Laravel specifically. This is the highest-leverage phase for job-readiness.

- [ ] Installation, project structure, the Artisan CLI
- [ ] Routing: web routes vs. API routes, route parameters, route model binding
- [ ] Controllers and the MVC pattern in Laravel's context
- [ ] Blade templating: layouts, components, directives
- [ ] Eloquent ORM — this is Laravel's biggest selling point, spend real time here:
  - [ ] Models, migrations, seeders, factories
  - [ ] Relationships: `hasOne`, `hasMany`, `belongsTo`, `belongsToMany`
  - [ ] Query builder basics and Eloquent query scopes
  - [ ] Eager loading (`with()`) to solve the N+1 problem you learned about in Phase 3
- [ ] Form validation (Laravel's `Request` validation, Form Requests)
- [ ] Middleware — what it is, how auth middleware works, writing your own
- [ ] Authentication: Laravel Breeze or Fortify for a quick start, understanding what's happening underneath
- [ ] Building a REST API with Laravel: resource controllers, API resources/transformers, versioning basics
- [ ] Queues and jobs (at least conceptually — know when you'd use a queue vs. doing something synchronously)

**Checkpoint Project:** Rebuild your Digital Voting System (or a similar CRUD-heavy app) in Laravel with Eloquent models, proper migrations, Form Request validation, and a working authentication system using Breeze. This single project, done well, is what turns "I know PHP" into "I know Laravel" on your resume — legitimately.

---

## Phase 6: APIs, Security & Production Concerns (1.5 weeks)

This is what separates "can build a CRUD app" from "can be trusted in production."

### APIs
- [ ] REST principles: proper use of GET/POST/PUT/PATCH/DELETE, status codes that actually matter (200, 201, 400, 401, 403, 404, 422, 500)
- [ ] JSON request/response handling
- [ ] API authentication: Laravel Sanctum (token-based, the modern default) — know the difference between session auth and token auth
- [ ] Rate limiting basics

### Security (you've already touched some of this — go deeper)
- [ ] OWASP Top 10, at least conceptually — SQL injection (you know this), XSS, CSRF (you know this), broken auth, insecure deserialization
- [ ] Password hashing: `password_hash()`/`password_verify()` — know why bcrypt/argon2 over plain hashing, and never roll your own
- [ ] Input validation vs. sanitization — know the difference
- [ ] HTTPS, secure cookies, `httponly`/`secure` flags on session cookies

### Production Concerns
- [ ] Error handling in production vs. development (never show stack traces to end users)
- [ ] Logging (Monolog, or Laravel's built-in logging)
- [ ] Basic caching concepts (what Redis/Memcached are for, even if you don't master them yet)
- [ ] Environment configs: dev vs. staging vs. production settings

**Checkpoint Project:** Convert your Laravel app's endpoints into a proper JSON API (using API Resources), secure it with Sanctum token auth, and deploy it somewhere real (Railway, Render, or a VPS) instead of a free shared host.

---

## Phase 7: Interview & Job-Readiness Prep (1 week, ongoing)

- [ ] Be able to explain, out loud, without notes: the request lifecycle in PHP (browser → server → PHP → DB → response)
- [ ] Be able to explain the difference between `include`/`require` and `include_once`/`require_once`
- [ ] Be able to explain `==` vs. `===` and why type juggling causes bugs
- [ ] Be able to whiteboard a basic database schema for a given scenario (they will ask this)
- [ ] Practice explaining your Digital Voting System and Laravel rebuild project end-to-end — what problem it solves, what you'd improve, why you made specific technical choices
- [ ] Do 15–20 PHP-specific practice problems on LeetCode/HackerRank (arrays, strings, basic algorithms) — not because jobs need LeetCode mastery, but because screening rounds often include 1–2 easy problems
- [ ] Prepare 2–3 questions to ask interviewers about their codebase, deployment process, and team practices — shows you think beyond tutorials

---

## What NOT to Over-Invest In (Early On)

- **Don't chase every framework.** Laravel covers the vast majority of PHP jobs. Symfony is worth knowing exists, but don't split focus early.
- **Don't obsess over design patterns beyond the common ones.** Interviewers care more about whether you know *why* you'd use dependency injection than whether you've memorized all 23 Gang-of-Four patterns.
- **Don't skip testing to "move faster."** Even basic PHPUnit familiarity is a real differentiator for junior candidates — most skip it entirely.

---

## Suggested Resources

- **Official PHP Manual** (php.net) — genuinely excellent, use it as your primary reference over random blog posts
- **Laravel Official Docs** (laravel.com/docs) — among the best-written framework docs in any language
- **PHP: The Right Way** (phptherightway.com) — a free, concise, up-to-date community reference for modern PHP practices
- **Laracasts** — the standard video resource for Laravel specifically; free tier covers a lot of ground

---

## Progress Tracker

| Phase | Topic | Target Weeks | Status |
|---|---|---|---|
| 0 | Environment & Tooling | 0.5 | ☐ |
| 1 | Core PHP Language | 1.5–2 | ☐ |
| 2 | Object-Oriented PHP | 2 | ☐ |
| 3 | Databases Properly | 1.5 | ☐ |
| 4 | Modern PHP & Composer | 1 | ☐ |
| 5 | Laravel | 2.5–3 | ☐ |
| 6 | APIs, Security & Production | 1.5 | ☐ |
| 7 | Interview Prep | 1 (ongoing) | ☐ |

**Total: roughly 10–12 weeks** to go from "built one PHP project" to "genuinely job-ready PHP/Laravel backend developer."

---

*This roadmap is designed to be a living document — check off boxes as you go, and revisit Phase 7 continuously as you get closer to applying.*

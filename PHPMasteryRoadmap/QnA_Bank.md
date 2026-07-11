# PHP & Laravel Interview Q&A Bank

*Cover the answer, read only the question, say your answer out loud before checking. If you can't explain it in your own words in under 30 seconds, you don't know it yet.*

---

## Core PHP

**Q: What's the difference between `include` and `require`?**
A: Both import a file's code, but `include` only throws a warning and continues execution if the file is missing, while `require` throws a fatal error and stops the script. Use `require` for anything the app can't run without (like a config file); `include` for optional pieces.

**Q: What does `_once` do, and when would you need it?**
A: `include_once`/`require_once` prevents a file from being loaded twice in the same request — important because re-declaring a class or function that's already loaded causes a fatal error. Composer's autoloader makes this largely unnecessary in modern code, but you'll still see it in legacy codebases.

**Q: What's the difference between `==` and `===`?**
A: `==` compares value after type juggling (converting types to match); `===` compares value *and* type with no conversion. Classic gotcha: `0 == "abc"` was `true` in old PHP versions (fixed in PHP 8). Default to `===` unless you have a specific reason not to.

**Q: What does `declare(strict_types=1)` actually do?**
A: It forces type declarations on function parameters/returns to be enforced exactly, instead of PHP silently coercing types (e.g., passing `"5"` where an `int` is expected would normally be auto-converted; with strict types on, it throws a `TypeError` instead).

**Q: Explain PHP's null coalescing operator (`??`) and when you'd use it.**
A: `$value = $array['key'] ?? 'default';` returns `$array['key']` if it exists and isn't null, otherwise returns `'default'` — without throwing an "undefined key" warning. It's shorthand for an `isset()` check. `??=` does the same but assigns in place.

**Q: What's the difference between `match` and `switch`?**
A: `match` (PHP 8+) uses strict comparison (`===`) internally, has no fall-through, and is an expression (it returns a value you can assign). `switch` uses loose comparison, requires `break` to avoid fall-through, and is a statement, not an expression. Prefer `match` for anything returning a value.

**Q: What's the difference between a PHP array and an "associative array"?**
A: There's technically only one array type in PHP — it's ordered and can use either sequential integer keys (a "list") or string keys (a "map"). What other languages split into `Array` and `Dictionary`/`HashMap` is unified into one type in PHP; the distinction is just about which keys you use.

**Q: By default, does a PHP closure capture outer variables by value or by reference?**
A: By value — changes inside the closure don't affect the outer scope. Adding `&` (`use (&$var)`) captures by reference, so changes propagate outward. This is a common "what does this print" interview trap.

**Q: Name the core array functions you'd reach for to transform, filter, and collapse an array.**
A: `array_map($fn, $arr)` transforms every element; `array_filter($arr, $fn)` keeps elements matching a condition; `array_reduce($arr, $fn, $initial)` collapses the array into a single value. These three come up constantly in both real code and interviews.

**Q: What's the difference between `preg_match` and `preg_match_all`?**
A: `preg_match` finds the first match of a pattern and stops. `preg_match_all` finds every match in the string and returns them all in an array. Both use PCRE regex syntax.

---

## Object-Oriented PHP

**Q: Abstract class vs. interface — what's the difference, and when do you use each?**
A: An abstract class can contain real implementation plus abstract methods, and a class can only extend *one* abstract class. An interface defines a contract with no implementation, and a class can implement *many* interfaces. Use an interface when unrelated classes need to guarantee the same behavior; use an abstract class when related classes share common code.

**Q: Why does visibility (`private`/`protected`/`public`) actually matter — isn't it just extra typing?**
A: It protects a class's internal invariants. A `public` property can be mutated into an invalid state by any code anywhere. Making it `private` and exposing controlled methods means the class can guarantee its own correctness — callers can't reach in and break it directly.

**Q: What is Dependency Injection, in plain terms?**
A: Instead of a class creating its own dependencies internally (`new Database()` inside the class), you pass the dependency in through the constructor. This makes the class testable (you can pass in a fake/mock) and decoupled from one specific implementation.

**Q: Explain SOLID in one line each.**
A: **S**ingle Responsibility — a class should have one reason to change. **O**pen/Closed — open for extension, closed for modification. **L**iskov Substitution — a subclass should work anywhere its parent is expected. **I**nterface Segregation — many small specific interfaces beat one giant one. **D**ependency Inversion — depend on abstractions, not concrete implementations.

**Q: Why would you use a Trait instead of just inheritance?**
A: PHP classes can only extend one parent, but you often need to share behavior across unrelated class hierarchies (e.g., a `Loggable` trait usable in both a `User` class and a `PaymentService` class with no shared parent). Traits let you mix in shared code without forcing an artificial inheritance relationship.

**Q: What's a static method, and when is it appropriate to use one?**
A: A static method belongs to the class itself, not an instance, so it can't access `$this` or instance properties. Appropriate for stateless utility functions (`Math::square($x)`); overusing static methods for things that *do* have state makes code hard to test and mock.

**Q: What is a "magic method"? Name two.**
A: Methods prefixed with `__` that PHP calls automatically in specific situations — e.g., `__construct` (object creation), `__toString` (when an object is used as a string), `__get`/`__set` (accessing undefined properties). Powerful but easy to overuse in ways that make code hard to trace.

**Q: How does PHP handle "multiple inheritance"?**
A: It doesn't, for classes — a class can only `extend` one parent, to avoid the ambiguity ("diamond problem") multiple inheritance causes in other languages. Instead, PHP supports implementing multiple interfaces and using multiple Traits for shared code.

**Q: What does constructor property promotion (PHP 8+) do?**
A: It's a syntax shortcut — instead of declaring a property, writing a constructor parameter, and manually assigning it, you write `public function __construct(private string $name) {}` and PHP does all three in one line.

**Q: What's a readonly property (PHP 8.1+), and why use one?**
A: A property that can only be assigned once, typically in the constructor — any attempt to modify it afterward throws an error. Useful for value objects and immutable data where you want a guarantee the value never changes after creation.

---

## Databases

**Q: A query works fine with 100 rows but times out at 1 million rows. What do you check first?**
A: Whether the columns used in `WHERE`, `JOIN`, and `ORDER BY` are indexed. Without an index, the database does a full table scan — fine at small scale, disastrous at large scale. Also check for N+1 query patterns and whether you're selecting more columns/rows than actually needed.

**Q: Why do prepared statements actually prevent SQL injection — not just "because best practice"?**
A: A prepared statement sends the SQL structure and the user data as two separate things to the database driver. The data is bound into placeholders *after* the query plan is already fixed, so it's never parsed as SQL syntax. String-concatenating user input into a query means that input becomes part of the SQL itself — that's what allows injection.

**Q: What's a database transaction, and give a real example of when you'd need one.**
A: A transaction groups multiple queries so they either all succeed or all fail together. Example: recording a vote might involve inserting into `votes` and updating a `vote_count` column — if the second write fails after the first succeeded, you'd have corrupted data without wrapping both in `beginTransaction()` / `commit()` / `rollBack()`.

**Q: What's the N+1 query problem?**
A: Fetching 10 posts, then looping through them and running a separate query per post to get its author, results in 1 + 10 = 11 queries when it could've been 2 (or 1 with a join). It silently kills performance at scale and is one of the most common real-world PHP/Laravel bugs. Eloquent's `with()` (eager loading) is the standard fix.

**Q: What's a foreign key, and why not just enforce relationships in application code?**
A: A foreign key is a database-level constraint guaranteeing referential integrity — e.g., you can't insert a `vote` referencing a `candidate_id` that doesn't exist. Enforcing this only in PHP means any direct DB access, script, or bug bypassing your app logic can corrupt data. The database should be the last line of defense, not the only one.

**Q: `INNER JOIN` vs. `LEFT JOIN` — what's the difference?**
A: `INNER JOIN` only returns rows with a match in both tables. `LEFT JOIN` returns all rows from the left table, filling in `NULL` for unmatched columns from the right table. Use `LEFT JOIN` for things like "all users, including ones with zero orders."

**Q: Why is `SELECT *` discouraged in production code?**
A: It fetches every column even when you only need two, wasting bandwidth and memory. It also silently breaks assumptions if the schema changes (a new large column gets pulled every time without anyone noticing), and it obscures what data the code actually depends on.

**Q: PDO vs. MySQLi — which should you default to, and why?**
A: Default to PDO. It supports multiple database drivers (MySQL, PostgreSQL, SQLite) behind one consistent API, while MySQLi is MySQL-only. Both support prepared statements safely; PDO is just more flexible if the underlying database ever changes.

---

## Laravel

**Q: What problem does Eloquent's `with()` solve?**
A: The N+1 query problem, via eager loading. `Election::with('candidates')->get()` fetches all elections and all their candidates in 2 queries total, instead of 1 query for elections plus N queries (one per election) for candidates.

**Q: Explain Eloquent's relationship methods: `hasOne`, `hasMany`, `belongsTo`, `belongsToMany`.**
A: `hasOne` — this model owns exactly one of another (User hasOne Profile). `hasMany` — this model owns many of another (Election hasMany Candidates). `belongsTo` — the inverse side of hasOne/hasMany (Candidate belongsTo Election). `belongsToMany` — many-to-many through a pivot table (User belongsToMany Roles).

**Q: What is middleware, in one sentence?**
A: Code that runs before (or after) a request reaches your controller — used for things like "is this user authenticated?" or "is this request rate-limited?" — without repeating the same checks in every controller.

**Q: What's the difference between a Resource Controller and a regular controller?**
A: A Resource Controller follows a REST convention with 7 predefined methods (`index`, `create`, `store`, `show`, `edit`, `update`, `destroy`) that map cleanly onto `Route::resource()`, giving you a full CRUD interface with one route declaration instead of manually defining each route.

**Q: What's a Form Request, and why use one instead of validating inline in the controller?**
A: A dedicated class that keeps validation rules out of the controller, makes them reusable, and gives you a clean place for authorization logic (`authorize()`) alongside validation (`rules()`). Keeps controllers thin and focused.

**Q: Session auth vs. Sanctum token auth — when would you use each?**
A: Session auth (traditional server-rendered Laravel apps) stores a session ID in a cookie shared between browser and server. Sanctum token auth issues a token the client stores and sends in an `Authorization` header — needed when your API is consumed by something that can't rely on shared cookies, like a separate React SPA or mobile app.

**Q: What's the Laravel middleware pipeline, conceptually?**
A: A request passes through a stack of middleware layers before reaching the controller — each layer can inspect/modify the request or short-circuit with an early response (e.g., an unauthenticated user gets redirected before the controller ever runs). Think of it as an onion: request goes in through each layer, response comes back out in reverse.

**Q: What does `php artisan migrate` actually do?**
A: It runs any migration files that haven't been applied yet, executing their `up()` methods to create/alter database tables — and tracks which migrations have run in a `migrations` table, so re-running the command is safe and idempotent.

---

## Security

**Q: Explain CSRF and how Laravel protects against it by default.**
A: Cross-Site Request Forgery tricks a logged-in user's browser into submitting a request to your site (e.g., a hidden form on a malicious page that POSTs to `/transfer-funds`) using their existing session cookie. Laravel requires a CSRF token (embedded via `@csrf`, checked server-side) that an attacker's page can't know or forge, blocking the forged request.

**Q: What's the difference between authentication and authorization?**
A: Authentication answers "who are you?" (logging in, verifying identity). Authorization answers "what are you allowed to do?" (can this authenticated user delete this specific post?). You can be authenticated but not authorized for a given action — a distinction that comes up constantly.

**Q: Why not just use MD5 or SHA256 to hash passwords?**
A: Those are fast hash functions, designed for speed — exactly the wrong property for passwords, since speed makes brute-forcing feasible. `password_hash()` uses bcrypt/argon2, deliberately slow and with an automatic random salt, making brute-force and rainbow-table attacks impractical.

**Q: What's the difference between validating and sanitizing input?**
A: Validation checks whether input meets expected rules and rejects it if not (e.g., "this must be a valid email"). Sanitization modifies input to make it safe (e.g., stripping HTML tags). Prefer validating and rejecting bad input over silently "fixing" it — silent sanitization can mask bugs or attacker probing.

**Q: Why should stack traces never be shown to end users in production?**
A: They can leak file paths, database structure, and internal logic to an attacker. Laravel's `APP_DEBUG=false` in production shows a generic error page instead of a trace — always confirm this is set before deploying.

---

## System Design / Conceptual

**Q: Walk me through what happens between a user submitting a login form and landing on their dashboard.**
A: Browser sends a POST with credentials → web server routes it to PHP-FPM → the router matches the route → middleware runs (CSRF check, etc.) → controller receives validated input → queries the database for the user, verifies the password hash → on success, regenerates the session ID and stores the authenticated user ID in session → sends a redirect response with a `Set-Cookie` header → browser follows the redirect, sending the new session cookie automatically.

**Q: How would you design a database schema for a voting system from scratch?**
A: Core tables: `users` (id, name, email, password_hash, role), `elections` (id, title, start_date, end_date, status), `candidates` (id, election_id FK, name, party), `votes` (id, election_id FK, candidate_id FK, user_id FK, created_at) with a unique constraint on `(election_id, user_id)` to enforce one vote per user per election at the database level, not just in application code.

**Q: What would you do differently if you rebuilt your last project today?**
A: Good answer structure: name 2–3 concrete things, e.g. "move from raw PHP to Laravel for cleaner structure and Eloquent's eager loading," "add database-level unique constraints instead of only checking in PHP," "add automated tests instead of manual testing," "use Sanctum for a proper API layer instead of session-only auth." Interviewers want self-awareness and growth, not defensiveness about the original build.

**Q: How would you scale a PHP app that's starting to slow down under load?**
A: In order of effort: add database indexes and fix N+1 queries first (cheapest, highest impact); add caching (Redis) for expensive/repeated reads; use eager loading and pagination instead of loading everything at once; only then consider infrastructure scaling (more app servers, read replicas, queues for slow background work). Interviewers want to see you reach for the cheap fixes before "just add more servers."

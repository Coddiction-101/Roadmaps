# 🎯 Unified Java Backend + DSA Roadmap 2026
# Complete Learning Path for CS Students
# Single Document: No Confusion, No Separate Files

> **Version:** 3.0 | **Last Updated:** June 2026
> **Target:** BCA/CS Student → Java Backend Developer + DSA Mastery
> **Goal:** Internships & Entry-Level Roles (3-8 LPA)

---

## 📋 Table of Contents

1. [How to Read This Document](#how-to-read-this-document)
2. [Phase 1: Java Foundation (Weeks 1-4)](#phase-1-java-foundation-weeks-1-4)
3. [Phase 2: DSA in Java Begins (Weeks 3-8)](#phase-2-dsa-in-java-begins-weeks-3-8)
4. [Phase 3: Spring Boot + Advanced DSA (Weeks 9-16)](#phase-3-spring-boot--advanced-dsa-weeks-9-16)
5. [Phase 4: Projects + System Design + Interview DSA (Weeks 17-24)](#phase-4-projects--system-design--interview-dsa-weeks-17-24)
6. [Daily Schedule Template](#daily-schedule-template)
7. [Weekly Milestone Tracker](#weekly-milestone-tracker)
8. [Unified Technology Stack Table](#unified-technology-stack-table)
9. [DSA Topic Priority Matrix](#dsa-topic-priority-matrix)
10. [Java Backend Topic Priority Matrix](#java-backend-topic-priority-matrix)
11. [Integration Points: Where Backend Meets DSA](#integration-points-where-backend-meets-dsa)
12. [6-Month Execution Plan](#6-month-execution-plan)
13. [12-Month Execution Plan](#12-month-execution-plan)
14. [Interview Preparation Timeline](#interview-preparation-timeline)
15. [Resource Links](#resource-links)

---

## How to Read This Document

### Color Coding
| Color | Meaning |
|-------|---------|
| 🟦 **Blue sections** | Java Backend topics |
| 🟨 **Yellow sections** | DSA topics |
| 🟩 **Green sections** | Integration (Backend + DSA combined) |
| 🟥 **Red sections** | Critical priority - do not skip |

### Time Allocation Rule
| Activity | Daily Hours | Weekly Hours |
|----------|-------------|--------------|
| Java Backend learning/coding | 3-4 hours | 20-25 hours |
| DSA problem solving | 2-3 hours | 12-15 hours |
| Project building | 1-2 hours | 5-8 hours |
| **Total** | **6-8 hours/day** | **40-50 hours/week** |

### Parallel Track System
This roadmap uses **parallel tracks**: you learn Backend concepts AND solve DSA problems simultaneously, not sequentially. Every week has both.

---

## Phase 1: Java Foundation (Weeks 1-4)

### 🟥 Week 1: Java Syntax + Arrays (DSA Track 1)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice | Done
|-----|-------|---------------|----------|
| 1 | Setup | Install IntelliJ IDEA, JDK 21, Maven | Create first Maven project |
| 2 | Variables & Types | Primitives, wrappers, `var`, literals | Build a calculator |
| 3 | Operators | Arithmetic, logical, bitwise, ternary | Expression evaluator |
| 4 | Input/Output | `Scanner`, `BufferedReader`, `System` | CLI menu program |
| 5 | Conditionals | `if-else`, `switch` (incl. expressions) | Grade calculator |
| 6 | Loops | `for`, `while`, `do-while`, enhanced for | Pattern printing |
| 7 | **Mini Project** | CLI Banking System (deposit, withdraw, balance) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Array Basics | Traversal, finding max/min, sum, average | LeetCode Easy |
| 3-4 | Array Operations | Reverse array, rotate array, shift elements | LeetCode Easy |
| 5-6 | Searching in Arrays | Linear search, binary search implementation | LeetCode Easy |
| 7 | **Contest/Revision** | Solve 5 array problems timed | LeetCode |

**Week 1 DSA Problems:**
- LeetCode 1: Two Sum
- LeetCode 26: Remove Duplicates from Sorted Array
- LeetCode 283: Move Zeroes
- LeetCode 121: Best Time to Buy and Sell Stock
- LeetCode 217: Contains Duplicate

**Integration Point 🟩:**
- Use arrays to store transaction history in your Banking System
- Implement search functionality to find transactions by amount

---

### 🟥 Week 2: Methods + Strings (DSA Track 2)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Methods | Parameters, return types, overloading | Math utility class |
| 2 | Recursion | Base case, recursive case, stack frames | Factorial, Fibonacci |
| 3 | String Basics | Immutability, String Pool, `intern()` | String analyzer |
| 4 | String Methods | `substring()`, `split()`, `trim()`, `replace()` | Text processor |
| 5 | StringBuilder | Mutable strings, performance comparison | String concatenation benchmark |
| 6 | String Algorithms | Palindrome, anagram, frequency count | Word counter |
| 7 | **Mini Project** | Text Analysis Tool (word count, palindrome check, anagram detector) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | String Traversal | Character iteration, string reversal | LeetCode Easy |
| 3-4 | String Comparison | `equals()`, `==`, lexicographic compare | LeetCode Easy |
| 5-6 | String Algorithms | Two-pointer on strings, sliding window intro | LeetCode Easy-Medium |
| 7 | **Contest/Revision** | Solve 5 string problems timed | LeetCode |

**Week 2 DSA Problems:**
- LeetCode 344: Reverse String
- LeetCode 125: Valid Palindrome
- LeetCode 242: Valid Anagram
- LeetCode 14: Longest Common Prefix
- LeetCode 28: Find the Index of the First Occurrence in a String

**Integration Point 🟩:**
- Implement JWT token validation using string manipulation
- Build a URL parser for your backend API (path extraction)

---

### 🟥 Week 3: OOP Fundamentals + Linked Lists (DSA Track 3)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Classes & Objects | Fields, methods, constructors, `this` | Design a `Student` class |
| 2 | Encapsulation | Private fields, getters/setters, validation | Bank account class |
| 3 | Inheritance | `extends`, `super()`, method overriding | Employee hierarchy |
| 4 | Polymorphism | Overloading vs overriding, dynamic dispatch | Shape drawing system |
| 5 | Abstraction | Abstract classes, abstract methods | Payment processor design |
| 6 | Interfaces | `implements`, multiple inheritance, `default` methods | Plugin architecture |
| 7 | **Mini Project** | Library Management System (OOP design) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Linked List Basics | Singly linked list implementation from scratch | LeetCode |
| 3-4 | Linked List Operations | Insert, delete, reverse, detect cycle | LeetCode Easy-Medium |
| 5-6 | Doubly Linked List | Implementation, advantages over singly | Custom implementation |
| 7 | **Contest/Revision** | Solve 5 linked list problems timed | LeetCode |

**Week 3 DSA Problems:**
- LeetCode 206: Reverse Linked List
- LeetCode 21: Merge Two Sorted Lists
- LeetCode 141: Linked List Cycle
- LeetCode 876: Middle of the Linked List
- LeetCode 19: Remove Nth Node From End of List

**Integration Point 🟩:**
- Implement an undo/redo feature in your Library System using a doubly linked list
- Build a task queue (producer-consumer) using linked list

---

### 🟥 Week 4: Exception Handling + File I/O + Stacks & Queues (DSA Track 4)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Exceptions | `try-catch-finally`, `throw`, `throws` | Custom exception hierarchy |
| 2 | Checked vs Unchecked | When to use which, best practices | Input validation system |
| 3 | File Handling | `File`, `FileReader`, `BufferedReader` | File copy utility |
| 4 | Serialization | `Serializable`, `ObjectOutputStream` | Save/restore object state |
| 5 | NIO Basics | `Path`, `Files`, `Paths` | Modern file operations |
| 6 | Logging | `java.util.logging`, SLF4J intro | Add logging to projects |
| 7 | **Mini Project** | Student Record System (CRUD with file persistence) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Stack Implementation | Array-based and linked list-based stacks | LeetCode |
| 3-4 | Stack Applications | Balanced parentheses, postfix evaluation | LeetCode Easy-Medium |
| 5-6 | Queue Implementation | Linear queue, circular queue, deque | LeetCode |
| 7 | **Contest/Revision** | Solve 5 stack/queue problems timed | LeetCode |

**Week 4 DSA Problems:**
- LeetCode 20: Valid Parentheses
- LeetCode 155: Min Stack
- LeetCode 232: Implement Queue using Stacks
- LeetCode 622: Design Circular Queue
- LeetCode 739: Daily Temperatures (stack)

**Integration Point 🟩:**
- Use stack for undo functionality in your Student Record System
- Implement request queue processing (FIFO) for API simulation
- Build expression evaluator for a calculator API

---

## Phase 2: DSA in Java Begins (Weeks 3-8)

### 🟥 Week 5: Collections Framework Deep Dive + Trees (DSA Track 5)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | List Interface | `ArrayList` vs `LinkedList` internals | Performance benchmark |
| 2 | Set Interface | `HashSet`, `LinkedHashSet`, `TreeSet` | Duplicate remover |
| 3 | Map Interface | `HashMap` internals, `LinkedHashMap`, `TreeMap` | Frequency counter |
| 4 | Queue & Deque | `PriorityQueue`, `ArrayDeque` | Task scheduler |
| 5 | Iterators | `Iterator`, `ListIterator`, `forEach` | Custom iteration patterns |
| 6 | Collections Utility | `sort()`, `binarySearch()`, `reverse()` | Data processing pipeline |
| 7 | **Mini Project** | Contact Management System (using appropriate collections) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Binary Tree Basics | Tree traversal (inorder, preorder, postorder) | LeetCode |
| 3-4 | Binary Search Tree | Insertion, deletion, search, validation | LeetCode Medium |
| 5-6 | Tree Properties | Height, diameter, balanced check | LeetCode Medium |
| 7 | **Contest/Revision** | Solve 5 tree problems timed | LeetCode |

**Week 5 DSA Problems:**
- LeetCode 94: Binary Tree Inorder Traversal
- LeetCode 104: Maximum Depth of Binary Tree
- LeetCode 98: Validate Binary Search Tree
- LeetCode 230: Kth Smallest Element in a BST
- LeetCode 235: Lowest Common Ancestor of a Binary Search Tree

**Integration Point 🟩:**
- Use `TreeMap` for sorted data storage in Contact Management
- Implement autocomplete using Trie (tree structure)
- Build category hierarchy using tree traversal

---

### 🟥 Week 6: Generics + Sorting Algorithms (DSA Track 6)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Generics Basics | `T`, `E`, `K`, `V`, bounded types | Generic `Box` class |
| 2 | Generic Methods & Classes | Type inference, wildcards (`?`, `? extends`, `? super`) | Generic utility class |
| 3 | Generic Collections | Type-safe collections, raw types dangers | Refactor old code |
| 4 | Comparable & Comparator | Natural ordering, custom comparators | Sorting objects |
| 5 | Lambda Expressions | Syntax, functional interfaces, method references | Replace anonymous classes |
| 6 | Streams Intro | `stream()`, `filter()`, `map()`, `collect()` | Data transformation |
| 7 | **Mini Project** | Employee Management with sorting, filtering, streams | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Bubble & Selection Sort | Implementation, time/space complexity | Custom implementation |
| 3-4 | Insertion & Merge Sort | Divide and conquer, stability | Custom implementation |
| 5-6 | Quick Sort & Heap Sort | Partitioning, heapify, in-place sorting | Custom implementation |
| 7 | **Contest/Revision** | Sorting-based problems | LeetCode |

**Week 6 DSA Problems:**
- LeetCode 912: Sort an Array (implement merge/quick sort)
- LeetCode 148: Sort List (merge sort on linked list)
- LeetCode 215: Kth Largest Element in an Array (quickselect)
- LeetCode 347: Top K Frequent Elements (heap + hashmap)
- LeetCode 56: Merge Intervals (sorting + greedy)

**Integration Point 🟩:**
- Implement custom sorting for API response data
- Use `Comparator` for multi-field sorting in Employee Management
- Build pagination with sorting for REST API simulation

---

### 🟥 Week 7: Multithreading + Searching Algorithms (DSA Track 7)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Thread Creation | `Thread` class, `Runnable`, `Callable` | Multi-threaded counter |
| 2 | Thread Lifecycle | States, `sleep()`, `yield()`, `join()` | Thread state demonstrator |
| 3 | Synchronization | `synchronized`, locks, race conditions | Thread-safe bank account |
| 4 | Thread Safety | `volatile`, atomic classes, immutability | Concurrent counter |
| 5 | Executor Framework | `ExecutorService`, `Future`, `Callable` | Thread pool demo |
| 6 | Concurrent Collections | `ConcurrentHashMap`, `CopyOnWriteArrayList` | Concurrent cache |
| 7 | **Mini Project** | Download Manager (multi-threaded file downloader) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Binary Search | Standard, lower bound, upper bound | LeetCode |
| 3-4 | Binary Search Variations | Search in rotated array, find peak element | LeetCode Medium |
| 5-6 | Search in 2D Matrix | Row-column sorted matrix search | LeetCode Medium |
| 7 | **Contest/Revision** | 5 binary search problems timed | LeetCode |

**Week 7 DSA Problems:**
- LeetCode 704: Binary Search
- LeetCode 35: Search Insert Position
- LeetCode 33: Search in Rotated Sorted Array
- LeetCode 153: Find Minimum in Rotated Sorted Array
- LeetCode 74: Search a 2D Matrix

**Integration Point 🟩:**
- Use binary search for efficient log searching in Download Manager
- Implement rate limiting using token bucket (concurrent programming)
- Build search API with pagination using binary search concepts

---

### 🟥 Week 8: JDBC + Hashing (DSA Track 8)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | JDBC Basics | Driver, `Connection`, `Statement`, `ResultSet` | Connect to MySQL |
| 2 | CRUD Operations | Insert, select, update, delete with JDBC | Student CRUD app |
| 3 | PreparedStatement | Parameterized queries, SQL injection prevention | Secure login system |
| 4 | Connection Pooling | Why pooling matters, HikariCP intro | Pool configuration |
| 5 | Transaction Management | `commit()`, `rollback()`, ACID properties | Bank transfer system |
| 6 | DAO Pattern | Data Access Object design pattern | Refactor CRUD app |
| 7 | **Mini Project** | Student Management System (JDBC + MySQL) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Hashing Basics | Hash functions, collision resolution | Custom implementation |
| 3-4 | HashMap Problems | Two sum, group anagrams, longest substring | LeetCode Medium |
| 5-6 | HashSet Problems | Intersection, union, difference | LeetCode Medium |
| 7 | **Contest/Revision** | 5 hashing problems timed | LeetCode |

**Week 8 DSA Problems:**
- LeetCode 1: Two Sum (hashmap approach)
- LeetCode 49: Group Anagrams
- LeetCode 128: Longest Consecutive Sequence
- LeetCode 3: Longest Substring Without Repeating Characters
- LeetCode 454: 4Sum II

**Integration Point 🟩:**
- Implement caching layer using `HashMap` for JDBC queries
- Use hashing for password storage (with salt)
- Build session management using hash-based token storage

---

## Phase 3: Spring Boot + Advanced DSA (Weeks 9-16)

### 🟥 Week 9: Spring Boot Basics + Recursion & Backtracking (DSA Track 9)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Spring Boot Setup | Spring Initializr, project structure, auto-configuration | First REST API |
| 2 | Dependency Injection | `@Autowired`, constructor injection, `@Component` | Service layer design |
| 3 | REST Controllers | `@RestController`, `@RequestMapping`, HTTP methods | CRUD REST API |
| 4 | Request/Response | `@RequestBody`, `@PathVariable`, `@RequestParam` | Parameter handling |
| 5 | Exception Handling | `@ControllerAdvice`, `@ExceptionHandler` | Global error handling |
| 6 | Validation | `@Valid`, `@NotNull`, custom validators | Input validation API |
| 7 | **Project Milestone** | Task Manager REST API (full CRUD) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Recursion Patterns | Subsets, permutations, combinations | LeetCode Medium |
| 3-4 | Backtracking | N-Queens, Sudoku solver, maze problems | LeetCode Medium-Hard |
| 5-6 | Recursion on Trees | Path sum, root-to-leaf paths | LeetCode Medium |
| 7 | **Contest/Revision** | 5 recursion/backtracking problems | LeetCode |

**Week 9 DSA Problems:**
- LeetCode 78: Subsets
- LeetCode 46: Permutations
- LeetCode 51: N-Queens
- LeetCode 112: Path Sum
- LeetCode 17: Letter Combinations of a Phone Number

**Integration Point 🟩:**
- Use recursion for hierarchical data in REST API (category trees)
- Implement file system traversal API using backtracking
- Build permission hierarchy resolver

---

### 🟥 Week 10: Spring Data JPA + Graphs (DSA Track 10)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | JPA Basics | Entities, `@Entity`, `@Id`, `@GeneratedValue` | First entity mapping |
| 2 | Relationships | `@OneToOne`, `@OneToMany`, `@ManyToMany` | Relationship mapping |
| 3 | Repository Pattern | `JpaRepository`, custom queries, `@Query` | Repository design |
| 4 | JPQL & Native SQL | Query methods, pagination, sorting | Complex queries |
| 5 | Transactional | `@Transactional`, propagation, isolation | Consistent operations |
| 6 | DTO Pattern | `ModelMapper`, manual mapping, record classes | Clean API design |
| 7 | **Project Milestone** | Task Manager with JPA + PostgreSQL | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Graph Representation | Adjacency matrix, adjacency list | Custom implementation |
| 3-4 | Graph Traversal | BFS, DFS on graphs | LeetCode Medium |
| 5-6 | Graph Applications | Cycle detection, topological sort | LeetCode Medium |
| 7 | **Contest/Revision** | 5 graph problems timed | LeetCode |

**Week 10 DSA Problems:**
- LeetCode 200: Number of Islands
- LeetCode 133: Clone Graph
- LeetCode 207: Course Schedule (topological sort)
- LeetCode 210: Course Schedule II
- LeetCode 994: Rotting Oranges (BFS)

**Integration Point 🟩:**
- Model social network connections using graph (JPA relationships)
- Implement recommendation engine using graph traversal
- Build dependency resolver for microservices

---

### 🟥 Week 11: Spring Security + Dynamic Programming (DSA Track 11)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Security Basics | Authentication vs authorization, JWT concepts | Theory |
| 2 | Spring Security Config | `SecurityFilterChain`, password encoding | Basic security setup |
| 3 | JWT Implementation | `jjwt` library, token generation, validation | JWT auth system |
| 4 | Role-Based Access | `@PreAuthorize`, `@Secured`, method security | RBAC implementation |
| 5 | OAuth2 Basics | Authorization code flow, resource server | OAuth2 simulation |
| 6 | HTTPS & CORS | SSL basics, CORS configuration | Secure API setup |
| 7 | **Project Milestone** | Secure Task Manager (JWT + RBAC) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | DP Introduction | Memoization, tabulation, Fibonacci | LeetCode Easy |
| 3-4 | 1D DP | Climbing stairs, house robber, coin change | LeetCode Medium |
| 5-6 | 2D DP | Grid paths, edit distance, LCS | LeetCode Medium |
| 7 | **Contest/Revision** | 5 DP problems timed | LeetCode |

**Week 11 DSA Problems:**
- LeetCode 509: Fibonacci Number
- LeetCode 70: Climbing Stairs
- LeetCode 198: House Robber
- LeetCode 322: Coin Change
- LeetCode 1143: Longest Common Subsequence

**Integration Point 🟩:**
- Use DP for optimizing database query plans
- Implement caching with memoization pattern
- Build rate limiter using sliding window (DP concept)

---

### 🟥 Week 12: REST API Design + Greedy Algorithms (DSA Track 12)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | REST Principles | Resource naming, HTTP methods, status codes | API design |
| 2 | HATEOAS & Versioning | API evolution strategies | Versioned API |
| 3 | OpenAPI/Swagger | Documentation generation, `springdoc-openapi` | Auto-generated docs |
| 4 | Pagination | Offset vs cursor, `Pageable`, `Page` | Paginated API |
| 5 | Filtering & Sorting | Specification API, QueryDSL | Advanced queries |
| 6 | API Testing | Postman, `MockMvc`, integration tests | Test suite |
| 7 | **Project Milestone** | E-Commerce API (products, orders, users) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Greedy Basics | Activity selection, fractional knapsack | LeetCode Medium |
| 3-4 | Interval Problems | Merge intervals, non-overlapping intervals | LeetCode Medium |
| 5-6 | Greedy on Arrays | Jump game, gas station, candy distribution | LeetCode Medium |
| 7 | **Contest/Revision** | 5 greedy problems timed | LeetCode |

**Week 12 DSA Problems:**
- LeetCode 55: Jump Game
- LeetCode 435: Non-overlapping Intervals
- LeetCode 134: Gas Station
- LeetCode 135: Candy
- LeetCode 406: Queue Reconstruction by Height

**Integration Point 🟩:**
- Use greedy for request scheduling in API gateway
- Implement load balancing using greedy approach
- Build meeting scheduler API

---

### 🟥 Week 13: Microservices Intro + Heap & Priority Queue (DSA Track 13)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Microservices Concepts | Monolith vs microservices, bounded contexts | Architecture design |
| 2 | Spring Cloud Gateway | API gateway, routing, filters | Gateway setup |
| 3 | Service Discovery | Eureka server, client registration | Service registry |
| 4 | Inter-service Communication | `RestTemplate`, `WebClient`, Feign | Service client |
| 5 | Circuit Breaker | Resilience4j, fallback mechanisms | Fault tolerance |
| 6 | Config Server | Centralized configuration | Externalized config |
| 7 | **Project Milestone** | Microservices demo (2 services + gateway) | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Heap Basics | Min heap, max heap, heapify | Custom implementation |
| 3-4 | Priority Queue | `PriorityQueue` in Java, applications | LeetCode Medium |
| 5-6 | Top-K Problems | Kth largest, top frequent elements | LeetCode Medium |
| 7 | **Contest/Revision** | 5 heap problems timed | LeetCode |

**Week 13 DSA Problems:**
- LeetCode 215: Kth Largest Element in an Array
- LeetCode 347: Top K Frequent Elements
- LeetCode 23: Merge k Sorted Lists
- LeetCode 295: Find Median from Data Stream
- LeetCode 253: Meeting Rooms II

**Integration Point 🟩:**
- Use priority queue for task scheduling in microservices
- Implement rate limiting with heap-based sliding window
- Build leaderboard API using heap

---

### 🟥 Week 14: Docker + Trie & Advanced Strings (DSA Track 14)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | Docker Basics | Images, containers, Dockerfile syntax | Containerize Spring app |
| 2 | Docker Compose | Multi-container setup, networking | Compose for app + DB |
| 3 | Spring Boot Docker | Jib, layered jars, multi-stage builds | Optimized image |
| 4 | CI/CD Basics | GitHub Actions, automated build/test | CI pipeline |
| 5 | Testing | Unit tests (`JUnit`, `Mockito`), integration tests | Test coverage |
| 6 | Code Quality | SonarQube, checkstyle, SpotBugs | Quality gates |
| 7 | **Project Milestone** | Dockerized E-Commerce API with CI/CD | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Trie Implementation | Insert, search, prefix search | Custom implementation |
| 3-4 | Trie Applications | Auto-complete, word search | LeetCode Medium |
| 5-6 | Advanced Strings | KMP, Rabin-Karp, Manacher's | LeetCode Hard |
| 7 | **Contest/Revision** | 5 advanced string/trie problems | LeetCode |

**Week 14 DSA Problems:**
- LeetCode 208: Implement Trie (Prefix Tree)
- LeetCode 212: Word Search II
- LeetCode 28: Find the Index of the First Occurrence (KMP)
- LeetCode 5: Longest Palindromic Substring
- LeetCode 76: Minimum Window Substring

**Integration Point 🟩:**
- Implement auto-complete API using Trie
- Build search suggestion engine
- Use KMP for log pattern matching

---

### 🟥 Week 15: AWS/Cloud + Union-Find & Advanced Graphs (DSA Track 15)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | AWS Basics | EC2, S3, RDS, IAM concepts | Free tier setup |
| 2 | Deploy to EC2 | SSH, systemd service, Nginx reverse proxy | Manual deployment |
| 3 | RDS Integration | PostgreSQL on RDS, connection security | Cloud database |
| 4 | S3 Integration | File upload/download, presigned URLs | File storage API |
| 5 | Monitoring | CloudWatch, application metrics | Observable system |
| 6 | Infrastructure as Code | Terraform basics (optional) | Automated infra |
| 7 | **Project Milestone** | Deployed E-Commerce API on AWS | **Live URL** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Union-Find | Path compression, union by rank | Custom implementation |
| 3-4 | Union-Find Applications | Connected components, MST (Kruskal) | LeetCode Medium |
| 5-6 | Advanced Graphs | Dijkstra, Bellman-Ford, Floyd-Warshall | LeetCode Medium-Hard |
| 7 | **Contest/Revision** | 5 advanced graph problems | LeetCode |

**Week 15 DSA Problems:**
- LeetCode 200: Number of Islands (Union-Find)
- LeetCode 261: Graph Valid Tree
- LeetCode 323: Number of Connected Components
- LeetCode 743: Network Delay Time (Dijkstra)
- LeetCode 787: Cheapest Flights Within K Stops

**Integration Point 🟩:**
- Use Union-Find for friend recommendation system
- Implement shortest path for delivery routing API
- Build network topology analyzer

---

### 🟥 Week 16: System Design Basics + Sliding Window & Two Pointers (DSA Track 16)

#### 🟦 Java Backend Track
| Day | Topic | What to Learn | Practice |
|-----|-------|---------------|----------|
| 1 | System Design Intro | Scalability, availability, CAP theorem | Theory |
| 2 | Database Design | Normalization, indexing, query optimization | Schema design |
| 3 | Caching | Redis, cache patterns, eviction strategies | Redis integration |
| 4 | Message Queues | RabbitMQ/Kafka basics, async processing | Queue integration |
| 5 | Load Balancing | Round-robin, least connections, health checks | Nginx LB setup |
| 6 | Database Scaling | Sharding, replication, read replicas | Design discussion |
| 7 | **Project Milestone** | System Design Document for your E-Commerce API | **GitHub Push** |

#### 🟨 DSA Track (Parallel)
| Day | Topic | Problems to Solve | Platform |
|-----|-------|-------------------|----------|
| 1-2 | Two Pointers | Pair sum, 3Sum, container with most water | LeetCode Medium |
| 3-4 | Sliding Window | Fixed window, variable window, substring problems | LeetCode Medium |
| 5-6 | Combined Techniques | Two pointers + sliding window | LeetCode Medium-Hard |
| 7 | **Contest/Revision** | 5 problems timed | LeetCode |

**Week 16 DSA Problems:**
- LeetCode 15: 3Sum
- LeetCode 11: Container With Most Water
- LeetCode 3: Longest Substring Without Repeating Characters
- LeetCode 438: Find All Anagrams in a String
- LeetCode 239: Sliding Window Maximum

**Integration Point 🟩:**
- Use sliding window for real-time analytics API
- Implement rate limiting with sliding window counter
- Build substring search for log analysis

---

## Phase 4: Projects + System Design + Interview DSA (Weeks 17-24)

### 🟥 Week 17: Major Project 1 + Interview DSA Review 1

#### 🟩 Combined Track
| Day | Backend Activity | DSA Activity | Integration |
|-----|-----------------|------------|-------------|
| 1 | Project planning: Feature list, DB schema, API design | Review: Arrays, Strings (10 problems) | Design API with efficient algorithms |
| 2 | Implement authentication & authorization | Review: Linked Lists (5 problems) | Use linked list for activity log |
| 3 | Implement core business logic | Review: Stacks & Queues (5 problems) | Use stack for undo operations |
| 4 | Implement CRUD APIs with pagination | Review: Trees (5 problems) | Tree-based category system |
| 5 | Add caching with Redis | Review: Hashing (5 problems) | Hash-based session store |
| 6 | Write tests (unit + integration) | Review: Binary Search (5 problems) | Search optimization |
| 7 | **Deploy & Document** | **Mock Interview 1** | **GitHub + Live URL** |

**Project Idea:** URL Shortener Service (like bit.ly)
- **Backend:** Spring Boot, JPA, PostgreSQL, Redis, Docker
- **DSA Used:** Hashing (URL mapping), Base62 encoding, rate limiting

---

### 🟥 Week 18: Major Project 2 + Interview DSA Review 2

#### 🟩 Combined Track
| Day | Backend Activity | DSA Activity | Integration |
|-----|-----------------|------------|-------------|
| 1 | Project planning: Real-time features, WebSocket design | Review: Graphs (5 problems) | Social graph modeling |
| 2 | Implement WebSocket for real-time updates | Review: DP (5 problems) | Optimize recommendation |
| 3 | Implement notification system | Review: Recursion & Backtracking (5 problems) | Permission tree traversal |
| 4 | Add file upload to S3 | Review: Heaps (5 problems) | Priority notification queue |
| 5 | Implement search with Elasticsearch (optional) | Review: Tries (5 problems) | Auto-complete search |
| 6 | Performance testing & optimization | Review: Greedy (5 problems) | Request scheduling |
| 7 | **Deploy & Document** | **Mock Interview 2** | **GitHub + Live URL** |

**Project Idea:** Real-time Chat Application Backend
- **Backend:** Spring Boot, WebSocket, MongoDB, Redis, Docker
- **DSA Used:** Graphs (friend connections), Trie (message search), Heap (priority messages)

---

### 🟥 Week 19: Major Project 3 + Interview DSA Review 3

#### 🟩 Combined Track
| Day | Backend Activity | DSA Activity | Integration |
|-----|-----------------|------------|-------------|
| 1 | Project planning: Microservices architecture | Review: Sliding Window & Two Pointers (5 problems) | Stream processing |
| 2 | Implement API Gateway & service discovery | Review: Union-Find (5 problems) | Service health monitoring |
| 3 | Implement inter-service communication | Review: Advanced Graphs (5 problems) | Service dependency graph |
| 4 | Add distributed tracing | Review: All patterns mixed (10 problems) | Algorithm selection |
| 5 | Implement circuit breaker & retry logic | Review: Company-specific problems (5) | Real-world application |
| 6 | Load testing with JMeter/k6 | Full mock test (timed, 5 problems) | Pressure handling |
| 7 | **Deploy & Document** | **Mock Interview 3** | **GitHub + Live URL** |

**Project Idea:** E-Commerce Platform (Microservices)
- **Backend:** Spring Boot, Spring Cloud, PostgreSQL, Redis, Kafka, Docker
- **DSA Used:** All topics (inventory management, recommendation, routing)

---

### 🟥 Weeks 20-24: Interview Preparation Intensive

#### 🟩 Combined Daily Schedule
| Time | Activity | Focus |
|------|----------|-------|
| 6:00-8:00 AM | DSA Problems | 2-3 LeetCode medium/hard |
| 8:00-9:00 AM | Breakfast + Review | Yesterday's solutions |
| 9:00-12:00 PM | Backend Coding | Project improvements, new features |
| 12:00-1:00 PM | Lunch + Light reading | Tech blogs, system design articles |
| 1:00-3:00 PM | System Design Study | Design patterns, architecture |
| 3:00-5:00 PM | DSA Revision | Weak topics, company-specific prep |
| 5:00-7:00 PM | Mock Interviews | Peer interviews, recording yourself |
| 7:00-8:00 PM | Dinner + Relax | — |
| 8:00-10:00 PM | Backend Revision | Java concepts, Spring Boot internals |
| 10:00-11:00 PM | Plan Tomorrow | Problem selection, goals |

#### Weekly Rotation
| Week | DSA Focus | Backend Focus | Interview Focus |
|------|-----------|---------------|-----------------|
| 20 | Arrays, Strings, Linked Lists | Java internals, JVM | HR questions, introduction |
| 21 | Trees, Graphs, DP | Spring Boot auto-configuration | Technical deep dives |
| 22 | System Design DSA | Microservices patterns | System design rounds |
| 23 | Company-specific (Google, Amazon) | Resume projects | Behavioral questions |
| 24 | Full revision, weak areas | Mock coding on whiteboard | Final polish |

---

## Daily Schedule Template

### Standard Day (No Project Deadline)
| Time Slot | Backend | DSA | Notes |
|-----------|---------|-----|-------|
| 6:00-8:00 AM | — | 2 LeetCode problems | Fresh mind for algorithms |
| 8:00-9:00 AM | Review yesterday's code | Review solutions | — |
| 9:00-12:00 PM | New backend topic + coding | — | Deep work block |
| 12:00-1:00 PM | — | — | Lunch break |
| 1:00-2:00 PM | — | 1 LeetCode problem | Post-lunch lighter work |
| 2:00-5:00 PM | Backend project work | — | Implementation time |
| 5:00-6:00 PM | — | 1 LeetCode problem | — |
| 6:00-7:00 PM | Code review, documentation | — | — |
| 7:00-8:00 PM | — | — | Dinner |
| 8:00-9:00 PM | Backend reading (docs, blogs) | — | Passive learning |
| 9:00-10:00 PM | — | Revise today's problems | Spaced repetition |

### Project Deadline Day
| Time Slot | Activity |
|-----------|----------|
| 6:00-8:00 AM | DSA (maintain streak) |
| 8:00 AM-6:00 PM | Backend project (focus blocks with breaks) |
| 6:00-7:00 PM | DSA (1 problem minimum) |
| 7:00-8:00 PM | Dinner |
| 8:00-10:00 PM | Project polish, testing, GitHub push |

---

## Weekly Milestone Tracker

| Week | Backend Milestone | DSA Milestone | Combined Output |
|------|-------------------|---------------|-----------------|
| 1 | CLI Banking System | 10 Array problems | GitHub repo with 2 projects |
| 2 | Text Analysis Tool | 10 String problems | +2 projects, 20 problems |
| 3 | Library Management (OOP) | 10 Linked List problems | +1 project, 30 problems |
| 4 | Student Record System | 10 Stack/Queue problems | +1 project, 40 problems |
| 5 | Contact Management | 10 Tree problems | +1 project, 50 problems |
| 6 | Employee Management | 10 Sorting problems | +1 project, 60 problems |
| 7 | Download Manager | 10 Binary Search problems | +1 project, 70 problems |
| 8 | Student Management (JDBC) | 10 Hashing problems | +1 project, 80 problems |
| 9 | Task Manager REST API | 10 Recursion problems | +1 project, 90 problems |
| 10 | Task Manager + JPA | 10 Graph problems | +1 project, 100 problems |
| 11 | Secure Task Manager | 10 DP problems | +1 project, 110 problems |
| 12 | E-Commerce API | 10 Greedy problems | +1 project, 120 problems |
| 13 | Microservices Demo | 10 Heap problems | +1 project, 130 problems |
| 14 | Dockerized E-Commerce | 10 Trie/String problems | +1 project, 140 problems |
| 15 | AWS Deployed API | 10 Advanced Graph problems | Live URL, 150 problems |
| 16 | System Design Doc | 10 Sliding Window problems | Document, 160 problems |
| 17 | URL Shortener | Review: 30 problems | Major project 1 |
| 18 | Chat Backend | Review: 30 problems | Major project 2 |
| 19 | E-Commerce Microservices | Review: 30 problems | Major project 3 |
| 20 | Polish & Optimize | Mock tests | Interview ready |
| 21 | Polish & Optimize | Mock tests | Interview ready |
| 22 | Polish & Optimize | Mock tests | Interview ready |
| 23 | Polish & Optimize | Mock tests | Interview ready |
| 24 | Final Review | Final Review | **PLACEMENT READY** |

---

## Unified Technology Stack Table

| Category | Technology | Priority | Used In Backend | Used In DSA | Status |
|----------|------------|----------|-----------------|-------------|--------|
| **Language** | Java 21 | Must Learn | Core language | Problem solving | [ ] |
| **Build Tool** | Maven | Must Learn | Dependency management | Project structure | [ ] |
| **IDE** | IntelliJ IDEA | Must Learn | Development | Debugging | [ ] |
| **Framework** | Spring Boot 3.x | Must Learn | REST APIs, DI | — | [ ] |
| **ORM** | Hibernate/JPA | Must Learn | Database layer | — | [ ] |
| **Database** | PostgreSQL | Must Learn | Primary database | — | [ ] |
| **Cache** | Redis | Important | Performance | — | [ ] |
| **Security** | Spring Security + JWT | Must Learn | Authentication | — | [ ] |
| **Docs** | OpenAPI/Swagger | Must Learn | API documentation | — | [ ] |
| **Testing** | JUnit 5 + Mockito | Must Learn | Unit testing | — | [ ] |
| **Container** | Docker | Must Learn | Deployment | — | [ ] |
| **CI/CD** | GitHub Actions | Important | Automation | — | [ ] |
| **Cloud** | AWS (EC2, RDS, S3) | Important | Deployment | — | [ ] |
| **Version Control** | Git + GitHub | Must Learn | Code management | Portfolio | [ ] |
| **DSA Platform** | LeetCode | Must Learn | — | Daily practice | [ ] |
| **DSA Language** | Java | Must Learn | — | All problems | [ ] |
| **System Design** | High Level Design | Important | Architecture | — | [ ] |

---

## DSA Topic Priority Matrix

| Topic | Interview Frequency | Learning Difficulty | Priority | Target Problems | Week |
|-------|---------------------|---------------------|----------|-----------------|------|
| Arrays | Very High | Easy | P0 | 30 | 1, 5 |
| Strings | Very High | Easy | P0 | 25 | 2, 14 |
| Linked Lists | High | Easy | P0 | 20 | 3 |
| Stacks & Queues | High | Medium | P0 | 15 | 4 |
| Trees | Very High | Medium | P0 | 25 | 5 |
| Binary Search | Very High | Medium | P0 | 20 | 7 |
| Hashing | Very High | Easy | P0 | 20 | 8 |
| Sorting | Medium | Medium | P1 | 10 | 6 |
| Graphs | High | Hard | P0 | 20 | 10, 15 |
| Recursion & Backtracking | High | Hard | P0 | 15 | 9 |
| Dynamic Programming | Very High | Hard | P0 | 25 | 11 |
| Greedy | Medium | Medium | P1 | 10 | 12 |
| Heaps | Medium | Medium | P1 | 10 | 13 |
| Tries | Medium | Medium | P1 | 8 | 14 |
| Union-Find | Medium | Medium | P1 | 8 | 15 |
| Sliding Window | High | Medium | P0 | 12 | 16 |
| Two Pointers | High | Easy | P0 | 12 | 16 |
| Bit Manipulation | Low | Medium | P2 | 5 | — |
| Segment Trees | Low | Hard | P2 | 3 | — |

**Total Target: 300+ problems by Week 24**

---

## Java Backend Topic Priority Matrix

| Topic | Interview Frequency | Learning Difficulty | Priority | Week |
|-------|---------------------|---------------------|----------|------|
| Java Core (OOP, Collections) | Very High | Easy | P0 | 1-5 |
| Exception Handling | High | Easy | P0 | 4 |
| Multithreading | High | Hard | P0 | 7 |
| JDBC | Medium | Easy | P1 | 8 |
| Spring Boot Core | Very High | Medium | P0 | 9-10 |
| Spring Data JPA | Very High | Medium | P0 | 10 |
| Spring Security | High | Hard | P0 | 11 |
| REST API Design | Very High | Medium | P0 | 12 |
| Microservices | High | Hard | P1 | 13 |
| Docker | High | Medium | P0 | 14 |
| AWS/Cloud | Medium | Medium | P1 | 15 |
| System Design | High | Hard | P1 | 16 |
| Testing | High | Medium | P0 | 14 |
| CI/CD | Medium | Medium | P1 | 14 |
| Message Queues | Medium | Hard | P2 | 16 |
| Caching | High | Medium | P1 | 16 |

---

## Integration Points: Where Backend Meets DSA

| Backend Feature | DSA Concept | Real Application |
|-----------------|-------------|------------------|
| URL Shortener | Hashing + Base62 | Generate short URLs |
| Rate Limiter | Sliding Window | API throttling |
| Search API | Trie + Binary Search | Auto-complete, log search |
| Friend Suggestions | Graph BFS | Social network features |
| Task Scheduler | Priority Queue | Background job processing |
| Undo/Redo | Stack | User action history |
| Cache Eviction | LRU (LinkedHashMap) | Redis-like caching |
| Recommendation | Graph + DP | Product recommendations |
| Load Balancer | Round Robin / Greedy | Request distribution |
| Database Index | B-Tree | Fast query performance |
| Session Store | HashMap | In-memory session management |
| Notification Queue | Queue + Heap | Priority notifications |
| Dependency Resolver | Topological Sort | Microservice startup order |
| Route Optimization | Dijkstra | Delivery routing |
| Data Pagination | Binary Search | Large dataset navigation |

---

## 6-Month Execution Plan

### Month 1: Foundation (Weeks 1-4)
**Goal:** Java syntax mastery + 40 DSA problems + 4 mini projects

| Deliverable | Metric |
|-------------|--------|
| Java fundamentals | Can explain any concept without notes |
| DSA problems solved | 40 (Arrays, Strings, Linked Lists, Stacks/Queues) |
| GitHub projects | 4 (Banking, Text Analysis, Library, Student Record) |
| LeetCode consistency | 7 days/week, minimum 2 problems/day |

### Month 2: Core DSA + OOP (Weeks 5-8)
**Goal:** Collections mastery + 80 more DSA problems + JDBC integration

| Deliverable | Metric |
|-------------|--------|
| Collections Framework | Can choose right collection for any scenario |
| DSA problems solved | 120 total (Trees, Sorting, Binary Search, Hashing) |
| GitHub projects | 8 total (+ Contact, Employee, Download Manager, JDBC Student) |
| Database skills | Can write complex SQL, design schemas |

### Month 3: Spring Boot Begins (Weeks 9-12)
**Goal:** REST API development + 160 total DSA problems

| Deliverable | Metric |
|-------------|--------|
| Spring Boot | Can build secure, documented REST APIs |
| DSA problems solved | 160 total (Recursion, Graphs, DP, Greedy) |
| GitHub projects | 12 total (+ Task Manager, Secure Task Manager, E-Commerce API) |
| API design | Understand REST principles, pagination, versioning |

### Month 4: Advanced Backend + DSA (Weeks 13-16)
**Goal:** Microservices + 220 total DSA problems + System Design basics

| Deliverable | Metric |
|-------------|--------|
| Microservices | Can design and implement service architecture |
| DSA problems solved | 220 total (Heaps, Tries, Advanced Graphs, Sliding Window) |
| DevOps | Docker, CI/CD, AWS deployment |
| System Design | Can design scalable systems (cache, DB, LB) |

### Month 5: Projects + Integration (Weeks 17-20)
**Goal:** 3 major projects + 280 DSA problems + interview readiness

| Deliverable | Metric |
|-------------|--------|
| Major projects | 3 (URL Shortener, Chat Backend, E-Commerce Microservices) |
| DSA problems solved | 280 total |
| Live deployments | 3 deployed applications |
| Mock interviews | 10+ practice sessions |

### Month 6: Interview Preparation (Weeks 21-24)
**Goal:** Placement ready

| Deliverable | Metric |
|-------------|--------|
| DSA problems solved | 300+ total |
| Mock interviews | 20+ sessions |
| Company-specific prep | Target company problem sets |
| Resume & LinkedIn | Optimized, recruiter-ready |
| Applications | 50+ companies applied |

---

## 12-Month Execution Plan

| Quarter | Focus | Backend Goal | DSA Goal | Output |
|---------|-------|-------------|----------|--------|
| Q1 (Months 1-3) | Foundation | Java, JDBC, Spring Boot basics | 160 problems | 12 projects, REST APIs |
| Q2 (Months 4-6) | Advanced | Microservices, DevOps, System Design | 300 problems | 3 major projects, deployed |
| Q3 (Months 7-9) | Specialization | Choose: Cloud/Security/Performance | 400 problems | Open source contributions |
| Q4 (Months 10-12) | Career | Job applications, interviews, offers | Maintain + company-specific | Job offer(s) |

---

## Interview Preparation Timeline

### 3 Months Before Interviews
| Activity | Frequency | Details |
|----------|-----------|---------|
| DSA problems | Daily | 3 medium/hard per day |
| System design | Weekly | 1 system design study per week |
| Mock interviews | Weekly | 1 peer mock interview |
| Project review | Weekly | Explain projects without notes |

### 1 Month Before Interviews
| Activity | Frequency | Details |
|----------|-----------|---------|
| Company-specific prep | Daily | Target company's favorite problems |
| Behavioral prep | Daily | STAR method stories |
| Mock interviews | 3x/week | With seniors, mentors, or platforms |
| Resume polish | Weekly | Tailor for each company |

### 1 Week Before Interview
| Activity | Details |
|----------|---------|
| Light DSA | Review favorite problems, don't learn new |
| Project deep dive | Know every line of your code |
| Company research | Products, tech stack, recent news |
| Rest | Sleep well, stay calm |

---

## Resource Links

### Java Backend
| Resource | Link | Purpose |
|----------|------|---------|
| Spring Boot Docs | https://spring.io/projects/spring-boot | Official reference |
| Baeldung | https://www.baeldung.com | Practical tutorials |
| Java Brains (YouTube) | https://www.youtube.com/c/JavaBrainsChannel | Video courses |
| Amigoscode | https://www.youtube.com/c/Amigoscode | Spring Boot crash course |

### DSA
| Resource | Link | Purpose |
|----------|------|---------|
| LeetCode | https://leetcode.com | Primary practice platform |
| NeetCode Roadmap | https://neetcode.io/roadmap | Structured problem list |
| Striver's SDE Sheet | https://takeuforward.org/interviews/strivers-sde-sheet-top-coding-interview-problems/ | Curated problems |
| Abdul Bari (YouTube) | https://www.youtube.com/channel/UCZCFT11CWBi3MHNlGf019nw | Algorithm explanations |

### System Design
| Resource | Link | Purpose |
|----------|------|---------|
| System Design Primer | https://github.com/donnemartin/system-design-primer | Open source learning |
| ByteByteGo | https://www.youtube.com/c/ByteByteGo | Visual explanations |
| Designing Data-Intensive Applications | Book | Deep dive |

### Practice Platforms
| Platform | Best For |
|----------|----------|
| LeetCode | Primary DSA practice |
| HackerRank | Structured learning |
| CodeChef | Competitive programming |
| GeeksforGeeks | Interview experiences |

---

## Success Metrics

### By Week 12 (Midpoint)
- [ ] 160+ DSA problems solved
- [ ] 12 GitHub projects
- [ ] 1 deployed application
- [ ] Can build REST API from scratch in 2 hours
- [ ] Can solve any easy and most medium LeetCode problems

### By Week 24 (End)
- [ ] 300+ DSA problems solved
- [ ] 15+ GitHub projects (3 major)
- [ ] 3 deployed applications with live URLs
- [ ] Can design basic scalable systems
- [ ] Can solve medium LeetCode consistently, some hard
- [ ] Ready for technical interviews

---

## Common Pitfalls to Avoid

| Pitfall | Why It Hurts | Solution |
|---------|-------------|----------|
| Doing DSA first, Backend later | You forget DSA while learning Backend | Parallel tracks from Day 1 |
| Skipping projects for more DSA | No proof of backend skills | Build 1 project per week minimum |
| Not using Java for DSA | Can't answer "solve in Java" in interviews | All DSA in Java from start |
| Ignoring system design | Senior roles require this | Start Week 16, not later |
| No GitHub activity | Recruiters can't verify skills | Push code daily |
| Skipping mock interviews | Real interview pressure is different | Start mocks in Month 5 |
| Learning too many technologies | Shallow knowledge everywhere | Stick to this roadmap |
| Not revising old DSA topics | Forgotten concepts in interviews | Weekly revision sessions |

---

## Final Checklist: Placement Ready

### Technical Skills
- [ ] Can explain Java memory model, GC, JVM internals
- [ ] Can build Spring Boot REST API with JPA, Security, Tests
- [ ] Can Dockerize and deploy to cloud
- [ ] Can solve 300+ LeetCode problems (mix of easy/medium/hard)
- [ ] Can design systems with caching, DB, load balancing

### Portfolio
- [ ] 15+ GitHub repositories
- [ ] 3 major projects with live demos
- [ ] Technical blog (5+ posts)
- [ ] Open source contributions (optional but great)

### Interview Readiness
- [ ] 20+ mock interviews completed
- [ ] STAR stories prepared for behavioral questions
- [ ] Company-specific problem sets practiced
- [ ] Can explain every project in detail without notes

### Professional Presence
- [ ] LinkedIn optimized and active
- [ ] Resume tailored for backend roles
- [ ] Network of 500+ professionals
- [ ] Referrals from 5+ people

---

> **Remember:** This is ONE document. Everything you need is here. No switching files, no confusion. Backend and DSA grow together. Every backend feature you build, think "what DSA concept powers this?" Every DSA problem you solve, think "where would I use this in a real system?"

**Start tomorrow. Week 1, Day 1. No excuses.**

---

**Last Updated:** June 2026
**Maintained By:** Gulshan Kushwaha
**Next Review:** Monthly

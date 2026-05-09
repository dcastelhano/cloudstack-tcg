# CloudStack TCG — Code Cards Expansion

## Integration Philosophy

Programming concepts aren't a separate domain — they're **the foundation** that runs ON cloud infrastructure. Code cards represent the software that deploys to Services.

## New Card Type: Code

**Code cards** are deployable software artifacts that attach to Services for bonuses.

```
┌─────────────────────┐
│ [1🖥️] Python Lambda │
│ 💻 Code             │
│                     │
│ Attach to a         │
│ Serverless service. │
│ +1 attack.          │
│                     │
│ "def handler..."    │
└─────────────────────┘
```

## Code Subtypes

### By Paradigm
- **OOP** — Classes, Objects, Inheritance
- **Functional** — Pure functions, Immutability, Composition
- **Procedural** — Scripts, Sequential logic
- **Reactive** — Streams, Events, Observers

### By Language Family
- **Python** — Data science, scripting, Lambda
- **JavaScript/TypeScript** — Web, Node.js, serverless
- **Java/Kotlin** — Enterprise, Android, Spring
- **Go** — Cloud-native, Kubernetes, CLI tools
- **Rust** — Systems, performance-critical, WebAssembly

## Code Cards

### OOP Concepts

| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Class Definition | 1🖥️ | Base for Methods. +1 health to attached Service. | Method, Constructor |
| Method | 0 | Attach to Class. +1 attack. | Class, Return |
| Constructor | 1🖥️ | Attach to Class. When played, draw a card. | Class, Object |
| Object Instance | 1🖥️ | Copy of a Class you control. Gains its bonuses. | Class |
| Interface | 2🖥️ | Services with Interface share damage. | Implementation |
| Implementation | 1🖥️ | Attach to Interface. Service gains +2 health. | Interface |
| Inheritance | 2🖥️🖥️ | Copy all attachments from one Service to another. | Class, Object |
| Polymorphism | 3🖥️🖥️ | Your Methods can attach to any Service type. | Interface, Class |

### Functional Concepts

| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Pure Function | 1🖥️ | Can't be modified. +2 attack. | Return, Composition |
| Return Value | 0 | Attach to Function. Draw a card when it attacks. | Function |
| Map | 1💾 | Apply effect to all your Services. | Array, Function |
| Filter | 1💾 | Choose which Services are targeted. | Array, Predicate |
| Reduce | 2💾 | Combine all Service attacks into one. | Array, Accumulator |
| Composition | 2🖥️ | Chain two Functions. Both effects trigger. | Function, Function |
| Immutable State | 2💾 | Service can't lose health this turn. | Pure Function |
| Higher-Order Function | 3🖥️🖥️ | Function that creates Functions. Draw 2 cards. | Function |

### Async/Concurrent Concepts

| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Promise | 1🖥️ | Effect resolves next turn. Draw 2 cards then. | Then, Await |
| Async/Await | 2🖥️ | Service can attack twice (non-blocking). | Promise |
| Callback | 1🖥️ | When this Service is destroyed, trigger effect. | Event |
| Event Listener | 1🌐 | React to opponent's actions. Counter-attack. | Event, Handler |
| Event Emitter | 1🌐 | Trigger all your Event Listeners. | Event Listener |
| Thread | 2🖥️ | Service acts independently. Extra attack phase. | Process |
| Mutex | 1🛡️ | Only one Service can be targeted per turn. | Thread, Lock |
| Message Queue | 2🌐 | Store attacks. Release all at once. | SQS, Event |

### Data Structure Concepts

| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Array | 1💾 | Hold up to 3 Code cards. | Loop, Index |
| Object/Dict | 1💾 | Key-value store. Search for specific cards. | Key, Value |
| Loop | 1🖥️ | Repeat an effect for each item in Array. | Array, Iterator |
| Index | 0 | Access specific item in Array instantly. | Array |
| Stack | 1💾 | LIFO. Last card played triggers first. | Push, Pop |
| Queue | 1💾 | FIFO. First card played triggers first. | Enqueue, Dequeue |
| Tree | 2💾 | Hierarchical effects. Bonuses cascade down. | Node, Root |
| Graph | 3💾💾 | All Services connect. Shared synergies. | Node, Edge |

### Error Handling

| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Try Block | 1🖥️ | Protect Service from next Incident. | Catch |
| Catch Block | 1🖥️ | When Try triggers, draw a card. | Try, Error |
| Throw | 1🖥️ | Deal 2 damage to opponent's Service. | Error, Exception |
| Finally | 1🖥️ | Always triggers, even if Service destroyed. | Try, Cleanup |
| Error | 0 | Incident. Destroy target Service without Try. | Throw, Catch |
| Exception Handler | 2🛡️ | All your Services have implicit Try. | Try, Catch |
| Retry Logic | 2🛡️ | Failed attacks retry once. | Try, Loop |
| Circuit Breaker | 3🛡️ | If Service fails 3x, disable it safely. | Retry, Fallback |

### Language-Specific Cards

#### Python Pack
| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Decorator | 1🖥️ | Wrap a Function. Add +1/+1. | Function |
| List Comprehension | 2💾 | Create Array with Filter built-in. | Array, Filter |
| Generator | 2🖥️ | Lazy evaluation. Draw cards as needed. | Iterator, Yield |
| Lambda Expression | 0 | Instant mini-function. +1 attack this turn. | Lambda (service) |
| Pandas DataFrame | 3💾💾 | Massive data processing. +3 attack vs Data services. | Data Lake |
| NumPy Array | 2💾🧠 | Optimized. +2 attack to ML services. | SageMaker |

#### JavaScript Pack
| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Closure | 2🖥️ | Function remembers scope. Persist effect. | Function, Scope |
| Prototype | 2🖥️ | All Objects gain this ability. | Object, Inheritance |
| Event Loop | 2🖥️ | Non-blocking. Service can't be frozen. | Async, Node.js |
| npm Package | 1🖥️ | Search deck for any Code card. | Node.js |
| React Component | 2🖥️🌐 | UI service. +2 health when attached to CloudFront. | CloudFront, S3 |
| Express Route | 1🌐 | API endpoint. Synergizes with API Gateway. | API Gateway |

#### Java Pack
| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Spring Bean | 2🖥️ | Managed instance. Auto-heals 1 per turn. | EC2, ECS |
| JVM | 3🖥️🖥️ | Platform. All Java cards cost -1. | Java cards |
| Annotation | 0 | Modify any card's behavior. | Class, Method |
| Maven Dependency | 1🖥️ | Import external code. Draw a card. | Build |
| Garbage Collection | 2🖥️ | Destroy all 0-health Services. Draw per destroyed. | JVM |

#### Go Pack
| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Goroutine | 1🖥️ | Lightweight thread. +1 attack per Goroutine. | Channel |
| Channel | 1🌐 | Communication. Goroutines share effects. | Goroutine |
| Go Binary | 2🖥️ | Single deployable. +2 attack to Fargate/Lambda. | Fargate, Lambda |
| Defer | 1🖥️ | Cleanup runs at end of turn. | Function |
| Interface (Go) | 1🖥️ | Implicit implementation. Any Service qualifies. | Duck Typing |

#### Rust Pack
| Card | Cost | Effect | Synergies |
|------|------|--------|-----------|
| Ownership | 2🛡️ | This Service can't be copied or stolen. | Borrowing |
| Borrowing | 1🛡️ | Temporarily use another Service's effect. | Ownership |
| Lifetime | 2🛡️ | Service exists for exactly N turns. Choose N. | Ownership |
| Unsafe Block | 3🖥️🛡️ | Bypass rules. +4 attack but vulnerable. | Raw Pointer |
| Cargo Build | 2🖥️ | Compile. All Rust cards gain +1/+1. | Rust cards |
| Result Type | 1🛡️ | Built-in error handling. Try+Catch combined. | Error |

## Code → Cloud Synergies

The magic: Code cards synergize with Cloud services!

| Code Card | Cloud Service | Synergy Name | Bonus |
|-----------|---------------|--------------|-------|
| Python Lambda | Lambda | "Native Runtime" | +2 attack |
| Node.js | Lambda | "JS Runtime" | +1 attack, draw card |
| Pandas DataFrame | Redshift | "Analytics Pipeline" | +3 attack |
| React Component | CloudFront | "Static SPA" | Can't be targeted |
| Express Route | API Gateway | "REST API" | +2 health |
| Go Binary | Fargate | "Cloud-Native" | +2 attack |
| Spring Bean | ECS | "Container Deploy" | Auto-heal 2 |
| JVM | EC2 | "Full Control" | +1/+1 |
| Docker Image | ECS/EKS | "Containerized" | Deploy to either |
| Goroutine | Lambda | "Concurrent Handler" | Attack twice |

## Educational Content Examples

### Class Definition
```yaml
back:
  concept: "Class"
  paradigm: "Object-Oriented Programming"
  what: "Blueprint for creating objects. Defines properties and methods."
  languages: ["Java", "Python", "TypeScript", "C#", "C++"]
  learn:
    why: "Encapsulation - bundle data and behavior together"
    example: |
      class User:
          def __init__(self, name):
              self.name = name
          def greet(self):
              return f"Hello, {self.name}"
  synergies:
    - concept: "Method"
      why: "Classes contain methods - behaviors that objects can perform"
    - concept: "Constructor"  
      why: "Special method that initializes new objects"
    - concept: "Inheritance"
      why: "Classes can extend other classes to reuse code"
  certification: "Any programming certification"
  docs: "https://docs.python.org/3/tutorial/classes.html"
```

### Promise
```yaml
back:
  concept: "Promise"
  paradigm: "Asynchronous Programming"
  what: "Object representing eventual completion of an async operation"
  languages: ["JavaScript", "TypeScript"]
  learn:
    why: "Handle async operations without callback hell"
    states: ["Pending", "Fulfilled", "Rejected"]
    example: |
      fetch('/api/data')
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(error => console.error(error))
  synergies:
    - concept: "Async/Await"
      why: "Syntactic sugar that makes Promises look synchronous"
    - concept: "Then"
      why: "Chain operations after Promise resolves"
    - concept: "Catch"
      why: "Handle errors in Promise chain"
  cloud_connection: "Lambda async invocations return Promises"
  docs: "https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise"
```

## Deck Building: Code + Cloud

### "Serverless Python" Deck
- 4x Lambda Function
- 4x Python Lambda (code)
- 4x Pandas DataFrame
- 4x API Gateway
- 4x DynamoDB
- 4x Decorator
- 4x List Comprehension
- + Infrastructure + Incidents

### "Enterprise Java" Deck
- 4x EC2 Instance
- 4x ECS Container
- 4x Spring Bean
- 4x JVM
- 4x RDS PostgreSQL
- 4x Maven Dependency
- 4x Class Definition
- + Infrastructure + Incidents

### "Cloud-Native Go" Deck
- 4x Fargate Task
- 4x EKS Cluster
- 4x Go Binary
- 4x Goroutine
- 4x Channel
- 4x Lambda Function
- + Infrastructure + Incidents

## Learning Outcomes

By playing CloudStack with Code cards, players learn:

1. **Language Paradigms** — OOP vs Functional vs Reactive
2. **Code-to-Cloud Mapping** — Which code runs where
3. **Design Patterns** — Why patterns exist and when to use them
4. **Error Handling** — Resilient code practices
5. **Async Programming** — Non-blocking operations
6. **Data Structures** — When to use arrays vs maps vs trees
7. **Language Trade-offs** — Why choose Python vs Go vs Java

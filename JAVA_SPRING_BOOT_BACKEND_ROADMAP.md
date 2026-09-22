# Java and Spring Boot Backend Roadmap

This document is a practical roadmap for learning Java, advanced Java, Spring Boot, and core backend engineering. It is written as a study guide, interview guide, project guide, and implementation guide.

It is intentionally structured in layers:

1. Learn the language.
2. Learn the runtime and JVM.
3. Learn core backend engineering.
4. Learn Spring Boot and ecosystem tooling.
5. Build projects.
6. Prepare for production systems.

If you are studying for industry work, do not treat this as only theory. Every topic here should be practiced with code.

---

## Table of Contents

1. Java Roadmap
2. Advanced Java Roadmap
3. Core Backend Engineering Roadmap
4. Spring Boot Roadmap
5. Spring Boot Advanced Roadmap
6. Resume-Worthy Backend Projects
7. Implementation Walkthroughs
8. Production Readiness Checklist
9. Interview Preparation Map
10. Suggested Learning Sequence
11. Deep Dive: Java Language and JVM Internals
12. Deep Dive: Spring Framework and Spring Boot Internals
13. Full Project: Expense Tracker (Complete Working Code)
14. Full Project: E-Commerce Order, Inventory and Payment Flow (Complete Working Code)
15. Full Project: URL Shortener with Redis Rate Limiting (Complete Working Code)
16. Interview Question Bank with Model Answers

---

## 1. Java Roadmap

### 1.1 What Java Is

Java is a general-purpose, object-oriented, class-based language designed to run on the JVM. It is strongly typed, garbage collected, portable, and heavily used in enterprise systems, financial systems, distributed systems, backend APIs, batch jobs, and cloud services.

Java is valuable in industry because it offers:

- Strong tooling.
- Large ecosystem.
- Stable runtime behavior.
- Mature concurrency primitives.
- Excellent IDE support.
- Massive enterprise adoption.

### 1.2 Java Versions You Should Know

You should know the purpose and industry relevance of major Java releases:

- Java 8: lambdas, streams, optional, new date/time API.
- Java 11: long-term support, improved APIs.
- Java 17: modern LTS baseline for many enterprises.
- Java 21: modern LTS with virtual threads and newer language features.

If you are learning for jobs, Java 17 and Java 21 are the most important versions to focus on.

### 1.3 Core Syntax

Java basics include:

- Variables and types.
- Operators.
- Conditionals.
- Loops.
- Methods.
- Arrays.
- Strings.
- Classes and objects.
- Packages and imports.

Example:

```java
public class HelloJava {
    public static void main(String[] args) {
        String name = "Java";
        int year = 2026;
        System.out.println("Learning " + name + " in " + year);
    }
}
```

### 1.4 Data Types

Primitive types:

- byte
- short
- int
- long
- float
- double
- char
- boolean

Reference types:

- String
- Arrays
- Collections
- Custom classes

Key concepts:

- Primitive types store values directly.
- Reference types store object references.
- Java is pass-by-value, including object references.

### 1.5 Operators

Important operator categories:

- Arithmetic.
- Relational.
- Logical.
- Bitwise.
- Assignment.
- Ternary.
- Increment and decrement.

Backend developers should especially understand:

- Short-circuit logic.
- Equality vs identity.
- Integer overflow.
- Bitwise operations for low-level work.

### 1.6 Control Flow

You should know:

- if / else.
- switch.
- while.
- do-while.
- for.
- enhanced for.
- break and continue.

Example:

```java
public class ControlFlowExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                continue;
            }
            System.out.println(i);
        }
    }
}
```

### 1.7 Methods

Methods are the unit of behavior.

Learn:

- Parameters and return values.
- Method overloading.
- Static methods.
- Recursive methods.
- Varargs.

Example:

```java
public class MathUtil {
    public static int add(int a, int b) {
        return a + b;
    }

    public static int add(int... numbers) {
        int sum = 0;
        for (int number : numbers) {
            sum += number;
        }
        return sum;
    }
}
```

### 1.8 Strings

You must understand:

- String immutability.
- String pool.
- StringBuilder.
- StringBuffer.
- equals() vs ==.

Example:

```java
String a = new String("java");
String b = "java";
boolean sameValue = a.equals(b);
boolean sameReference = a == b;
```

### 1.9 Arrays

Arrays are fixed-size containers.

Learn:

- One-dimensional arrays.
- Multi-dimensional arrays.
- Sorting.
- Searching.
- Copying arrays.

Example:

```java
int[] values = {3, 1, 4, 1, 5};
for (int value : values) {
    System.out.println(value);
}
```

### 1.10 Object-Oriented Programming

Java is built on OOP.

You should know:

- Class.
- Object.
- Encapsulation.
- Abstraction.
- Inheritance.
- Polymorphism.
- Composition.

Example:

```java
class User {
    private final String username;

    User(String username) {
        this.username = username;
    }

    public String getUsername() {
        return username;
    }
}
```

### 1.11 Constructors

Learn:

- Default constructor.
- Parameterized constructor.
- Constructor chaining.
- Private constructors.

### 1.12 Access Modifiers

Learn:

- public.
- private.
- protected.
- package-private.

### 1.13 Packages

Packages help organize code and control visibility.

### 1.14 Object Class

Know and override:

- equals()
- hashCode()
- toString()
- clone() only when necessary

### 1.15 Exception Handling

Backend code must handle exceptions well.

Learn:

- try / catch / finally.
- checked vs unchecked exceptions.
- custom exceptions.
- exception propagation.
- best practices for error messages.

Example:

```java
public class InvalidOrderException extends RuntimeException {
    public InvalidOrderException(String message) {
        super(message);
    }
}
```

### 1.16 Collections Framework

The collections framework is one of the most important parts of Java.

You should know:

- List.
- Set.
- Map.
- Queue.
- Deque.
- Iterator.
- Comparable.
- Comparator.

Collection choices:

- ArrayList for indexed access.
- LinkedList for frequent insertions/removals.
- HashSet for uniqueness.
- TreeSet for sorted uniqueness.
- HashMap for key-value lookup.
- TreeMap for sorted key-value lookup.

### 1.17 Generics

Generics allow type-safe reusable code.

Learn:

- Generic classes.
- Generic methods.
- Bounded types.
- Wildcards.

Example:

```java
public class Box<T> {
    private T value;

    public void setValue(T value) {
        this.value = value;
    }

    public T getValue() {
        return value;
    }
}
```

### 1.18 Input and Output

Learn:

- File handling.
- Buffered streams.
- NIO and NIO.2.
- Serialization basics.
- Deserialization risks.

### 1.19 Lambda Expressions

Lambda expressions make Java more functional.

Example:

```java
List<String> names = List.of("a", "b", "c");
names.forEach(System.out::println);
```

### 1.20 Streams API

Learn:

- map
- filter
- flatMap
- reduce
- collect
- groupingBy
- partitioningBy

Example:

```java
List<Integer> numbers = List.of(1, 2, 3, 4, 5);
List<Integer> evenSquares = numbers.stream()
        .filter(n -> n % 2 == 0)
        .map(n -> n * n)
        .toList();
```

### 1.21 Date and Time API

Use java.time:

- LocalDate.
- LocalTime.
- LocalDateTime.
- ZonedDateTime.
- Instant.
- Duration.
- Period.

### 1.22 Immutable Objects

Learn how to build immutable classes because they improve safety and thread compatibility.

### 1.23 Java Memory Model Basics

Understand:

- Stack vs heap.
- Object references.
- Garbage collection.
- Reachability.
- Finalization history and why not to rely on it.

### 1.24 JVM Basics

The JVM executes bytecode and manages memory, JIT compilation, class loading, and runtime optimization.

You should know:

- Bytecode.
- ClassLoader.
- JIT compiler.
- Garbage collector.
- HotSpot JVM.

---

## 2. Advanced Java Roadmap

### 2.1 Multithreading and Concurrency

This is one of the most important advanced topics for backend developers.

Learn:

- Thread.
- Runnable.
- Callable.
- ExecutorService.
- Future.
- CompletableFuture.
- synchronized.
- volatile.
- Lock.
- ReadWriteLock.
- Atomic classes.
- Concurrent collections.

### 2.2 Race Conditions and Deadlocks

You should understand:

- Race condition.
- Deadlock.
- Livelock.
- Starvation.
- Thread safety.

### 2.3 Java Concurrency Utilities

Useful tools:

- CountDownLatch.
- CyclicBarrier.
- Semaphore.
- Phaser.
- BlockingQueue.

### 2.4 CompletableFuture

Useful for async composition.

Example:

```java
CompletableFuture.supplyAsync(() -> "data")
        .thenApply(String::toUpperCase)
        .thenAccept(System.out::println);
```

### 2.5 Virtual Threads

Modern Java supports virtual threads for highly scalable concurrency. Learn where they help and where they do not.

### 2.6 Reflection

Reflection is used by frameworks like Spring, Hibernate, Jackson, Mockito, and many others.

Learn:

- Class metadata inspection.
- Constructor and method invocation.
- Field access.
- Reflection costs and risks.

### 2.7 Annotations

Learn:

- Built-in annotations.
- Custom annotations.
- Annotation processing basics.

### 2.8 Java Modules

Understand the module system conceptually, even if many enterprise codebases still use classpath-based builds.

### 2.9 Serialization

Learn:

- Java serialization.
- Why native serialization is usually avoided in modern systems.
- Safer alternatives such as JSON and protobuf.

### 2.10 Garbage Collection

Know the basics of:

- Young generation.
- Old generation.
- GC pauses.
- Throughput vs latency.
- G1 GC.
- ZGC.

### 2.11 Performance Tuning

Learn to analyze:

- CPU usage.
- Memory usage.
- GC pressure.
- Allocation rate.
- Lock contention.

### 2.12 JVM Diagnostics

Useful tools:

- jstack.
- jmap.
- jcmd.
- jstat.
- JFR.
- VisualVM.

### 2.13 Design Patterns

Core patterns to know:

- Singleton.
- Factory.
- Builder.
- Strategy.
- Observer.
- Adapter.
- Decorator.
- Proxy.
- Template Method.
- Command.
- Chain of Responsibility.

### 2.14 SOLID Principles

You should be able to explain and apply:

- Single Responsibility Principle.
- Open Closed Principle.
- Liskov Substitution Principle.
- Interface Segregation Principle.
- Dependency Inversion Principle.

### 2.15 Clean Code Practices

Backend code should be:

- Readable.
- Predictable.
- Small and focused.
- Properly named.
- Easy to test.

### 2.16 Testing in Java

Learn:

- Unit testing with JUnit.
- Assertions.
- Parameterized tests.
- Mockito.
- Integration tests.
- Testcontainers.

Example:

```java
import static org.junit.jupiter.api.Assertions.assertEquals;

import org.junit.jupiter.api.Test;

class MathUtilTest {
    @Test
    void addsNumbers() {
        assertEquals(5, MathUtil.add(2, 3));
    }
}
```

### 2.17 Build Tools

Learn:

- Maven.
- Gradle.
- Dependency management.
- Multi-module builds.
- Build profiles.

### 2.18 Logging

Learn:

- SLF4J.
- Logback.
- Structured logging.
- Log levels.
- Correlation IDs.

### 2.19 Security Basics

Learn:

- Input validation.
- Output encoding.
- Authentication.
- Authorization.
- Secrets handling.
- Secure password storage.
- Avoiding injection vulnerabilities.

### 2.20 Networking Basics for Backend Engineers

Know:

- TCP vs UDP.
- HTTP methods.
- HTTP status codes.
- REST basics.
- Cookies and headers.
- TLS.

### 2.21 API Design

Learn to design APIs that are:

- Resource-oriented.
- Versioned.
- Consistent.
- Well-documented.
- Secure.

### 2.22 Data Structures and Algorithms

Backend interviews still expect this.

You should know:

- Arrays.
- Linked lists.
- Stacks.
- Queues.
- Trees.
- Hash tables.
- Graphs.
- Sorting.
- Searching.
- Recursion.
- Dynamic programming basics.

---

## 3. Core Backend Engineering Roadmap

### 3.1 What Backend Engineering Means

Backend engineering is about building reliable server-side systems that store data, process business rules, expose APIs, integrate with other systems, and remain secure, observable, and scalable.

### 3.2 Core Responsibilities

Backend developers typically handle:

- API design.
- Database modeling.
- Authentication and authorization.
- Business logic.
- Integrations.
- Performance tuning.
- Error handling.
- Observability.

### 3.3 HTTP and REST

Learn:

- Request and response structure.
- Headers.
- Query parameters.
- Path variables.
- Payload formats.
- Idempotency.
- Caching.

### 3.4 Status Codes

Important codes:

- 200 OK.
- 201 Created.
- 204 No Content.
- 400 Bad Request.
- 401 Unauthorized.
- 403 Forbidden.
- 404 Not Found.
- 409 Conflict.
- 422 Unprocessable Entity.
- 500 Internal Server Error.

### 3.5 Database Fundamentals

Learn:

- Relational databases.
- Normalization.
- Primary keys.
- Foreign keys.
- Indexes.
- Joins.
- Transactions.
- Isolation levels.

### 3.6 SQL

You should know:

- SELECT.
- INSERT.
- UPDATE.
- DELETE.
- JOIN.
- GROUP BY.
- HAVING.
- Window functions.
- Subqueries.

### 3.7 NoSQL

Know when to use:

- Document stores.
- Key-value stores.
- Wide-column stores.
- Graph databases.

### 3.8 Caching

Learn:

- In-memory caching.
- Cache invalidation.
- TTLs.
- Distributed cache.
- Redis basics.

### 3.9 Messaging and Async Processing

Learn:

- Queues.
- Pub/sub.
- Kafka basics.
- RabbitMQ basics.
- Event-driven architecture.
- Dead letter queues.

### 3.10 Distributed Systems Basics

Important topics:

- Consistency.
- Availability.
- Partition tolerance.
- Latency.
- Retry.
- Circuit breaker.
- Bulkhead.
- Backpressure.

### 3.11 Scalability

Learn:

- Horizontal scaling.
- Vertical scaling.
- Stateless services.
- Load balancing.
- Sharding.
- Replication.

### 3.12 Reliability

Learn:

- Timeouts.
- Retries.
- Idempotency keys.
- Fallbacks.
- Rate limiting.
- Graceful degradation.

### 3.13 Observability

Learn:

- Logs.
- Metrics.
- Traces.
- Correlation IDs.
- Health checks.

### 3.14 Security

Learn:

- Authentication.
- Authorization.
- JWT.
- OAuth2.
- CSRF.
- CORS.
- Secret management.
- OWASP Top 10.

### 3.15 DevOps Awareness

Backend developers should understand:

- Docker.
- CI/CD.
- Environment variables.
- Config management.
- Deployment strategies.

---

## 4. Spring Boot Roadmap

### 4.1 What Spring Boot Is

Spring Boot is a framework that simplifies Spring application development by offering auto-configuration, starters, embedded servers, opinionated defaults, and production-grade features.

### 4.2 Why Industry Uses It

Spring Boot is used because it provides:

- Fast development.
- Large ecosystem.
- Dependency injection.
- Strong integration support.
- Production readiness.

### 4.3 Core Spring Concepts

Learn:

- IoC.
- DI.
- Bean lifecycle.
- Application context.
- Bean scopes.
- Configuration classes.

### 4.4 Spring Boot Starters

Common starters:

- spring-boot-starter-web
- spring-boot-starter-webflux
- spring-boot-starter-data-jpa
- spring-boot-starter-security
- spring-boot-starter-validation
- spring-boot-starter-test

### 4.5 REST Controllers

Example:

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UserController {

    @GetMapping("/users/{id}")
    public String getUser(@PathVariable Long id) {
        return "User " + id;
    }
}
```

### 4.6 Service Layer

Keep business logic out of controllers.

Example:

```java
import org.springframework.stereotype.Service;

@Service
public class OrderService {

    public String placeOrder(String productName) {
        return "Order placed for " + productName;
    }
}
```

### 4.7 Repository Layer

Learn Spring Data JPA repositories and derived query methods.

### 4.8 Dependency Injection

Prefer constructor injection.

### 4.9 Configuration

Learn:

- application.properties.
- application.yml.
- @ConfigurationProperties.
- Profiles.

### 4.10 Validation

Learn:

- Bean Validation.
- @Valid.
- @NotNull.
- @NotBlank.
- Custom validators.

### 4.11 Exception Handling in Spring Boot

Learn:

- @ControllerAdvice.
- @ExceptionHandler.
- Error response design.

### 4.12 Spring Data JPA

Learn:

- Entity mappings.
- Relationships.
- Fetch types.
- JPQL.
- Native queries.
- Pagination.
- Auditing.

### 4.13 Transactions

Learn:

- @Transactional.
- Rollback behavior.
- Propagation.
- Isolation.

### 4.14 Security

Learn Spring Security basics:

- Security filter chain.
- Authentication providers.
- Password encoding.
- Method security.
- JWT.
- OAuth2 login.

### 4.15 Spring Boot Actuator

Learn:

- health.
- metrics.
- info.
- readiness and liveness.

### 4.16 Testing Spring Boot

Learn:

- @SpringBootTest.
- @WebMvcTest.
- @DataJpaTest.
- MockMvc.
- WebTestClient.
- Testcontainers.

### 4.17 Spring Boot with WebFlux

If the project is reactive, learn:

- Mono.
- Flux.
- Reactive repositories.
- WebClient.
- backpressure.

### 4.18 Spring Boot with Messaging

Learn how to integrate with:

- Kafka.
- RabbitMQ.
- JMS.

### 4.19 Spring Boot Production Concerns

Learn:

- graceful shutdown.
- config separation.
- secrets.
- logging.
- tracing.
- metrics.
- connection pooling.

---

## 5. Spring Boot Advanced Roadmap

### 5.1 Auto-Configuration Internals

Understand why starter dependencies change behavior automatically.

### 5.2 Bean Scanning and Lifecycle

Know how beans are detected, created, initialized, proxied, and destroyed.

### 5.3 AOP

Learn:

- Aspects.
- Advice.
- Pointcuts.
- Proxies.

### 5.4 Reactive Programming

Learn when reactive helps and when it adds complexity.

### 5.5 Distributed Tracing

Learn integration with OpenTelemetry and tracing systems.

### 5.6 Resilience Patterns

Learn libraries and patterns for:

- circuit breakers.
- retries.
- rate limiting.
- bulkheads.

### 5.7 Multi-Service Architecture

Learn:

- service boundaries.
- contract design.
- service discovery.
- API gateway.
- centralized auth.

### 5.8 Security Architecture

Learn how to secure:

- public APIs.
- internal service-to-service calls.
- admin endpoints.
- file downloads.

### 5.9 Common Spring Boot Mistakes

Avoid:

- putting business logic in controllers.
- using entities directly in API responses without care.
- ignoring lazy-loading issues.
- blocking reactive chains.
- overusing global state.

---

## 6. Resume-Worthy Backend Projects

These are project ideas that look credible on a resume if built well.

### 6.1 E-Commerce Backend

Features:

- user accounts.
- product catalog.
- search and filtering.
- cart.
- checkout.
- payment integration.
- order tracking.

Tech stack:

- Java.
- Spring Boot.
- PostgreSQL.
- Redis.
- JWT.
- Docker.

### 6.2 Expense Tracker API

Features:

- income and expense records.
- category budgets.
- monthly reports.
- recurring expenses.
- export to CSV.

### 6.3 Job Portal Backend

Features:

- employer profiles.
- candidate profiles.
- job posting.
- job search.
- application tracking.
- resume upload.

### 6.4 Online Learning Platform Backend

Features:

- courses.
- modules.
- enrollment.
- quizzes.
- progress tracking.
- certificate generation.

### 6.5 Food Delivery Backend

Features:

- restaurant management.
- menu management.
- cart and checkout.
- delivery tracking.
- order status updates.

### 6.6 Appointment Booking System

Features:

- time slots.
- booking rules.
- cancellation.
- reminders.
- calendar sync.

### 6.7 Ticketing System

Features:

- ticket creation.
- assignment.
- priority.
- SLA tracking.
- comments.
- notifications.

### 6.8 Banking-Like Ledger System

Features:

- accounts.
- transactions.
- double-entry principles.
- balance consistency.
- audit history.

### 6.9 URL Shortener

Features:

- short code generation.
- redirect service.
- analytics.
- rate limiting.

### 6.10 Notification Platform

Features:

- email.
- SMS.
- push events.
- templates.
- delivery retries.

### 6.11 File Storage Service

Features:

- uploads.
- metadata.
- access control.
- pre-signed links.

### 6.12 Microservices Retail Platform

Features:

- auth service.
- catalog service.
- order service.
- payment service.
- notification service.
- gateway.

This is one of the strongest resume projects if done with good architecture and observability.

---

## 7. Implementation Walkthroughs

Below are practical blueprints for how to implement some projects.

### 7.1 Project Blueprint: Expense Tracker API

#### Requirements

- Users can create accounts.
- Users can add income and expenses.
- Users can see monthly summaries.
- Users can filter by category and date.

#### Database Tables

- users
- transactions
- categories

#### Suggested API Endpoints

- POST /api/users
- POST /api/transactions
- GET /api/transactions
- GET /api/reports/monthly

#### Core Code Sketch

Entity:

```java
import jakarta.persistence.*;
import java.math.BigDecimal;
import java.time.LocalDate;

@Entity
public class TransactionRecord {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String description;
    private BigDecimal amount;
    private LocalDate transactionDate;
    private String category;

    protected TransactionRecord() {
    }

    public TransactionRecord(String description, BigDecimal amount, LocalDate transactionDate, String category) {
        this.description = description;
        this.amount = amount;
        this.transactionDate = transactionDate;
        this.category = category;
    }
}
```

Service:

```java
import org.springframework.stereotype.Service;

@Service
public class TransactionService {

    public String summarizeMonth() {
        return "Monthly summary";
    }
}
```

#### What Makes It Resume-Worthy

- Validation.
- Filtering.
- Reporting.
- Pagination.
- Clean architecture.

### 7.2 Project Blueprint: E-Commerce Backend

#### Core Flow

1. User signs in.
2. User browses products.
3. User adds items to cart.
4. User checks out.
5. Order is created.
6. Payment is processed.
7. Inventory is updated.

#### Services

- auth-service
- product-service
- cart-service
- order-service
- payment-service
- notification-service

#### Important Backend Concerns

- Idempotent checkout.
- Inventory reservation.
- Payment retry safety.
- Order state machine.

### 7.3 Project Blueprint: Job Portal Backend

#### Key Entities

- User
- EmployerProfile
- CandidateProfile
- JobPost
- Application

#### Feature Set

- Search jobs.
- Apply to jobs.
- Track application status.
- Upload resume.
- Employer dashboard.

### 7.4 Project Blueprint: Banking-Like Ledger

This is a strong advanced project.

#### Goals

- Ensure balance consistency.
- Track every mutation.
- Support auditability.

#### Important Rules

- Never update balances without transaction safety.
- Store every transfer as immutable ledger entries.
- Use database transactions.

### 7.5 Project Blueprint: Notification System

#### Features

- Event ingestion.
- Template processing.
- Multi-channel delivery.
- Retry queue.
- Status tracking.

#### Architecture

- API receives event.
- Event written to queue.
- Worker consumes event.
- Notification provider sends message.
- Result stored.

---

## 8. Production Readiness Checklist

If you want real backend credibility, your project should include:

- Authentication.
- Authorization.
- Validation.
- Logging.
- Error handling.
- Pagination.
- Sorting.
- Filtering.
- Unit tests.
- Integration tests.
- Database migrations.
- Docker support.
- Health endpoints.
- Metrics.
- Clear README.
- API documentation.

---

## 9. Interview Preparation Map

### 9.1 Java Questions You Must Answer

- What is the difference between == and equals()?
- Why are Strings immutable?
- What is the difference between HashMap and ConcurrentHashMap?
- What is the difference between ArrayList and LinkedList?
- What is the difference between checked and unchecked exceptions?
- What is the JVM?
- What are streams?
- What are lambda expressions?

### 9.2 Spring Boot Questions You Must Answer

- What is dependency injection?
- What is auto-configuration?
- How does Spring Security work?
- What is the difference between @Component, @Service, and @Repository?
- What is the difference between @RestController and @Controller?
- How do you handle exceptions globally?
- What is @Transactional?

### 9.3 Backend Questions You Must Answer

- How do you design a REST API?
- How do you secure APIs?
- How do you scale a backend?
- How do you design for retries and idempotency?
- How do you avoid race conditions?
- How do you monitor a production service?

---

## 10. Suggested Learning Sequence

### Phase 1: Java Fundamentals

Start with syntax, types, loops, methods, classes, and collections.

### Phase 2: Java Core + OOP

Move into OOP, exceptions, generics, and basic I/O.

### Phase 3: Advanced Java

Study concurrency, JVM internals, streams, reflection, and performance basics.

### Phase 4: Backend Fundamentals

Learn HTTP, REST, SQL, database design, and API development.

### Phase 5: Spring Boot

Learn controllers, services, repositories, validation, security, testing, and configuration.

### Phase 6: Production Systems

Add caching, messaging, observability, Docker, CI/CD, and cloud deployment.

### Phase 7: Projects

Build 3 to 5 serious projects with documentation, tests, and deployment.

---

## Final Advice

If your goal is a backend role, do not only memorize Java and Spring Boot. Build:

- One CRUD-heavy project.
- One authentication project.
- One asynchronous or event-driven project.
- One system with complex business rules.
- One project with production readiness.

That combination gives you much better resume value than many small toy apps.

---

## Code Starter: Complete Minimal Spring Boot API

This is a small working starting point for a Spring Boot backend.

```java
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
public class DemoApplication {
    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}

@RestController
class HealthController {
    @GetMapping("/health")
    public String health() {
        return "OK";
    }
}
```

## Code Starter: Simple Service Layer

```java
package com.example.demo.service;

import org.springframework.stereotype.Service;

@Service
public class GreetingService {

    public String greet(String name) {
        if (name == null || name.isBlank()) {
            return "Hello, Guest";
        }
        return "Hello, " + name;
    }
}
```

## Code Starter: Controller Using Service

```java
package com.example.demo.controller;

import com.example.demo.service.GreetingService;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class GreetingController {

    private final GreetingService greetingService;

    public GreetingController(GreetingService greetingService) {
        this.greetingService = greetingService;
    }

    @GetMapping("/greet")
    public String greet(@RequestParam(required = false) String name) {
        return greetingService.greet(name);
    }
}
```

---

This file is a roadmap foundation. It can be expanded into a much larger handbook with dedicated sections for each subtopic, project, and framework module.

---

## 11. Deep Dive: Java Language and JVM Internals

This section goes beyond the basics and explains what actually happens under the hood. Interviewers at mid and senior level expect this depth.

### 11.1 JVM Architecture

The JVM is made of three major subsystems:

- **Class Loader Subsystem**: loads, links, and initializes classes.
- **Runtime Data Areas**: method area, heap, stack, PC registers, native method stack.
- **Execution Engine**: interpreter, JIT compiler, garbage collector.

Class loading happens in three phases:

1. **Loading** — reads the `.class` file bytes and creates a `Class` object.
2. **Linking** — split into verification (bytecode safety check), preparation (default values for static fields), and resolution (symbolic references resolved to direct references).
3. **Initialization** — static initializers and static field assignments run, in the order they appear in source.

Class loader delegation model (parent-first):

```
Bootstrap ClassLoader   → loads java.base and core JDK classes
        │
Platform ClassLoader    → loads JDK platform modules
        │
Application ClassLoader → loads your application classes and dependencies
```

A class loader always asks its parent to load a class first. Only if the parent fails does the child attempt to load it. This is why you cannot easily shadow `java.lang.String` — the bootstrap loader will always win.

### 11.2 Runtime Data Areas in Detail

- **Method Area (Metaspace since Java 8)**: stores class metadata, constant pool, static variables, method bytecode. Metaspace grows in native memory, not the heap, which removed the old `PermGen` size errors.
- **Heap**: stores all objects and arrays. Divided into generations for generational garbage collection.
- **Java Stack**: one per thread. Holds stack frames — each frame has local variables, operand stack, and a reference to the constant pool.
- **PC Register**: one per thread, tracks the current executing instruction.
- **Native Method Stack**: supports native (JNI) method calls.

### 11.3 Generational Garbage Collection

The heap is split into generations because most objects die young (the "weak generational hypothesis"):

```
Heap
 ├── Young Generation
 │    ├── Eden Space         ← new objects allocated here
 │    ├── Survivor Space S0
 │    └── Survivor Space S1
 └── Old Generation (Tenured) ← long-lived objects promoted here
```

Minor GC cleans the young generation frequently and is fast. Major/Full GC cleans the old generation and is slower, causing longer pauses.

Object promotion flow:

1. Object is allocated in Eden.
2. Eden fills up, minor GC triggers.
3. Live objects copied to a survivor space.
4. After surviving a configurable number of GC cycles (tenuring threshold), the object is promoted to the old generation.

### 11.4 Garbage Collector Algorithms

- **Serial GC**: single-threaded, best for small heaps and simple applications.
- **Parallel GC**: multiple threads for collection, optimizes for throughput, still has stop-the-world pauses.
- **CMS (Concurrent Mark Sweep)**: deprecated, tried to reduce pause times by doing most work concurrently with the application.
- **G1 GC (Garbage First)**: default since Java 9. Splits the heap into regions, prioritizes collecting regions with the most garbage first, balances throughput and pause time.
- **ZGC**: designed for very large heaps with sub-millisecond pause targets, uses colored pointers and load barriers.
- **Shenandoah**: similar low-pause goals to ZGC, different implementation strategy.

Choosing a GC in production:

```
-XX:+UseG1GC        # good general purpose default
-XX:+UseZGC         # very large heap, low latency requirement
-XX:+UseParallelGC  # batch/throughput-oriented workloads
```

### 11.5 JIT Compilation Tiers

The JVM starts by interpreting bytecode, then compiles "hot" methods (frequently executed) into native machine code:

- **C1 (Client compiler)**: compiles quickly with light optimization, used for startup speed.
- **C2 (Server compiler)**: compiles slowly with heavy optimization (inlining, loop unrolling, escape analysis), used for long-running hot methods.
- **Tiered compilation** (default): starts with the interpreter, moves to C1, then eventually promotes very hot methods to C2.

**Escape analysis** lets the JIT determine that an object never escapes a method. If so, it can be allocated on the stack instead of the heap, or its fields can be scalarized into registers — removing allocation and GC overhead entirely.

### 11.6 String Pool and Interning

```java
String a = "hello";       // literal — goes into the string pool
String b = "hello";       // reuses the same pooled reference
String c = new String("hello"); // new object on the heap, NOT pooled automatically
String d = c.intern();    // explicitly interns, now d == a
```

`a == b` is `true` because both point to the same pooled literal. `a == c` is `false` because `c` is a distinct heap object. This matters in high-throughput systems where excessive `new String(...)` allocation can bloat memory; `String.intern()` or simply preferring literals avoids this.

### 11.7 HashMap Internals

A `HashMap` stores entries in an array of buckets. The bucket index is computed as:

```java
index = (capacity - 1) & (hash ^ (hash >>> 16));
```

Key internals:

- Each bucket holds a linked list of entries that hash to the same index (collision chain).
- Since Java 8, if a bucket's chain grows to 8 or more entries **and** the table capacity is at least 64, the chain converts to a red-black tree (treeification) for O(log n) worst-case lookup instead of O(n).
- The default load factor is 0.75. When `size > capacity * loadFactor`, the table resizes (doubles) and all entries are rehashed.
- `HashMap` is **not thread-safe**. Concurrent modification during resize can cause infinite loops in old JDKs, or lost updates in general.

For concurrent access use `ConcurrentHashMap`, which since Java 8 uses per-bin locking (via `synchronized` on the bin's first node) plus CAS operations instead of full-table locking (segment locking from Java 7 was removed).

### 11.8 The Java Memory Model and `volatile`

The Java Memory Model (JMM) defines the **happens-before** relationship — the guarantee that determines whether one thread's write is visible to another thread's read.

Key happens-before rules:

- A write to a `volatile` field happens-before every subsequent read of that field.
- An unlock on a monitor happens-before every subsequent lock on that same monitor.
- Thread.start() happens-before any action in the started thread.
- All actions in a thread happen-before another thread successfully returns from `Thread.join()` on it.

`volatile` guarantees visibility and prevents instruction reordering around the field, but **does not** guarantee atomicity for compound operations like `count++` (that requires `synchronized`, `Lock`, or `AtomicInteger`).

```java
private volatile boolean running = true; // visibility across threads

public void stop() {
    running = false; // guaranteed to be seen by other threads promptly
}
```

### 11.9 CAS and Atomic Classes

Compare-And-Swap (CAS) is a hardware-supported atomic instruction: "update this memory location to a new value only if it still holds the expected old value." `AtomicInteger`, `AtomicLong`, and `AtomicReference` use CAS in a retry loop instead of locking:

```java
AtomicInteger counter = new AtomicInteger(0);

public void increment() {
    int prev, next;
    do {
        prev = counter.get();
        next = prev + 1;
    } while (!counter.compareAndSet(prev, next)); // retries under contention
}

// Simpler, same effect:
counter.incrementAndGet();
```

CAS-based structures scale better under moderate contention than locks because there is no thread blocking/parking — but under very high contention, locks (or striped counters like `LongAdder`) can perform better.

### 11.10 Streams Internals

`Stream` pipelines are **lazy**. Intermediate operations (`map`, `filter`) just build up a pipeline description; nothing executes until a terminal operation (`collect`, `forEach`, `reduce`) is invoked. This allows short-circuiting:

```java
Optional<Integer> firstMatch = numbers.stream()
        .filter(n -> n > 100)   // not executed yet
        .map(n -> n * 2)        // not executed yet
        .findFirst();           // triggers execution, one element at a time
```

Internally, a stream is a chain of `Sink` objects. Each element flows through the chain one at a time (unless a stateful operation like `sorted()` requires buffering all elements first). Parallel streams split the source using a `Spliterator` and process chunks on the common `ForkJoinPool`.

### 11.11 Records, Sealed Classes, and Pattern Matching (Modern Java)

```java
// Record — immutable data carrier, auto-generates constructor, accessors, equals, hashCode, toString
public record OrderLine(String productId, int quantity, BigDecimal price) {
    public BigDecimal lineTotal() {
        return price.multiply(BigDecimal.valueOf(quantity));
    }
}

// Sealed class — restricts which classes may extend it
public sealed interface PaymentEvent permits PaymentSucceeded, PaymentFailed {
}

public record PaymentSucceeded(String orderId) implements PaymentEvent {}
public record PaymentFailed(String orderId, String reason) implements PaymentEvent {}

// Pattern matching with switch — exhaustive, compiler-checked
public String describe(PaymentEvent event) {
    return switch (event) {
        case PaymentSucceeded s -> "Order " + s.orderId() + " paid";
        case PaymentFailed f -> "Order " + f.orderId() + " failed: " + f.reason();
    };
}
```

Sealed types plus exhaustive `switch` give you compiler-enforced exhaustiveness — if you add a new subtype and forget to handle it in a switch, the build fails instead of throwing a runtime surprise.

### 11.12 Virtual Threads (Project Loom)

Virtual threads are lightweight threads managed by the JVM instead of the OS. They make blocking-style code scale to very high concurrency without needing reactive programming:

```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    for (int i = 0; i < 100_000; i++) {
        int taskId = i;
        executor.submit(() -> {
            // blocking call — cheap because it "unmounts" from the carrier OS thread
            callDownstreamService(taskId);
        });
    }
}
```

Virtual threads are cheap to create (millions are feasible) because blocking operations (I/O, `Thread.sleep`) release the underlying OS "carrier" thread back to a small shared pool while the virtual thread waits. They are best for I/O-bound workloads, not CPU-bound work, and do not replace `synchronized`-based pinning concerns — avoid holding `synchronized` blocks across blocking calls on virtual threads.

---

## 12. Deep Dive: Spring Framework and Spring Boot Internals

### 12.1 The `ApplicationContext` Lifecycle

Understanding what happens between `SpringApplication.run()` and your first request being served:

1. **Environment preparation** — property sources loaded (application.yml, environment variables, command-line args, in that precedence order).
2. **Context creation** — an `AnnotationConfigApplicationContext` (or reactive variant) is instantiated.
3. **BeanDefinition loading** — component scanning discovers classes annotated with `@Component`, `@Service`, `@Repository`, `@Controller`, `@Configuration`, and registers `BeanDefinition` objects (metadata, not instances yet).
4. **BeanFactoryPostProcessor phase** — processors like `PropertySourcesPlaceholderConfigurer` modify bean *definitions* before any bean is instantiated.
5. **Bean instantiation** — the container creates singleton beans eagerly (by default), resolving constructor dependencies recursively.
6. **BeanPostProcessor phase** — runs around each bean's initialization:
   - `postProcessBeforeInitialization` (this is where `@Autowired` field injection and `@PostConstruct` scheduling happens for some processors)
   - the bean's `afterPropertiesSet()` / `@PostConstruct` method runs
   - `postProcessAfterInitialization` (this is where AOP proxies are created — a bean can be **wrapped** here, meaning the object you receive via injection may not be the raw instance)
7. **Application is refreshed** — `ContextRefreshedEvent` published, embedded server (Tomcat/Netty) starts accepting connections.
8. **Shutdown hook registered** — on JVM shutdown, `@PreDestroy` methods run and the context closes gracefully.

### 12.2 `BeanFactoryPostProcessor` vs `BeanPostProcessor`

|                              | Operates on                          | Timing                            | Typical use                                                                                 |
| ---------------------------- | ------------------------------------ | --------------------------------- | ------------------------------------------------------------------------------------------- |
| `BeanFactoryPostProcessor` | Bean**definitions** (metadata) | Before any bean is instantiated   | Property placeholder resolution, modifying bean definitions programmatically                |
| `BeanPostProcessor`        | Bean**instances**              | Around each bean's initialization | AOP proxy creation,`@Autowired`/`@Value` field injection, validation of bean properties |

### 12.3 Proxy Mechanisms: JDK Dynamic Proxy vs CGLIB

Spring AOP (used for `@Transactional`, `@Async`, `@Cacheable`, custom `@Aspect` advice) wraps your bean in a proxy:

- **JDK Dynamic Proxy** — used when the bean implements at least one interface. The proxy implements the same interface(s) and delegates to the real object, adding advice around each call.
- **CGLIB Proxy** — used when the bean has no interface (a concrete class). CGLIB generates a subclass at runtime that overrides public/protected methods to add advice.

**The classic self-invocation pitfall:**

```java
@Service
public class OrderService {

    public void placeOrder(Order order) {
        // Calling another @Transactional method on 'this' bypasses the proxy!
        this.saveWithAudit(order); // NOT intercepted — runs without a new transaction
    }

    @Transactional
    public void saveWithAudit(Order order) {
        // ...
    }
}
```

Because `this` refers to the raw target object, not the proxy, calling `this.saveWithAudit()` from within the same class skips the AOP proxy entirely — `@Transactional`, `@Async`, `@Cacheable` are silently ignored. The fix is to inject the bean into itself (via `@Lazy` self-injection) or move the method to a separate collaborator bean.

### 12.4 `@Transactional` Deep Dive

- `@Transactional` only works through the proxy — it has no effect on `private` methods (the proxy cannot override them) or on self-invocation as shown above.
- **Propagation** controls how a transaction relates to an existing one:
  - `REQUIRED` (default) — join the existing transaction, or create one if none exists.
  - `REQUIRES_NEW` — always suspend any existing transaction and start a new, independent one.
  - `NESTED` — start a savepoint within the existing transaction; rollback only unwinds to the savepoint.
  - `MANDATORY` — must run inside an existing transaction, throws if none exists.
- **Isolation** controls what one transaction can see of another's uncommitted/committed changes: `READ_UNCOMMITTED`, `READ_COMMITTED`, `REPEATABLE_READ`, `SERIALIZABLE`.
- By default, Spring rolls back only on unchecked exceptions (`RuntimeException`, `Error`). To roll back on a checked exception, declare it explicitly:

```java
@Transactional(rollbackFor = InsufficientBalanceException.class)
public void transferFunds(String fromAccount, String toAccount, BigDecimal amount) throws InsufficientBalanceException {
    // ...
}
```

### 12.5 Spring Security Filter Chain, Explained End to End

Every incoming HTTP request to a Spring Security-secured application passes through an ordered chain of `Filter` objects before it ever reaches your controller:

```
Request
  │
  ▼
SecurityContextPersistenceFilter   → loads/saves SecurityContext (session or stateless)
  │
  ▼
CsrfFilter                         → validates CSRF token for state-changing requests
  │
  ▼
LogoutFilter                       → handles /logout
  │
  ▼
UsernamePasswordAuthenticationFilter (form login) OR
BasicAuthenticationFilter (HTTP Basic) OR
Custom JwtAuthenticationFilter (token-based APIs)
  │
  ▼
ExceptionTranslationFilter         → catches AccessDeniedException / AuthenticationException
  │
  ▼
FilterSecurityInterceptor / AuthorizationFilter → enforces access rules (hasRole, permitAll, etc.)
  │
  ▼
Your DispatcherServlet → Controller
```

A minimal real JWT filter implementation:

```java
package com.example.demo.security;

import io.jsonwebtoken.Claims;
import io.jsonwebtoken.Jwts;
import jakarta.servlet.FilterChain;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.springframework.lang.NonNull;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.security.web.authentication.WebAuthenticationDetailsSource;
import org.springframework.stereotype.Component;
import org.springframework.web.filter.OncePerRequestFilter;

import java.io.IOException;
import java.security.Key;
import java.util.List;

@Component
public class JwtAuthenticationFilter extends OncePerRequestFilter {

    private final Key signingKey;

    public JwtAuthenticationFilter(Key signingKey) {
        this.signingKey = signingKey;
    }

    @Override
    protected void doFilterInternal(@NonNull HttpServletRequest request,
                                     @NonNull HttpServletResponse response,
                                     @NonNull FilterChain filterChain) throws ServletException, IOException {

        String header = request.getHeader("Authorization");

        if (header != null && header.startsWith("Bearer ")) {
            String token = header.substring(7);
            try {
                Claims claims = Jwts.parserBuilder()
                        .setSigningKey(signingKey)
                        .build()
                        .parseClaimsJws(token)
                        .getBody();

                String username = claims.getSubject();
                var authentication = new UsernamePasswordAuthenticationToken(username, null, List.of());
                authentication.setDetails(new WebAuthenticationDetailsSource().buildDetails(request));
                SecurityContextHolder.getContext().setAuthentication(authentication);
            } catch (Exception ex) {
                // Invalid/expired token: leave context unauthenticated, let downstream 401/403 handling apply
                SecurityContextHolder.clearContext();
            }
        }

        filterChain.doFilter(request, response);
    }
}
```

Registering the filter and locking down endpoints:

```java
package com.example.demo.security;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
import org.springframework.security.config.http.SessionCreationPolicy;
import org.springframework.security.web.SecurityFilterChain;
import org.springframework.security.web.authentication.UsernamePasswordAuthenticationFilter;

@Configuration
@EnableWebSecurity
public class SecurityConfig {

    private final JwtAuthenticationFilter jwtAuthenticationFilter;

    public SecurityConfig(JwtAuthenticationFilter jwtAuthenticationFilter) {
        this.jwtAuthenticationFilter = jwtAuthenticationFilter;
    }

    @Bean
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
        http
            .csrf(csrf -> csrf.disable()) // acceptable for stateless token APIs, not for cookie-based sessions
            .sessionManagement(session -> session.sessionCreationPolicy(SessionCreationPolicy.STATELESS))
            .authorizeHttpRequests(auth -> auth
                .requestMatchers("/auth/login", "/actuator/health").permitAll()
                .requestMatchers("/admin/**").hasRole("ADMIN")
                .anyRequest().authenticated()
            )
            .addFilterBefore(jwtAuthenticationFilter, UsernamePasswordAuthenticationFilter.class);

        return http.build();
    }
}
```

### 12.6 Reactive Stack: Netty Event Loop and Reactor Operators

Spring WebFlux runs on Reactor + Netty by default. Instead of a thread-per-request model (Tomcat/Servlet), a small fixed number of **event loop threads** handle many concurrent connections by never blocking:

```
Client requests
     │
     ▼
Netty Event Loop (a handful of threads, e.g. 4-8)
     │  each thread multiplexes many connections via non-blocking I/O
     ▼
Reactor pipeline (Mono/Flux) — subscribes, applies operators, emits signals
     │
     ▼
Non-blocking downstream calls (WebClient, R2DBC) — never park a thread waiting
```

The cardinal rule: **never call blocking code (JDBC, `Thread.sleep`, blocking HTTP clients) directly inside a reactive chain** — it starves the event loop and stalls all requests sharing that thread. If you must call blocking code, offload it explicitly:

```java
Mono<String> result = Mono.fromCallable(() -> legacyBlockingCall())
        .subscribeOn(Schedulers.boundedElastic()); // dedicated thread pool for blocking work
```

Common Reactor operators:

```java
Flux<Order> orders = orderRepository.findAll()
        .filter(order -> order.getStatus() == OrderStatus.PENDING)
        .flatMap(order -> enrichWithCustomer(order))   // concurrent, unordered
        .concatMap(order -> chargePayment(order))      // sequential, preserves order
        .onErrorResume(ex -> Flux.empty())              // graceful fallback
        .doOnNext(order -> log.info("Processed {}", order.getId()))
        .timeout(Duration.ofSeconds(5));
```

### 12.7 Testing Slices, Explained

Spring Boot provides narrow "test slices" that load only the beans relevant to a layer, keeping tests fast:

- `@WebMvcTest(OrderController.class)` — loads only MVC infrastructure (controllers, `@ControllerAdvice`, filters) and mocks the service layer via `@MockBean`.
- `@DataJpaTest` — loads only JPA-related beans, configures an embedded/test database, wraps each test in a rollback transaction.
- `@JsonTest` — loads only Jackson-related beans to test serialization/deserialization of DTOs.
- `@SpringBootTest` — loads the **full** application context; use `webEnvironment = RANDOM_PORT` with `TestRestTemplate` or `WebTestClient` for true end-to-end tests, but expect slower test suites.

```java
@WebMvcTest(OrderController.class)
class OrderControllerTest {

    @Autowired
    private MockMvc mockMvc;

    @MockBean
    private OrderService orderService;

    @Test
    void returnsOrderById() throws Exception {
        when(orderService.findById(1L)).thenReturn(new OrderDto(1L, "PENDING"));

        mockMvc.perform(get("/api/orders/1"))
                .andExpect(status().isOk())
                .andExpect(jsonPath("$.status").value("PENDING"));
    }
}
```

### 12.8 Actuator Internals

Actuator exposes operational endpoints (`/actuator/health`, `/actuator/metrics`, `/actuator/info`) backed by `HealthIndicator` and `MeterRegistry` beans. Custom health checks and metrics are trivial to add:

```java
@Component
public class DownstreamHealthIndicator implements HealthIndicator {

    @Override
    public Health health() {
        boolean reachable = pingDownstreamService();
        return reachable
                ? Health.up().withDetail("downstream", "reachable").build()
                : Health.down().withDetail("downstream", "unreachable").build();
    }
}
```

In Kubernetes, `/actuator/health/liveness` and `/actuator/health/readiness` map directly to liveness and readiness probes — readiness failing takes the pod out of the load balancer rotation without killing it; liveness failing causes a pod restart.

---

## 13. Full Project: Expense Tracker (Complete Working Code)

This section contains a complete, runnable Spring Boot module. Every file shown below can be copy-pasted into a real project structure.

### 13.1 Project Structure

```
expense-tracker/
├── pom.xml
├── src/main/java/com/example/expense/
│   ├── ExpenseTrackerApplication.java
│   ├── entity/
│   │   ├── TransactionRecord.java
│   │   └── TransactionType.java
│   ├── dto/
│   │   ├── TransactionRequest.java
│   │   ├── TransactionResponse.java
│   │   └── MonthlySummaryResponse.java
│   ├── repository/
│   │   └── TransactionRepository.java
│   ├── service/
│   │   └── TransactionService.java
│   ├── controller/
│   │   └── TransactionController.java
│   └── exception/
│       ├── TransactionNotFoundException.java
│       └── GlobalExceptionHandler.java
├── src/main/resources/application.yml
├── src/test/java/com/example/expense/service/TransactionServiceTest.java
└── Dockerfile
```

### 13.2 `pom.xml` (Key Dependencies)

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-validation</artifactId>
    </dependency>
    <dependency>
        <groupId>com.h2database</groupId>
        <artifactId>h2</artifactId>
        <scope>runtime</scope>
    </dependency>
    <dependency>
        <groupId>org.postgresql</groupId>
        <artifactId>postgresql</artifactId>
        <scope>runtime</scope>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

### 13.3 Entity Layer

```java
package com.example.expense.entity;

public enum TransactionType {
    INCOME,
    EXPENSE
}
```

```java
package com.example.expense.entity;

import jakarta.persistence.*;
import java.math.BigDecimal;
import java.time.LocalDate;

@Entity
@Table(name = "transaction_record")
public class TransactionRecord {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false)
    private String description;

    @Column(nullable = false, precision = 19, scale = 2)
    private BigDecimal amount;

    @Column(nullable = false)
    private LocalDate transactionDate;

    @Column(nullable = false)
    private String category;

    @Enumerated(EnumType.STRING)
    @Column(nullable = false)
    private TransactionType type;

    protected TransactionRecord() {
        // required by JPA
    }

    public TransactionRecord(String description, BigDecimal amount, LocalDate transactionDate,
                              String category, TransactionType type) {
        this.description = description;
        this.amount = amount;
        this.transactionDate = transactionDate;
        this.category = category;
        this.type = type;
    }

    public Long getId() {
        return id;
    }

    public String getDescription() {
        return description;
    }

    public BigDecimal getAmount() {
        return amount;
    }

    public LocalDate getTransactionDate() {
        return transactionDate;
    }

    public String getCategory() {
        return category;
    }

    public TransactionType getType() {
        return type;
    }

    public void update(String description, BigDecimal amount, LocalDate transactionDate,
                        String category, TransactionType type) {
        this.description = description;
        this.amount = amount;
        this.transactionDate = transactionDate;
        this.category = category;
        this.type = type;
    }
}
```

### 13.4 DTOs with Validation

```java
package com.example.expense.dto;

import com.example.expense.entity.TransactionType;
import jakarta.validation.constraints.DecimalMin;
import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.PastOrPresent;

import java.math.BigDecimal;
import java.time.LocalDate;

public record TransactionRequest(
        @NotBlank(message = "description must not be blank") String description,
        @NotNull @DecimalMin(value = "0.01", message = "amount must be greater than zero") BigDecimal amount,
        @NotNull @PastOrPresent(message = "transactionDate cannot be in the future") LocalDate transactionDate,
        @NotBlank String category,
        @NotNull TransactionType type
) {
}
```

```java
package com.example.expense.dto;

import com.example.expense.entity.TransactionType;

import java.math.BigDecimal;
import java.time.LocalDate;

public record TransactionResponse(
        Long id,
        String description,
        BigDecimal amount,
        LocalDate transactionDate,
        String category,
        TransactionType type
) {
}
```

```java
package com.example.expense.dto;

import java.math.BigDecimal;

public record MonthlySummaryResponse(
        int year,
        int month,
        BigDecimal totalIncome,
        BigDecimal totalExpense,
        BigDecimal netBalance
) {
}
```

### 13.5 Repository Layer

```java
package com.example.expense.repository;

import com.example.expense.entity.TransactionRecord;
import com.example.expense.entity.TransactionType;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;

import java.math.BigDecimal;
import java.time.LocalDate;

public interface TransactionRepository extends JpaRepository<TransactionRecord, Long> {

    Page<TransactionRecord> findByCategoryIgnoreCase(String category, Pageable pageable);

    Page<TransactionRecord> findByTransactionDateBetween(LocalDate start, LocalDate end, Pageable pageable);

    @Query("""
           SELECT COALESCE(SUM(t.amount), 0) FROM TransactionRecord t
           WHERE t.type = :type
             AND YEAR(t.transactionDate) = :year
             AND MONTH(t.transactionDate) = :month
           """)
    BigDecimal sumByTypeAndMonth(@Param("type") TransactionType type,
                                  @Param("year") int year,
                                  @Param("month") int month);
}
```

### 13.6 Service Layer

```java
package com.example.expense.service;

import com.example.expense.dto.MonthlySummaryResponse;
import com.example.expense.dto.TransactionRequest;
import com.example.expense.dto.TransactionResponse;
import com.example.expense.entity.TransactionRecord;
import com.example.expense.entity.TransactionType;
import com.example.expense.exception.TransactionNotFoundException;
import com.example.expense.repository.TransactionRepository;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.math.BigDecimal;

@Service
@Transactional(readOnly = true)
public class TransactionService {

    private final TransactionRepository transactionRepository;

    public TransactionService(TransactionRepository transactionRepository) {
        this.transactionRepository = transactionRepository;
    }

    @Transactional
    public TransactionResponse create(TransactionRequest request) {
        TransactionRecord record = new TransactionRecord(
                request.description(),
                request.amount(),
                request.transactionDate(),
                request.category(),
                request.type()
        );
        TransactionRecord saved = transactionRepository.save(record);
        return toResponse(saved);
    }

    public TransactionResponse getById(Long id) {
        return toResponse(findOrThrow(id));
    }

    public Page<TransactionResponse> listByCategory(String category, Pageable pageable) {
        return transactionRepository.findByCategoryIgnoreCase(category, pageable)
                .map(this::toResponse);
    }

    @Transactional
    public TransactionResponse update(Long id, TransactionRequest request) {
        TransactionRecord record = findOrThrow(id);
        record.update(request.description(), request.amount(), request.transactionDate(),
                request.category(), request.type());
        return toResponse(record); // dirty checking flushes the update automatically
    }

    @Transactional
    public void delete(Long id) {
        TransactionRecord record = findOrThrow(id);
        transactionRepository.delete(record);
    }

    public MonthlySummaryResponse monthlySummary(int year, int month) {
        BigDecimal income = transactionRepository.sumByTypeAndMonth(TransactionType.INCOME, year, month);
        BigDecimal expense = transactionRepository.sumByTypeAndMonth(TransactionType.EXPENSE, year, month);
        return new MonthlySummaryResponse(year, month, income, expense, income.subtract(expense));
    }

    private TransactionRecord findOrThrow(Long id) {
        return transactionRepository.findById(id)
                .orElseThrow(() -> new TransactionNotFoundException("Transaction not found: " + id));
    }

    private TransactionResponse toResponse(TransactionRecord record) {
        return new TransactionResponse(record.getId(), record.getDescription(), record.getAmount(),
                record.getTransactionDate(), record.getCategory(), record.getType());
    }
}
```

### 13.7 Controller Layer

```java
package com.example.expense.controller;

import com.example.expense.dto.MonthlySummaryResponse;
import com.example.expense.dto.TransactionRequest;
import com.example.expense.dto.TransactionResponse;
import com.example.expense.service.TransactionService;
import jakarta.validation.Valid;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/transactions")
public class TransactionController {

    private final TransactionService transactionService;

    public TransactionController(TransactionService transactionService) {
        this.transactionService = transactionService;
    }

    @PostMapping
    @ResponseStatus(HttpStatus.CREATED)
    public TransactionResponse create(@Valid @RequestBody TransactionRequest request) {
        return transactionService.create(request);
    }

    @GetMapping("/{id}")
    public TransactionResponse getById(@PathVariable Long id) {
        return transactionService.getById(id);
    }

    @GetMapping
    public Page<TransactionResponse> list(@RequestParam String category, Pageable pageable) {
        return transactionService.listByCategory(category, pageable);
    }

    @PutMapping("/{id}")
    public TransactionResponse update(@PathVariable Long id, @Valid @RequestBody TransactionRequest request) {
        return transactionService.update(id, request);
    }

    @DeleteMapping("/{id}")
    @ResponseStatus(HttpStatus.NO_CONTENT)
    public void delete(@PathVariable Long id) {
        transactionService.delete(id);
    }

    @GetMapping("/reports/monthly")
    public ResponseEntity<MonthlySummaryResponse> monthlySummary(@RequestParam int year, @RequestParam int month) {
        return ResponseEntity.ok(transactionService.monthlySummary(year, month));
    }
}
```

### 13.8 Exception Handling

```java
package com.example.expense.exception;

public class TransactionNotFoundException extends RuntimeException {
    public TransactionNotFoundException(String message) {
        super(message);
    }
}
```

```java
package com.example.expense.exception;

import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.MethodArgumentNotValidException;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.RestControllerAdvice;

import java.time.Instant;
import java.util.LinkedHashMap;
import java.util.Map;

@RestControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(TransactionNotFoundException.class)
    public ResponseEntity<Map<String, Object>> handleNotFound(TransactionNotFoundException ex) {
        return ResponseEntity.status(HttpStatus.NOT_FOUND).body(errorBody(ex.getMessage()));
    }

    @ExceptionHandler(MethodArgumentNotValidException.class)
    public ResponseEntity<Map<String, Object>> handleValidation(MethodArgumentNotValidException ex) {
        Map<String, String> fieldErrors = new LinkedHashMap<>();
        ex.getBindingResult().getFieldErrors().forEach(error ->
                fieldErrors.put(error.getField(), error.getDefaultMessage()));

        Map<String, Object> body = errorBody("Validation failed");
        body.put("fieldErrors", fieldErrors);
        return ResponseEntity.status(HttpStatus.BAD_REQUEST).body(body);
    }

    @ExceptionHandler(Exception.class)
    public ResponseEntity<Map<String, Object>> handleGeneric(Exception ex) {
        return ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR)
                .body(errorBody("Unexpected error occurred"));
    }

    private Map<String, Object> errorBody(String message) {
        Map<String, Object> body = new LinkedHashMap<>();
        body.put("timestamp", Instant.now().toString());
        body.put("message", message);
        return body;
    }
}
```

### 13.9 Configuration

```yaml
# application.yml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/expense_tracker
    username: ${DB_USERNAME:expense_user}
    password: ${DB_PASSWORD:changeme}
  jpa:
    hibernate:
      ddl-auto: validate
    open-in-view: false
  flyway:
    enabled: true

server:
  port: 8080

management:
  endpoints:
    web:
      exposure:
        include: health,info,metrics
```

### 13.10 Unit Test

```java
package com.example.expense.service;

import com.example.expense.dto.TransactionRequest;
import com.example.expense.entity.TransactionRecord;
import com.example.expense.entity.TransactionType;
import com.example.expense.repository.TransactionRepository;
import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.extension.ExtendWith;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.junit.jupiter.MockitoExtension;

import java.math.BigDecimal;
import java.time.LocalDate;

import static org.assertj.core.api.Assertions.assertThat;
import static org.mockito.ArgumentMatchers.any;
import static org.mockito.Mockito.when;

@ExtendWith(MockitoExtension.class)
class TransactionServiceTest {

    @Mock
    private TransactionRepository transactionRepository;

    @InjectMocks
    private TransactionService transactionService;

    @Test
    void createsTransactionAndReturnsResponse() {
        TransactionRequest request = new TransactionRequest(
                "Groceries", BigDecimal.valueOf(45.50), LocalDate.now(), "Food", TransactionType.EXPENSE);

        TransactionRecord saved = new TransactionRecord(
                request.description(), request.amount(), request.transactionDate(),
                request.category(), request.type());

        when(transactionRepository.save(any(TransactionRecord.class))).thenReturn(saved);

        var response = transactionService.create(request);

        assertThat(response.description()).isEqualTo("Groceries");
        assertThat(response.amount()).isEqualByComparingTo("45.50");
    }
}
```

### 13.11 Dockerfile

```dockerfile
FROM eclipse-temurin:21-jdk-alpine AS build
WORKDIR /app
COPY . .
RUN ./mvnw clean package -DskipTests

FROM eclipse-temurin:21-jre-alpine
WORKDIR /app
COPY --from=build /app/target/expense-tracker-*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```

---

## 14. Full Project: E-Commerce Order, Inventory and Payment Flow (Complete Working Code)

This project demonstrates the backend concerns that separate a toy CRUD app from a production-grade system: idempotency, inventory reservation, and compensating transactions (saga pattern) when a downstream step fails.

### 14.1 Order State Machine

```
CREATED → INVENTORY_RESERVED → PAYMENT_CHARGED → CONFIRMED
   │              │                    │
   │              │                    └── PAYMENT_FAILED → INVENTORY_RELEASED → CANCELLED
   │              └── INSUFFICIENT_STOCK → CANCELLED
   └── VALIDATION_FAILED → REJECTED
```

Each transition is a discrete, auditable step. If a later step fails, the system runs compensating actions for the steps already completed, instead of leaving the system in an inconsistent state.

### 14.2 Entities

```java
package com.example.ecommerce.entity;

public enum OrderStatus {
    CREATED,
    INVENTORY_RESERVED,
    PAYMENT_CHARGED,
    CONFIRMED,
    CANCELLED
}
```

```java
package com.example.ecommerce.entity;

import jakarta.persistence.*;
import java.math.BigDecimal;
import java.time.Instant;

@Entity
@Table(name = "orders")
public class Order {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false, unique = true)
    private String idempotencyKey;

    @Column(nullable = false)
    private String productId;

    @Column(nullable = false)
    private int quantity;

    @Column(nullable = false, precision = 19, scale = 2)
    private BigDecimal totalAmount;

    @Enumerated(EnumType.STRING)
    @Column(nullable = false)
    private OrderStatus status;

    @Version
    private Long version; // optimistic locking to prevent lost updates under concurrent status changes

    @Column(nullable = false)
    private Instant createdAt;

    protected Order() {
    }

    public Order(String idempotencyKey, String productId, int quantity, BigDecimal totalAmount) {
        this.idempotencyKey = idempotencyKey;
        this.productId = productId;
        this.quantity = quantity;
        this.totalAmount = totalAmount;
        this.status = OrderStatus.CREATED;
        this.createdAt = Instant.now();
    }

    public void markInventoryReserved() {
        this.status = OrderStatus.INVENTORY_RESERVED;
    }

    public void markPaymentCharged() {
        this.status = OrderStatus.PAYMENT_CHARGED;
    }

    public void markConfirmed() {
        this.status = OrderStatus.CONFIRMED;
    }

    public void markCancelled() {
        this.status = OrderStatus.CANCELLED;
    }

    public Long getId() {
        return id;
    }

    public String getIdempotencyKey() {
        return idempotencyKey;
    }

    public String getProductId() {
        return productId;
    }

    public int getQuantity() {
        return quantity;
    }

    public BigDecimal getTotalAmount() {
        return totalAmount;
    }

    public OrderStatus getStatus() {
        return status;
    }
}
```

### 14.3 Idempotency Support

Clients (especially mobile clients on flaky networks) may retry a checkout request. Without an idempotency key, this can create duplicate orders and double charges. The pattern: the client generates a unique key per checkout attempt; the server stores it and returns the original result on repeat.

```java
package com.example.ecommerce.repository;

import com.example.ecommerce.entity.Order;
import org.springframework.data.jpa.repository.JpaRepository;

import java.util.Optional;

public interface OrderRepository extends JpaRepository<Order, Long> {
    Optional<Order> findByIdempotencyKey(String idempotencyKey);
}
```

```java
package com.example.ecommerce.controller;

import jakarta.servlet.http.HttpServletRequest;
import org.springframework.http.HttpStatus;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.RestControllerAdvice;

@RestControllerAdvice
public class CheckoutExceptionAdvice {

    @ExceptionHandler(MissingIdempotencyKeyException.class)
    public org.springframework.http.ResponseEntity<String> handleMissingKey(MissingIdempotencyKeyException ex) {
        return org.springframework.http.ResponseEntity.status(HttpStatus.BAD_REQUEST)
                .body("Idempotency-Key header is required for checkout requests");
    }
}
```

```java
package com.example.ecommerce.controller;

public class MissingIdempotencyKeyException extends RuntimeException {
    public MissingIdempotencyKeyException(String message) {
        super(message);
    }
}
```

### 14.4 Inventory Reservation Service

```java
package com.example.ecommerce.service;

import com.example.ecommerce.entity.InventoryItem;
import com.example.ecommerce.exception.InsufficientStockException;
import com.example.ecommerce.repository.InventoryRepository;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

@Service
public class InventoryService {

    private final InventoryRepository inventoryRepository;

    public InventoryService(InventoryRepository inventoryRepository) {
        this.inventoryRepository = inventoryRepository;
    }

    /**
     * Uses a pessimistic write lock (SELECT ... FOR UPDATE) on the inventory row
     * so concurrent checkouts for the same product cannot both pass the stock check
     * and oversell the last unit.
     */
    @Transactional
    public void reserve(String productId, int quantity) {
        InventoryItem item = inventoryRepository.findByProductIdForUpdate(productId)
                .orElseThrow(() -> new InsufficientStockException("Unknown product: " + productId));

        if (item.getAvailableQuantity() < quantity) {
            throw new InsufficientStockException("Not enough stock for product: " + productId);
        }

        item.decreaseAvailable(quantity);
    }

    @Transactional
    public void release(String productId, int quantity) {
        inventoryRepository.findByProductIdForUpdate(productId)
                .ifPresent(item -> item.increaseAvailable(quantity));
    }
}
```

```java
package com.example.ecommerce.repository;

import com.example.ecommerce.entity.InventoryItem;
import jakarta.persistence.LockModeType;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Lock;
import org.springframework.data.jpa.repository.Query;

import java.util.Optional;

public interface InventoryRepository extends JpaRepository<InventoryItem, Long> {

    @Lock(LockModeType.PESSIMISTIC_WRITE)
    @Query("SELECT i FROM InventoryItem i WHERE i.productId = :productId")
    Optional<InventoryItem> findByProductIdForUpdate(String productId);
}
```

### 14.5 Payment Gateway Adapter (Port and Adapter Pattern)

Abstracting the payment provider behind an interface keeps the business logic testable and provider-agnostic:

```java
package com.example.ecommerce.payment;

import java.math.BigDecimal;

public interface PaymentGateway {
    PaymentResult charge(String orderId, BigDecimal amount);
}
```

```java
package com.example.ecommerce.payment;

public record PaymentResult(boolean success, String transactionReference, String failureReason) {
}
```

```java
package com.example.ecommerce.payment;

import org.springframework.stereotype.Component;

import java.math.BigDecimal;
import java.util.UUID;

@Component
public class MockPaymentGateway implements PaymentGateway {

    @Override
    public PaymentResult charge(String orderId, BigDecimal amount) {
        // Real implementations call Stripe/Adyen/internal payment rails here.
        boolean approved = amount.compareTo(java.math.BigDecimal.valueOf(10000)) < 0;
        return approved
                ? new PaymentResult(true, UUID.randomUUID().toString(), null)
                : new PaymentResult(false, null, "Amount exceeds approval limit");
    }
}
```

### 14.6 Checkout Orchestration with Compensating Transactions (Saga Pattern)

This is the core of the project — a service that coordinates multiple steps across different resources and **compensates** (undoes) prior steps if a later step fails:

```java
package com.example.ecommerce.service;

import com.example.ecommerce.entity.Order;
import com.example.ecommerce.exception.InsufficientStockException;
import com.example.ecommerce.exception.PaymentDeclinedException;
import com.example.ecommerce.payment.PaymentGateway;
import com.example.ecommerce.payment.PaymentResult;
import com.example.ecommerce.repository.OrderRepository;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.math.BigDecimal;

@Service
public class CheckoutService {

    private static final Logger log = LoggerFactory.getLogger(CheckoutService.class);

    private final OrderRepository orderRepository;
    private final InventoryService inventoryService;
    private final PaymentGateway paymentGateway;

    public CheckoutService(OrderRepository orderRepository, InventoryService inventoryService,
                            PaymentGateway paymentGateway) {
        this.orderRepository = orderRepository;
        this.inventoryService = inventoryService;
        this.paymentGateway = paymentGateway;
    }

    public Order checkout(String idempotencyKey, String productId, int quantity, BigDecimal totalAmount) {
        // Step 0: idempotency check — replay the previous result instead of processing twice.
        var existing = orderRepository.findByIdempotencyKey(idempotencyKey);
        if (existing.isPresent()) {
            log.info("Idempotent replay for key {}", idempotencyKey);
            return existing.get();
        }

        Order order = createOrder(idempotencyKey, productId, quantity, totalAmount);

        try {
            // Step 1: reserve inventory (own local transaction)
            inventoryService.reserve(productId, quantity);
            markInventoryReserved(order);

            // Step 2: charge payment (external call, NOT part of the DB transaction)
            PaymentResult result = paymentGateway.charge(order.getIdempotencyKey(), totalAmount);
            if (!result.success()) {
                throw new PaymentDeclinedException(result.failureReason());
            }
            markPaymentCharged(order);

            // Step 3: confirm order
            return confirmOrder(order);

        } catch (InsufficientStockException ex) {
            cancelOrder(order);
            throw ex;

        } catch (PaymentDeclinedException ex) {
            // Compensating action: release the inventory that was reserved in step 1.
            inventoryService.release(productId, quantity);
            cancelOrder(order);
            throw ex;
        }
    }

    @Transactional
    protected Order createOrder(String idempotencyKey, String productId, int quantity, BigDecimal totalAmount) {
        Order order = new Order(idempotencyKey, productId, quantity, totalAmount);
        return orderRepository.save(order);
    }

    @Transactional
    protected void markInventoryReserved(Order order) {
        order.markInventoryReserved();
        orderRepository.save(order);
    }

    @Transactional
    protected void markPaymentCharged(Order order) {
        order.markPaymentCharged();
        orderRepository.save(order);
    }

    @Transactional
    protected Order confirmOrder(Order order) {
        order.markConfirmed();
        return orderRepository.save(order);
    }

    @Transactional
    protected void cancelOrder(Order order) {
        order.markCancelled();
        orderRepository.save(order);
    }
}
```

Why each step is its own small `@Transactional` method instead of one large transaction: the payment gateway call is a **remote network call**. Holding a single long-lived database transaction (and its row locks) open across a slow external HTTP call would hold locks far too long and destroy throughput under load. Each step commits independently, and failures are handled with explicit compensation instead of relying on a database rollback that cannot undo an external payment call anyway.

### 14.7 Controller

```java
package com.example.ecommerce.controller;

import com.example.ecommerce.entity.Order;
import com.example.ecommerce.service.CheckoutService;
import jakarta.validation.constraints.Min;
import jakarta.validation.constraints.NotBlank;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.math.BigDecimal;

@RestController
@RequestMapping("/api/checkout")
public class CheckoutController {

    private final CheckoutService checkoutService;

    public CheckoutController(CheckoutService checkoutService) {
        this.checkoutService = checkoutService;
    }

    public record CheckoutRequest(@NotBlank String productId, @Min(1) int quantity, BigDecimal totalAmount) {
    }

    @PostMapping
    public ResponseEntity<Order> checkout(@RequestHeader("Idempotency-Key") String idempotencyKey,
                                           @RequestBody CheckoutRequest request) {
        if (idempotencyKey == null || idempotencyKey.isBlank()) {
            throw new MissingIdempotencyKeyException("Idempotency-Key header is required");
        }
        Order order = checkoutService.checkout(idempotencyKey, request.productId(), request.quantity(),
                request.totalAmount());
        return ResponseEntity.ok(order);
    }
}
```

---

## 15. Full Project: URL Shortener with Redis Rate Limiting (Complete Working Code)

This project demonstrates a Base62 short-code algorithm, Redis-backed atomic counters, a token-bucket rate limiter, and Kafka event publishing for click analytics — all common real-world backend patterns.

### 15.1 Base62 Encoding

Short codes should be compact and URL-safe. Base62 (digits + lowercase + uppercase) turns an incrementing numeric ID into a short string:

```java
package com.example.shortener.util;

public final class Base62Encoder {

    private static final String ALPHABET = "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    private static final int BASE = ALPHABET.length();

    private Base62Encoder() {
    }

    public static String encode(long value) {
        if (value == 0) {
            return String.valueOf(ALPHABET.charAt(0));
        }
        StringBuilder builder = new StringBuilder();
        long remaining = value;
        while (remaining > 0) {
            int index = (int) (remaining % BASE);
            builder.append(ALPHABET.charAt(index));
            remaining /= BASE;
        }
        return builder.reverse().toString();
    }

    public static long decode(String code) {
        long result = 0;
        for (char c : code.toCharArray()) {
            result = result * BASE + ALPHABET.indexOf(c);
        }
        return result;
    }
}
```

Using a database auto-increment ID (or a Redis `INCR` counter) as the input guarantees uniqueness without needing to check for collisions.

### 15.2 Entity and Repository

```java
package com.example.shortener.entity;

import jakarta.persistence.*;
import java.time.Instant;

@Entity
@Table(name = "short_url")
public class ShortUrl {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false, unique = true)
    private String shortCode;

    @Column(nullable = false, length = 2048)
    private String originalUrl;

    @Column(nullable = false)
    private Instant createdAt;

    private Instant expiresAt;

    protected ShortUrl() {
    }

    public ShortUrl(String originalUrl, Instant expiresAt) {
        this.originalUrl = originalUrl;
        this.expiresAt = expiresAt;
        this.createdAt = Instant.now();
    }

    public void assignShortCode(String shortCode) {
        this.shortCode = shortCode;
    }

    public Long getId() {
        return id;
    }

    public String getShortCode() {
        return shortCode;
    }

    public String getOriginalUrl() {
        return originalUrl;
    }

    public boolean isExpired() {
        return expiresAt != null && Instant.now().isAfter(expiresAt);
    }
}
```

```java
package com.example.shortener.repository;

import com.example.shortener.entity.ShortUrl;
import org.springframework.data.jpa.repository.JpaRepository;

import java.util.Optional;

public interface ShortUrlRepository extends JpaRepository<ShortUrl, Long> {
    Optional<ShortUrl> findByShortCode(String shortCode);
}
```

### 15.3 Redis-Backed Token Bucket Rate Limiter

A token bucket allows short bursts while enforcing a steady average rate — better for real traffic patterns than a strict fixed window. This implementation uses a Lua script for atomicity so the check-and-decrement happens as a single Redis operation, avoiding race conditions between concurrent requests:

```java
package com.example.shortener.ratelimit;

import org.springframework.data.redis.core.StringRedisTemplate;
import org.springframework.data.redis.core.script.DefaultRedisScript;
import org.springframework.stereotype.Component;

import java.util.List;

@Component
public class RedisTokenBucketRateLimiter {

    private static final String LUA_SCRIPT = """
            local key = KEYS[1]
            local capacity = tonumber(ARGV[1])
            local refillRatePerSecond = tonumber(ARGV[2])
            local now = tonumber(ARGV[3])

            local bucket = redis.call('HMGET', key, 'tokens', 'timestamp')
            local tokens = tonumber(bucket[1])
            local lastRefill = tonumber(bucket[2])

            if tokens == nil then
                tokens = capacity
                lastRefill = now
            end

            local elapsed = math.max(0, now - lastRefill)
            local refill = elapsed * refillRatePerSecond
            tokens = math.min(capacity, tokens + refill)

            local allowed = 0
            if tokens >= 1 then
                tokens = tokens - 1
                allowed = 1
            end

            redis.call('HMSET', key, 'tokens', tokens, 'timestamp', now)
            redis.call('EXPIRE', key, 60)

            return allowed
            """;

    private final StringRedisTemplate redisTemplate;
    private final DefaultRedisScript<Long> script;

    public RedisTokenBucketRateLimiter(StringRedisTemplate redisTemplate) {
        this.redisTemplate = redisTemplate;
        this.script = new DefaultRedisScript<>(LUA_SCRIPT, Long.class);
    }

    public boolean tryAcquire(String clientKey, int capacity, double refillRatePerSecond) {
        double nowSeconds = System.currentTimeMillis() / 1000.0;
        Long result = redisTemplate.execute(
                script,
                List.of("rate-limit:" + clientKey),
                String.valueOf(capacity),
                String.valueOf(refillRatePerSecond),
                String.valueOf(nowSeconds)
        );
        return result != null && result == 1L;
    }
}
```

Applying it as a servlet filter so it protects every endpoint uniformly:

```java
package com.example.shortener.ratelimit;

import jakarta.servlet.FilterChain;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.springframework.core.annotation.Order;
import org.springframework.stereotype.Component;
import org.springframework.web.filter.OncePerRequestFilter;

import java.io.IOException;

@Component
@Order(1)
public class RateLimitFilter extends OncePerRequestFilter {

    private final RedisTokenBucketRateLimiter rateLimiter;

    public RateLimitFilter(RedisTokenBucketRateLimiter rateLimiter) {
        this.rateLimiter = rateLimiter;
    }

    @Override
    protected void doFilterInternal(HttpServletRequest request, HttpServletResponse response,
                                     FilterChain filterChain) throws ServletException, IOException {
        String clientIp = request.getRemoteAddr();

        // Allow 20 requests per client, refilling at 5 tokens/second (steady-state ~5 req/s, burst up to 20).
        if (!rateLimiter.tryAcquire(clientIp, 20, 5.0)) {
            response.setStatus(429); // Too Many Requests
            response.getWriter().write("Rate limit exceeded, try again shortly");
            return;
        }

        filterChain.doFilter(request, response);
    }
}
```

### 15.4 Service Layer

```java
package com.example.shortener.service;

import com.example.shortener.entity.ShortUrl;
import com.example.shortener.exception.ShortUrlNotFoundException;
import com.example.shortener.repository.ShortUrlRepository;
import com.example.shortener.util.Base62Encoder;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.time.Instant;

@Service
public class ShortenerService {

    private final ShortUrlRepository shortUrlRepository;

    public ShortenerService(ShortUrlRepository shortUrlRepository) {
        this.shortUrlRepository = shortUrlRepository;
    }

    @Transactional
    public String createShortUrl(String originalUrl, Instant expiresAt) {
        ShortUrl entity = new ShortUrl(originalUrl, expiresAt);
        ShortUrl saved = shortUrlRepository.save(entity); // flush to get the generated ID
        String code = Base62Encoder.encode(saved.getId());
        saved.assignShortCode(code);
        return code;
    }

    @Transactional(readOnly = true)
    public String resolve(String shortCode) {
        ShortUrl entity = shortUrlRepository.findByShortCode(shortCode)
                .orElseThrow(() -> new ShortUrlNotFoundException("Unknown short code: " + shortCode));

        if (entity.isExpired()) {
            throw new ShortUrlNotFoundException("Short URL has expired: " + shortCode);
        }
        return entity.getOriginalUrl();
    }
}
```

### 15.5 Controller with Redirect and Click Analytics Publishing

```java
package com.example.shortener.controller;

import com.example.shortener.analytics.ClickEventPublisher;
import com.example.shortener.service.ShortenerService;
import jakarta.validation.constraints.NotBlank;
import org.springframework.http.HttpHeaders;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.net.URI;
import java.time.Instant;

@RestController
public class ShortenerController {

    private final ShortenerService shortenerService;
    private final ClickEventPublisher clickEventPublisher;

    public ShortenerController(ShortenerService shortenerService, ClickEventPublisher clickEventPublisher) {
        this.shortenerService = shortenerService;
        this.clickEventPublisher = clickEventPublisher;
    }

    public record ShortenRequest(@NotBlank String url, Instant expiresAt) {
    }

    @PostMapping("/api/shorten")
    public ResponseEntity<String> shorten(@RequestBody ShortenRequest request) {
        String code = shortenerService.createShortUrl(request.url(), request.expiresAt());
        return ResponseEntity.status(HttpStatus.CREATED).body("/r/" + code);
    }

    @GetMapping("/r/{code}")
    public ResponseEntity<Void> redirect(@PathVariable String code) {
        String originalUrl = shortenerService.resolve(code);
        clickEventPublisher.publishClick(code); // fire-and-forget async event for analytics
        return ResponseEntity.status(HttpStatus.FOUND)
                .header(HttpHeaders.LOCATION, originalUrl)
                .build();
    }
}
```

### 15.6 Kafka Click Event Publisher

```java
package com.example.shortener.analytics;

import org.springframework.kafka.core.KafkaTemplate;
import org.springframework.stereotype.Component;

import java.time.Instant;

@Component
public class ClickEventPublisher {

    private static final String TOPIC = "url-click-events";

    private final KafkaTemplate<String, ClickEvent> kafkaTemplate;

    public ClickEventPublisher(KafkaTemplate<String, ClickEvent> kafkaTemplate) {
        this.kafkaTemplate = kafkaTemplate;
    }

    public void publishClick(String shortCode) {
        ClickEvent event = new ClickEvent(shortCode, Instant.now());
        // Async send — does not block the redirect response on Kafka latency.
        kafkaTemplate.send(TOPIC, shortCode, event);
    }

    public record ClickEvent(String shortCode, Instant clickedAt) {
    }
}
```

This design keeps the hot path (redirecting the user) fast by publishing analytics asynchronously instead of writing a synchronous database row on every click.

---

## 16. Interview Question Bank with Model Answers

### 16.1 Java Fundamentals

**Q: What is the difference between `==` and `.equals()`?**
`==` compares references for objects (whether two variables point to the same memory location) and values for primitives. `.equals()` performs logical/content comparison and can be overridden. For boxed types like `Integer`, `==` can appear to work for small cached values (-128 to 127) due to the integer cache, which is a common trap — always use `.equals()` for wrapper/object comparison.

**Q: Why are Strings immutable in Java?**
Immutability enables safe string pool sharing (many variables can reference the same literal without risk of one mutation affecting others), thread safety without synchronization, safe use as `HashMap` keys (hash code can be cached since it never changes), and security (e.g., class loader and file path arguments can't be mutated after validation).

**Q: How does `HashMap` work internally, and what changed in Java 8?**
Keys are hashed and spread across buckets in an array; a bucket holds a collision chain. Java 8 added treeification — when a single bucket's chain exceeds 8 entries (and the table has at least 64 buckets), it converts to a red-black tree, bounding worst-case lookup to O(log n) instead of O(n) under pathological hash collisions.

**Q: Explain checked vs unchecked exceptions and when to use each.**
Checked exceptions (subclasses of `Exception`, not `RuntimeException`) must be declared or caught — use them for recoverable conditions the caller is expected to handle (e.g., `IOException`). Unchecked exceptions (subclasses of `RuntimeException`) represent programming errors or conditions that usually cannot be meaningfully recovered from at the call site (e.g., `IllegalArgumentException`). Most modern Java backend code favors unchecked exceptions plus centralized handling (`@ControllerAdvice`) over checked exceptions, to avoid verbose try/catch chains.

**Q: What is the difference between `ArrayList` and `LinkedList`?**
`ArrayList` is backed by a resizable array — O(1) indexed access, O(n) insert/remove in the middle (requires shifting elements). `LinkedList` is a doubly linked list — O(1) insert/remove at known nodes (including the ends), but O(n) indexed access. In practice, `ArrayList` is preferred for most use cases because of better cache locality; `LinkedList` is rarely the right default choice.

### 16.2 Concurrency

**Q: What is a race condition, and how do you prevent one?**
A race condition occurs when the outcome of a program depends on the non-deterministic timing/interleaving of multiple threads accessing shared mutable state. Prevention: make shared state immutable, confine mutable state to a single thread, use `synchronized`/`Lock` to serialize access, or use atomic/concurrent data structures (`AtomicInteger`, `ConcurrentHashMap`).

**Q: How do you avoid deadlocks?**
Always acquire multiple locks in a globally consistent order across all code paths, use lock timeouts (`tryLock` with a timeout) instead of indefinite blocking, minimize the scope and duration of locked sections, and prefer higher-level concurrency utilities (`ExecutorService`, concurrent collections) over hand-rolled locking wherever possible.

**Q: When would you use `CompletableFuture` over a plain `Future`?**
`Future.get()` blocks and offers no composition. `CompletableFuture` supports non-blocking composition (`thenApply`, `thenCompose`, `thenCombine`), exception handling (`exceptionally`, `handle`), and fan-out/fan-in patterns (`allOf`, `anyOf`) — essential for orchestrating multiple downstream calls without blocking a thread per call.

### 16.3 Spring and Spring Boot

**Q: What is dependency injection and why does Spring favor constructor injection?**
Dependency injection means an object's collaborators are provided externally rather than constructed internally, decoupling components and enabling substitution (e.g., mocks in tests). Constructor injection is favored because it guarantees the object is always fully initialized (no partially-constructed state), makes dependencies explicit and immutable (`final` fields), and fails fast at startup if a required bean is missing — as opposed to field injection, which can hide missing dependencies until runtime.

**Q: How does Spring Boot auto-configuration work?**
Spring Boot scans `META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports` (or the legacy `spring.factories`) for `@Configuration` classes annotated with conditions like `@ConditionalOnClass`, `@ConditionalOnMissingBean`, and `@ConditionalOnProperty`. When you add a starter dependency (e.g., `spring-boot-starter-data-jpa`), the relevant classes become present on the classpath, satisfying `@ConditionalOnClass`, and Spring Boot auto-registers sensible default beans (a `DataSource`, an `EntityManagerFactory`) — which you can always override by defining your own bean of the same type.

**Q: Explain the difference between `@Component`, `@Service`, and `@Repository`.**
Functionally, all three make a class a Spring-managed bean via component scanning. They are semantically different: `@Service` signals business/service-layer logic, `@Repository` signals a persistence-layer bean and additionally enables automatic translation of persistence exceptions into Spring's `DataAccessException` hierarchy. `@Component` is the generic base stereotype. Using the specific annotation communicates intent and unlocks stereotype-specific behavior.

**Q: What is `@Transactional` and what are common mistakes with it?**
It wraps a method call in a database transaction via an AOP proxy. Common mistakes: calling an `@Transactional` method from another method in the *same* class (`this.method()`) bypasses the proxy entirely; marking a `private` method `@Transactional` has no effect (proxies can't override private methods); assuming it rolls back on checked exceptions by default (it only rolls back on unchecked exceptions unless `rollbackFor` is specified); and holding a transaction open across a slow external call, which needlessly extends lock duration.

**Q: How would you secure a REST API in Spring Boot?**
Use Spring Security with a stateless filter chain (`SessionCreationPolicy.STATELESS`), authenticate via JWT or OAuth2 bearer tokens validated in a custom filter or resource server configuration, enforce authorization with `hasRole`/`hasAuthority` on routes or `@PreAuthorize` on methods, validate all input with Bean Validation, and apply HTTPS, rate limiting, and CORS restrictions at the edge (gateway or filter level).

### 16.4 System Design and Backend Architecture

**Q: How do you design an idempotent API endpoint?**
The client supplies a unique idempotency key per logical operation (e.g., a UUID generated once per checkout attempt). The server persists the key alongside the operation's result. On a repeated request with the same key, the server returns the previously stored result instead of re-executing the operation — critical for payment/checkout flows where network retries must not cause duplicate charges.

**Q: How do you scale a backend service horizontally?**
Keep the service stateless (no in-memory session state; externalize session/cache to Redis), put it behind a load balancer, ensure the database or cache layer can handle increased connection counts (connection pooling, read replicas), and design for idempotency and retries since more instances mean more possible concurrent/duplicate requests.

**Q: How do you handle partial failures in a distributed system?**
Apply timeouts on every remote call, use retries with exponential backoff and jitter for transient failures, use a circuit breaker to stop calling a consistently failing downstream dependency, provide a fallback or degraded response where possible, and design workflows with compensating actions (saga pattern) instead of assuming a single ACID transaction can span multiple services.

**Q: How would you design a rate limiter?**
Common algorithms: fixed window (simple but allows bursts at window boundaries), sliding window log/counter (more accurate, more memory), and token bucket (allows controlled bursts while enforcing an average rate — usually the best general-purpose choice). Implement it centrally (e.g., in Redis with an atomic Lua script) so it works correctly across multiple service instances, not just in local memory.

**Q: How do you design a system for eventual consistency?**
Accept that different parts of the system may temporarily disagree, and design explicitly for it: use event-driven updates (publish a domain event when state changes; downstream services consume and update their own view), version records to detect stale writes, and communicate consistency guarantees clearly to API consumers instead of pretending strong consistency exists across service boundaries.

---

## Closing Notes on This Roadmap

This document intentionally favors **fewer, deeply explained topics with real, compilable code** over a long list of shallow one-line bullet points repeated many times. Depth is what actually gets tested in interviews and is what makes a resume project credible — a project with a correctly implemented idempotency key, a real saga-style compensation path, or a working Redis token-bucket rate limiter demonstrates far more engineering maturity than ten CRUD apps with only a `GET`/`POST`/`PUT`/`DELETE` controller and no edge-case handling.

Recommended way to use this file:

1. Read section 1-3 and write the small examples yourself, not just read them.
2. Read section 4-5 and build the minimal Spring Boot starter at the end of section 10.
3. Study section 11-12 until you can explain the JVM memory model and the Spring bean lifecycle without notes — these come up constantly in interviews.
4. Clone the structure of the three full projects (sections 13-15) into a real repository, run them locally against a real Postgres/Redis/Kafka instance (Docker Compose is a good way to spin these up locally), and extend them with your own features.
5. Use section 16 as a final review before interviews, but make sure every answer is backed by something you actually built, not just memorized.

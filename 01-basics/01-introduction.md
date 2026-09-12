# Introduction to Java

> **Section**: Basics  
> **Topic**: 01 — Introduction  
> **Last Updated**: 2026-09-12  
> **Status**: ✅ Complete

## 📌 What You'll Learn

- [What is Java?](#what-is-java)
- [Why is Java popular?](#why-is-java-so-popular)
- [Core features of Java](#javas-core-features)
- [Java Architecture](#java-architecture)
- [Where Java is used](#where-java-is-used)

---

## What is Java?

Java is a high-level, object-oriented, platform-independent programming language developed by James Gosling at Sun
Microsystems in 1995. It is now owned by Oracle Corporation.

**Key idea:** "Write Once, Run Anywhere" (WORA) — Java code compiled on one machine can run on any other machine that
has a Java Virtual Machine (JVM).

---

## Why Is Java So Popular?

- **Platform Independent**: Bytecode runs on any JVM — Windows, Mac, Linux.
- **Object-Oriented**: Everything is an object — reusable, modular code.
- **Robust**: Strong memory management, garbage collection, exception handling.
- **Secure**: No pointers, bytecode verification, security manager.
- **Multithreaded**: Built-in support for concurrent programming.
- **Huge Ecosystem**: Millions of libraries, frameworks, and tools.
- **Community**: One of the largest developer communities in the world.
- **Job Market**: Massive demand in enterprise, Android, backend, big data.

---

## Java's Core Features

### Platform Independence

- Java source code (`.java`) → compiled to bytecode (`.class`) → runs on JVM
- JVM is platform-specific, but bytecode is universal

### Object-Oriented Programming (OOP)

Four pillars:

- **Encapsulation** — bundling data + methods, hiding internals
- **Inheritance** — child class inherits from parent
- **Polymorphism** — one interface, many implementations
- **Abstraction** — hiding complexity, showing only essentials

### Automatic Memory Management

- Garbage Collector (GC) automatically frees unused memory
- No manual `free()` like C/C++

### Rich Standard Library

`java.lang`, `java.util`, `java.io`, `java.nio`, `java.net`, `java.sql`, `java.time`, etc.

### Multithreading

- Built-in `Thread` class and `java.util.concurrent` package
- Supports concurrent and parallel programming

---

## Java Architecture

| Term    | Full Form                | What It Is                                    |
|---------|--------------------------|-----------------------------------------------|
| **JVM** | Java Virtual Machine     | Runs bytecode                                 |
| **JRE** | Java Runtime Environment | JVM + libraries (to run Java apps)            |
| **JDK** | Java Development Kit     | JRE + compiler + tools (to develop Java apps) |

**Rule:** To **run** Java → JRE. To **develop** Java → JDK.

---

## Where Java Is Used

- **Enterprise Applications** — banking, insurance, e-commerce
- **Android Apps** — though Kotlin is now preferred
- **Web Backends** — Spring Boot is industry standard
- **Big Data** — Hadoop, Spark, Kafka
- **Cloud & Microservices** — AWS, Azure, GCP
- **Scientific & Research** — MATLAB, data analysis
- **Games** — Minecraft (Java Edition)
- **IoT & Embedded** — Java ME, Raspberry Pi

---

## 💡 Key Takeaways

- Java is platform-independent via JVM
- It's object-oriented and robust
- Used everywhere: enterprise, Android, backend, big data
- JDK = JRE + tools (for development)

---

[← Back to Basics Index](README.md) | [Next: Variables and data types →](02-variables-and-data-types.md)
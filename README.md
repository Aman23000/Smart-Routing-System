# Smart Routing System

Java implementation of the **Template Method Pattern** — generates fully customized emails for five distinct customer segments while sharing a single, consistent email structure.

[![Java](https://img.shields.io/badge/Java-11+-ED8B00?style=flat&logo=java)](https://adoptium.net/)
[![Maven](https://img.shields.io/badge/Maven-3.6+-C71A36?style=flat&logo=apachemaven)](https://maven.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Overview

Different customer types need different messaging, but the email generation flow is always the same: build subject → compose body → format footer. The **Template Method Pattern** defines that skeleton in an abstract base class and lets each customer subclass override only the parts that differ — no duplication, easy to extend.

## Design Pattern — Template Method

| Role | Class |
|---|---|
| Abstract template | `EmailTemplateBase` |
| Corporate clients | `CorporateClient` |
| Elite members | `EliteMember` |
| Loyal customers | `LoyalCustomer` |
| Prospective customers | `ProspectiveCustomer` |
| Returning clients | `ReturningClient` |

`EmailTemplateBase` calls `generateEmail()` which internally invokes `subjectLine()` and `messageBody()` — both abstract, overridden in each subclass.

## Project Structure

```
src/main/java/edu/bu/met/cs665/
├── Main.java
└── Models/
    ├── EmailTemplateBase.java   # Abstract template
    ├── CorporateClient.java
    ├── EliteMember.java
    ├── LoyalCustomer.java
    ├── ProspectiveCustomer.java
    └── ReturningClient.java
```

## Prerequisites

- Java 11+
- Maven 3.6+

## Build & Run

```bash
mvn clean package
java -jar target/*.jar
```

## Run Tests

```bash
mvn test
```
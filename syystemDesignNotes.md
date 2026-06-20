# ❄️ System Design

## 📖 Definition

* Process of designing software architecture and infrastructure.

## 🎯 Goals

* Scalability
* Reliability
* Availability
* Performance
* Maintainability

## 🧩 Main Components

* Client
* Server
* Database
* Cache
* Load Balancer
* Message Queue

## 📚 Types of System Design

### 1️⃣ HLD (High-Level Design)

* Overall architecture
* Components and communication

### 2️⃣ LLD (Low-Level Design)

* Classes
* Objects
* Design Patterns

> **💡 Remember:**
>
> System Design = Building software that works efficiently even when millions of users use it simultaneously.

---

# ❄️ Data Intensive Application

## 📖 Definition

A Data Intensive Application is a system whose primary challenge is handling large volumes of data reliably, efficiently, and at scale.

**Examples:** WhatsApp, Amazon, Netflix

## 🏗️ Typical Architecture

```text
Users
   |
Load Balancer
   |
Application Servers
   |
+--------+--------+
|                 |
Cache         Database
|                 |
+--------+--------+
         |
   Message Queue
         |
 Other Services
```

## ⚙️ Main Operations

* Data Storage
* Data Retrieval
* Data Processing
* Data Transfer

## ⭐ Characteristics

### Reliability

* Works correctly despite failures.

### Scalability

* Handles increasing traffic/load.

### Maintainability

* Easy to modify and maintain.

> **💡 Remember:**
>
> Data-intensive applications are all about efficiently managing data at scale.

---

# ❄️ Reliability

## 📖 Definition

Reliability is the ability of a system to continue functioning correctly and consistently even when faults occur.

### A Reliable System

* Produces correct results
* Handles failures gracefully
* Does not lose important data
* Continues serving users

## 🚗 Amazon Example

```text
User
  |
Load Balancer
  |
Server 1 ❌
Server 2 ✅
Server 3 ✅
```

Even if one server crashes, the order should still be processed.

## ⚠️ Fault vs Failure

### Fault

A problem inside the system.

**Examples**

* Hard disk failure
* Network issue
* Bug in code
* Database crash

### Failure

Users experience incorrect behavior.

**Examples**

* Website unavailable
* Wrong account balance
* Lost order
* Application crash

## 🔥 Types of Faults

### 1. Hardware Faults

**Examples**

* Hard disk crash
* RAM failure
* CPU failure

### 2. Software Faults

**Examples**

* Bugs
* Memory leaks
* Infinite loops
* Wrong business logic

### 3. Human Errors

**Examples**

* Wrong deployment
* Accidental database deletion
* Wrong configuration
* Incorrect DNS changes

## 🛠️ Techniques to Build Reliable Systems

### 1. Redundancy

* Never rely on a single component.

### 2. Replication

```text
Primary Database
      |
-----------------
|       |       |
Replica Replica Replica
```

**Benefits**

* High Availability
* Better Reliability

### 3. Monitoring

**Tools**

* Prometheus
* Grafana
* Datadog

### 4. Automated Recovery

```text
Server Crash
     |
Auto Restart
     |
Healthy Again
```

### 5. Backups

```text
Database Deleted
       |
Restore Backup
```

## 🎬 Netflix Example

Netflix assumes servers will fail and designs systems to survive failures.

**Chaos Monkey**

```text
Random Server Crash
       |
System Survives
```

If the system survives, it is reliable.

---

# ❄️ Scalability

## 📖 Definition

Scalability is the ability of a system to handle increasing load without significantly affecting performance.

> As users grow, the system should continue working efficiently.

## Example

### Small Scale

```text
Users
  |
Server
  |
Database
```

### Large Scale

```text
10 Million Users/Day
```

Problems:

* Slow response
* Database overload
* Server crashes
* Timeouts

Scalability helps solve these problems.

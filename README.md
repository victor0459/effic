# effic
A WeChat Official Account Backend Service Project (Java + SOA Distributed Architecture)

Project Introduction
effic is an enterprise-level backend service project for WeChat Official Account scenarios, designed with the SOA (Service-Oriented Architecture) paradigm. It aims to build a highly available, high-concurrency, and easily scalable backend service system for WeChat Official Accounts.
Core Objectives:
	·Provide stable backend support for health management-focused WeChat Official Accounts
	·Enable distributed service governance and flexible business expansion
	·Ensure service performance and data security in high-concurrency scenarios
Current Stage: Backend core module under active development, with basic common modules completed and ongoing iteration.

Tech Stack
Backend
	Technology	Purpose
	Java	Core development language
	SOA Architecture	Service-oriented distributed system design
	Dubbo	Service governance and RPC remote procedure calls
	Zookeeper	Service registration, discovery, and health check center
	Spring MVC	Web framework for handling HTTP requests
	Spring Security	Permission control and user authentication & authorization
	MySQL	Relational database for core business data storage
	MyBatis	ORM framework for database access encapsulation
	Lua	Performance optimization for high-concurrency business modules
	Git	Distributed version control system
Frontend
	Technology	Purpose
	Vue.js	Core frontend framework
	Element UI	UI component library for rapid page construction
	Bootstrap	Responsive layout framework
	Ajax	Asynchronous data interaction between frontend and backend
	Freemarker	Template engine for page staticization optimization

Project Architecture
Overall Architecture
This project adopts SOA (Service-Oriented Architecture), vertically splitting the system into independent services by business domain:
·Service Layer: Split by business domains (e.g., User Service, Message Service, Health Assessment Service)
·Registry Center: Zookeeper manages service registration, discovery, and health checks
·Service Invocation: Dubbo enables transparent RPC calls across services
·Data Layer: Unified MySQL + MyBatis persistence layer, supporting transactions and sharding
·Common Layer: Encapsulates universal utilities, data source connections, and common functions for reuse across all services
·High-Concurrency Optimization: Lua scripts are used to boost performance in core high-traffic business modules

Module Structure
```
Project Structure
-----------------
hea_parent/
├── hea_common/	# Common Module (Completed)
│   ├── pom.xml
│   └── src/
│       ├── constant/	
│       │   ├── MessageConstant.java
│       │   ├── Result.java
│       │   └── Rsp.java
│       ├── entity/	# Public entity classes
│       │   ├── PageResult.java
│       │   ├── QueryPageBean.java
│       │   └── Res.java
│       ├── exception/
│       │   └── HealthException.java
│       └── utils/	# Public utility classes (date, encryption, string processing, etc.)
│           ├── DateUtils.java
│           ├── POIUtils.java
│           └── ValidateCodeUtils.java
├── health_dao/	| Encapsulation of general data access layer
│   ├── pom.xml
│   └── src/
│       └── main/
│           ├── java/
│           │   └── com/
│           │       └── itvictor/
│           │           └── health/
│           │               └── dao/
│           │                   ├── CheckGroupDao.java
│           │                   ├── CheckItemDao.java
│           │                   ├── MemberDao.java
│           │                   ├── OrderDao.java
│           │                   ├── OrderSettingDao.java
│           │                   ├── SetmealDao.java
│           │                   └── UserDao.java
│           └── resources/
│               ├── applicationContext-dao.xml
│               ├── log4j.properties
│               ├── sqlMapConfig.xml
│               └── com/
│                   └── itvictor/
│                       └── health/
│                           └── dao/
│                               ├── CheckGroupDao.xml
│                               ├── CheckItemDao.xml
│                               ├── MemberDao.xml
│                               ├── OrderDao.xml
│                               ├── OrderSettingDao.xml
│                               ├── SetmealDao.xml
│                               └── UserDao.xml
├── health_interface/	# Business Service Layer (Under Development)
│   └── src/
│       └── main/
│           └── java/
│               └── com/
│                   └── itvictor/
│                       └── health/
│                           └── service/
│                               ├── CheckGroupService.java
│                               ├── CheckItemService.java
│                               ├── MemberService.java
│                               ├── OrderService.java
│                               ├── OrderSettingService.java
│                               ├── ReportService.java
│                               ├── SetmealService.java
│                               └── UserService.java
├── health_jobs/	# Configuration classes (data source, Dubbo, Zookeeper, etc.)
│   └── src/
│       └── main/
│           ├── java/
│           │   └── com/
│           │       └── itvictor/
│           │           └── health/
│           │               └── job/
│           │                   ├── CleanImgJob.java
│           │                   └── JobApplication.java
│           └── resources/
│               └── spring-jobs.xml
├── LICENSE
└── README.md
```

Current Development Progress
 Completed
 Overall project structure and SOA architecture design
 Development of the common module:
	·Database connection pool configuration and multi-data source support
	·Encapsulation of basic utility classes (date, encryption, validation, etc.)
	·MyBatis general Mapper and pagination plugin integration
	·Dubbo + Zookeeper service configuration
In Progress
 Implementation of business service modules (user, message, health management, etc.)
 WeChat Official Account message receiving and response interfaces
 Backend management pages and permission control
 Lua script optimization for high-concurrency business logic
To Do
 Frontend page implementation (Vue + Element UI)
 Page staticization with Freemarker
 API documentation and automated testing
 Service monitoring and log collection

Quick Start (Development Environment)
Note: The project is currently in the backend development stage, and no runnable demo is available yet. Below is a guide for setting up the development environment.
JDK 1.8+
MySQL 5.7+
Zookeeper 3.4+
Maven 3.6+

Project Features
	Distributed Architecture: SOA + Dubbo + Zookeeper, supporting horizontal service scaling
	High-Concurrency Optimization: Lua scripts for performance improvement in core business modules
	Security & Reliability: Fine-grained permission control via Spring Security
	Maintainability: Reusable common modules and clean code structure
	Frontend-Backend Separation: Vue.js + Freemarker for page staticization, improving access speed





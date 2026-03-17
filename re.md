# effic
A WeChat Official Account Backend Service Project (Java + SOA Distributed Architecture)

## Project Introduction
effic is an enterprise-level backend service project for WeChat Official Account scenarios, designed with the SOA (Service-Oriented Architecture) paradigm. It aims to build a highly available, high-concurrency, and easily scalable backend service system for WeChat Official Accounts.

Core Objectives:
- Provide stable backend support for health management-focused WeChat Official Accounts
- Enable distributed service governance and flexible business expansion
- Ensure service performance and data security in high-concurrency scenarios

Current Stage: Backend core module under active development, basic common modules completed, ongoing iteration.

## Tech Stack
### Backend
Java, SOA Architecture, Dubbo, Zookeeper, Spring MVC, Spring Security, MySQL, MyBatis, Lua, Git

### Frontend
Vue.js, Element UI, Bootstrap, Ajax, Freemarker

## Project Structure
hea_parent/
├── hea_common/ # Common Module (Completed)
│ ├── pom.xml
│ └── src/
│ ├── constant/
│ │ ├── MessageConstant.java
│ │ ├── Result.java
│ │ └── Rsp.java
│ ├── entity/
│ │ ├── PageResult.java
│ │ ├── QueryPageBean.java
│ │ └── Res.java
│ ├── exception/
│ │ └── HealthException.java
│ └── utils/
│ ├── DateUtils.java
│ ├── POIUtils.java
│ └── ValidateCodeUtils.java
│
├── health_dao/ # Data Access Layer
│ ├── pom.xml
│ └── src/
│ └── main/
│ ├── java/
│ │ └── com/itvictor/health/dao/
│ │ ├── CheckGroupDao.java
│ │ ├── CheckItemDao.java
│ │ ├── MemberDao.java
│ │ ├── OrderDao.java
│ │ ├── OrderSettingDao.java
│ │ ├── SetmealDao.java
│ │ └── UserDao.java
│ └── resources/
│ ├── applicationContext-dao.xml
│ ├── log4j.properties
│ ├── sqlMapConfig.xml
│ └── com/itvictor/health/dao/
│ ├── CheckGroupDao.xml
│ ├── CheckItemDao.xml
│ ├── MemberDao.xml
│ ├── OrderDao.xml
│ ├── OrderSettingDao.xml
│ ├── SetmealDao.xml
│ └── UserDao.xml
│
├── health_interface/ # Business Service Layer (Under Development)
│ └── src/
│ └── main/
│ └── java/
│ └── com/itvictor/health/service/
│ ├── CheckGroupService.java
│ ├── CheckItemService.java
│ ├── MemberService.java
│ ├── OrderService.java
│ ├── OrderSettingService.java
│ ├── ReportService.java
│ ├── SetmealService.java
│ └── UserService.java
│
├── health_jobs/ # Timing & Configuration Tasks
│ └── src/
│ └── main/
│ ├── java/
│ │ └── com/itvictor/health/job/
│ │ ├── CleanImgJob.java
│ │ └── JobApplication.java
│ └── resources/
│ └── spring-jobs.xml
│
├── LICENSE
└── README.md

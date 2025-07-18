# JeecgBoot Backend Technology Stack Summary (后端技术栈总结)

## Project Overview (项目概述)
JeecgBoot is an AI low-code platform based on BPM and code generators, adopting a front-end and back-end separation architecture, supporting microservices and multi-tenancy, and integrating AI large model capabilities.

**Current Version**: 3.7.4

## Core Technology Framework (核心技术框架)

### 1. Basic Framework (基础框架)
- **Java**: JDK 17 (supports JDK 8, JDK 21)
- **Spring Boot**: 2.7.18
- **Spring Framework**: Based on Spring Boot 2.7.18
- **Maven**: Dependency management tool

### 2. Microservices Architecture (微服务架构)
- **Spring Cloud**: 2021.0.8
- **Spring Cloud Alibaba**: 2021.0.6.2
- **Nacos**: 2.0.4 (Service registration & discovery, configuration center)
- **Gateway**: API gateway routing
- **Sentinel**: Circuit breaker, rate limiting
- **Seata**: 1.5.2 (Distributed transactions)
- **Feign**: Distributed HTTP calls

### 3. Data Persistence Layer (数据持久层)
- **MyBatis-Plus**: 3.5.3.2 (ORM framework)
- **Druid**: 1.2.24 (Database connection pool)
- **Dynamic DataSource**: 4.1.3 (Dynamic datasource, multi-datasource support)

### 4. Supported Databases (支持的数据库)
- **MySQL**: 5.7+ (Primary support, default scripts)
- **Oracle**: 11g
- **SQL Server**: 2017
- **PostgreSQL**: 42.2.25
- **MariaDB**
- **DM Database**: 8.1.1.49 (Domestic database)
- **KingbaseES**: 9.0.0 (Domestic database)
- **TiDB**
- **KingBase8**

### 5. Security Framework (安全框架)
- **Apache Shiro**: 1.13.0 (Permission control)
- **JWT**: 4.5.0 (JSON Web Token)
- **Shiro-Redis**: 3.2.3 (Shiro with Redis integration)

### 6. Caching Technology (缓存技术)
- **Redis**: 5.0 (Distributed cache, session management)

### 7. Web Server (Web 服务器)
- **Undertow**: High-performance web server replacing Tomcat
- **WebSocket**: Real-time communication support

### 8. Scheduled Tasks (定时任务)
- **Quartz**: Spring Boot integrated scheduled tasks
- **XXL-Job**: 2.4.1 (Distributed scheduled tasks)

### 9. Message Queue (消息队列)
- **RabbitMQ**: Message middleware
- **RocketMQ**: Alibaba Cloud message queue

### 10. File Storage (文件存储)
- **MinIO**: 8.0.3 (Distributed file storage)
- **Alibaba Cloud OSS**: 3.11.2 (Object storage service)
- **Qiniu Cloud**: 7.4.0 (Cloud storage)
- **Baidu Cloud**: 4.16.19 (Cloud storage)

### 11. AI Large Model Integration (AI 大模型集成)
- **ChatGPT**: OpenAI large language model
- **DeepSeek**: Default large model
- **Ollama**: Local private large model support

### 12. Reporting Tools (报表工具)
- **JimuReport**: 1.9.5 (Building block reports, supports printing, data reports, graphic reports)

### 13. Code Generator (代码生成器)
- **CodeGenerate**: 1.4.9 (One-click generation of front-end and back-end code)

### 14. Documentation and API (文档和接口)
- **Knife4j**: 4.4.0 (Enhanced Swagger UI, online API documentation)
- **OpenAPI 2.0**: API documentation specification

### 15. Excel Processing (Excel 处理)
- **AutoPoi**: 1.4.11 (Excel import/export tools)

### 16. Utility Libraries (工具类库)
- **Hutool**: 5.8.25 (Java utility library)
- **FastJSON**: 2.0.56 (JSON processing)
- **Commons IO**: 2.11.0
- **Commons Lang**: 2.6
- **Lombok**: Simplifies Java code

### 17. Third-party Integration (第三方集成)
- **JustAuth**: 1.4.0 (Third-party login)
- **Alibaba Cloud SMS**: 2.1.0 (SMS service)
- **Aviator**: 5.2.6 (Expression engine)

### 18. Monitoring and Operations (监控和运维)
- **Spring Boot Actuator**: Application monitoring
- **Spring Boot Admin**: Service monitoring
- **Skywalking**: Distributed tracing
- **Micrometer**: Monitoring metrics
- **Prometheus**: Monitoring metrics collection
- **Loki + Grafana**: Lightweight distributed logging

### 19. Containerized Deployment (容器化部署)
- **Docker**: Containerized deployment
- **Docker Compose**: Service orchestration
- **Kubernetes**: Container orchestration support
- **Jenkins**: CI/CD continuous integration

### 20. Logging System (日志系统)
- **Logback**: 1.2.13 (Logging framework)
- **Log4j2**: 2.17.0 (Alternative logging framework)

### 21. Other Technologies (其他技术)
- **Markdown**: 0.17.0 (Markdown parsing)
- **Freemarker**: Template engine
- **Quartz**: Scheduled task scheduling
- **Validation**: Parameter validation
- **AOP**: Aspect-oriented programming
- **Mail**: Email sending functionality

## Architecture Features (架构特点)

### Modular Design (分模块设计)
```
jeecg-boot-parent (Parent project)
├── jeecg-boot-base-core (Core base module)
├── jeecg-module-system (System management module)
├── jeecg-module-demo (Demo module)
└── jeecg-server-cloud (Microservices module)
    ├── jeecg-cloud-nacos (Nacos service)
    ├── jeecg-cloud-gateway (Gateway service)
    ├── jeecg-system-cloud-start (System microservice startup)
    └── jeecg-visual (Visual monitoring)
```

### Microservices Capabilities (微服务能力)
- Service registration and discovery (Nacos)
- Unified configuration center (Nacos)
- API gateway routing (Gateway)
- Distributed calls (Feign)
- Circuit breaker and rate limiting (Sentinel)
- Distributed file storage (MinIO/OSS)
- Unified permission control (JWT + Shiro)
- Service monitoring (Spring Boot Admin)
- Distributed tracing (Skywalking)
- Message middleware (RabbitMQ/RocketMQ)
- Distributed tasks (XXL-Job)
- Distributed transactions (Seata)

### AI Capabilities (AI 能力)
- AI chat assistant
- AI table creation
- AI article writing
- AI workflow orchestration (in development)
- AI knowledge base Q&A (in development)
- RAG (Retrieval-Augmented Generation)

### Low-Code Capabilities (低代码能力)
- Online form development
- Code generator (one-click generation of front-end and back-end code)
- Online report design
- Dashboard designer
- Workflow engine
- Form designer

## Database Scripts (数据库脚本)
- **Main database**: jeecgboot-mysql-5.7.sql (5.5MB)
- **Nacos configuration**: tables_nacos.sql
- **XXL-Job**: tables_xxl_job.sql

## Deployment Methods (部署方式)
1. **Traditional deployment**: Direct IDE startup
2. **Docker standalone**: docker-compose.yml
3. **Docker microservices**: docker-compose-cloud.yml
4. **Kubernetes**: K8s deployment support
5. **Jenkins**: CI/CD automated deployment

This technology stack represents the best practices of modern enterprise-level Java application development, integrating cutting-edge technologies such as microservices, AI, and low-code development, suitable for various enterprise application scenarios.

---

*This document provides a comprehensive overview of all backend technologies used in the JeecgBoot project, making it suitable for enterprise-level application development with modern technology stacks.*
# mall 微服务商城

基于 Spring Cloud Alibaba 的微服务商城系统，包含后台管理、商品搜索、商城门户等能力，采用 Nacos 作为注册与配置中心。

## 模块结构

| 模块 | 端口 | 说明 |
|------|------|------|
| mall-auth | 8401 | 认证中心 |
| mall-gateway | 8201 | API 网关（统一入口） |
| mall-admin | 8080 | 后台管理 |
| mall-search | 8081 | 搜索服务（Elasticsearch） |
| mall-portal | 8085 | 商城门户 |
| mall-monitor | 8101 | 服务监控（Spring Boot Admin） |
| mall-demo | 8082 | 示例模块 |

## 技术栈

- Spring Boot 3.5 / Spring Cloud 2025 / Spring Cloud Alibaba 2025
- Sa-Token 认证授权
- MyBatis + MySQL 5.7
- Elasticsearch 7.17
- Redis / RabbitMQ / MongoDB / MinIO
- Nacos 注册与配置中心

## 快速开始

完整本地启动步骤见 [本地启动说明.md](本地启动说明.md)。

1. 启动中间件：`docker compose -f docker-compose-env-local.yml up -d`
2. 导入数据库：`mysql -h127.0.0.1 -P3307 -uroot -proot mall < sql/mall.sql`
3. 发布 Nacos 配置（见本地启动说明第五节）
4. 构建：`mvn install -DskipTests -Ddocker.skip=true`
5. 启动 6 个微服务

## 环境要求

- JDK 21（编译目标 17）
- Maven 3.9+
- Docker Desktop + WSL2
- MySQL 5.7 / Redis / RabbitMQ / Elasticsearch 7.17 / MongoDB / MinIO / Nacos 2.1.0

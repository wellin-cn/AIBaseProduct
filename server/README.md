# 服务端项目

这是多项目结构中的服务端项目目录。

## 目录结构

```
server/
├── knowledge/              # 服务端知识库
│   ├── features/
│   │   ├── doing/         # 进行中的功能
│   │   └── done/          # 已完成的功能
│   ├── architecture/      # 架构设计文档
│   ├── apis/              # API设计文档
│   └── database/          # 数据库设计文档
├── ai-dev-templates/      # AI开发模板（软连接到shared）
└── examples/              # 示例文件（软连接到shared）
```

## AI开发工作流

### 1. 创建服务端功能PRD

```text
使用 @ai-dev-templates/create-server-prd.md
我想构建的服务端功能是：[详细描述您的API和业务逻辑需求]
```

如果是更通用的功能，也可以使用：
```text
使用 @ai-dev-templates/create-prd.md
```

### 2. 生成服务端任务列表

```text
现在取 @knowledge/features/doing/server-prd-[功能名称].md 
并使用 @ai-dev-templates/generate-server-tasks.md 创建任务
```

### 3. 执行开发任务

```text
请从任务1.1开始，使用 @ai-dev-templates/process-task-list.md
```

## 推荐的工作流程

1. **需求分析**: 在knowledge/features/doing/目录下创建PRD
2. **任务规划**: 生成详细的服务端开发任务列表
3. **开发实现**: 按任务列表逐步实现
4. **测试验证**: 包含单元测试、集成测试、API测试
5. **部署上线**: 容器化部署和CI/CD配置
6. **归档管理**: 完成后移至knowledge/features/done/

## 服务端开发重点

- **API设计**: RESTful API设计，统一响应格式
- **数据模型**: 数据库设计，ORM模型定义
- **业务逻辑**: 服务层业务规则实现
- **认证授权**: JWT认证，RBAC权限控制
- **性能优化**: 缓存策略，数据库优化
- **监控运维**: 日志记录，性能监控，错误告警

## 技术栈建议

- **框架**: Express.js / Koa.js / NestJS (Node.js) 或 FastAPI (Python)
- **数据库**: PostgreSQL / MySQL / MongoDB
- **缓存**: Redis
- **消息队列**: Redis Queue / RabbitMQ
- **监控**: Winston (日志) + Prometheus (监控)
- **部署**: Docker + Kubernetes / Docker Compose
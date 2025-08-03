# 共享AI开发工作流

这个shared目录包含了服务端和客户端项目共享的AI开发工作流模板和示例。

## 目录结构

```
shared/
├── ai-dev-templates/          # AI开发工作流模板
│   ├── create-prd.md         # 通用PRD创建指南
│   ├── create-server-prd.md  # 服务端PRD创建指南
│   ├── create-client-prd.md  # 客户端PRD创建指南
│   ├── generate-tasks.md     # 通用任务生成指南
│   ├── generate-server-tasks.md  # 服务端任务生成指南
│   ├── generate-client-tasks.md  # 客户端任务生成指南
│   └── process-task-list.md  # 任务处理执行指南
└── examples/                 # 示例文件
    ├── example-user-login-prd.md
    └── example-user-login-tasks.md
```

## 模板说明

### 通用模板
- **create-prd.md**: 适用于所有类型功能的PRD创建指南
- **generate-tasks.md**: 通用的任务列表生成指南
- **process-task-list.md**: 任务执行和管理指南

### 服务端专用模板
- **create-server-prd.md**: 专为后端API、数据库、业务逻辑设计的PRD模板
- **generate-server-tasks.md**: 专为服务端开发流程设计的任务生成模板

### 客户端专用模板
- **create-client-prd.md**: 专为前端UI/UX、用户交互设计的PRD模板
- **generate-client-tasks.md**: 专为客户端开发流程设计的任务生成模板

## 使用方式

这些模板通过软连接的方式被server和client项目引用：

```
server/ai-dev-templates -> ../shared/ai-dev-templates
client/ai-dev-templates -> ../shared/ai-dev-templates
server/examples -> ../shared/examples
client/examples -> ../shared/examples
```

这样可以确保：
1. 所有项目使用统一的工作流模板
2. 模板更新时自动同步到所有项目
3. 避免重复维护多份相同的文件

## 更新模板

当需要更新AI开发工作流模板时，只需修改shared目录中的文件，所有项目将自动获得更新。
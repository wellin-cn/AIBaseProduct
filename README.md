# 🚀 AI开发任务工作流 - 多项目版 🤖

欢迎使用 **多项目AI开发任务工作流**！这个工具库提供了一套结构化的markdown文件，专为配合AI驱动的IDE和CLI工具进行**服务端和客户端**协同开发而设计。最初为 [Cursor](https://cursor.sh/) 构建，同样适用于Claude Code、Windsurf等任何AI编程助手。通过使用这些结构化提示，您可以系统性地处理前后端功能构建，从想法到实现，并内置验证检查点。

🆕 **多项目特色**：
- 🔄 **前后端协同**：专门的服务端和客户端开发模板
- 🔗 **共享模板**：通过软连接实现模板统一管理
- 📋 **分工明确**：前端专注UI/UX，后端专注API/数据库
- 🏗️ **架构清晰**：支持微服务和分布式开发模式

让我们告别混乱的巨大AI请求，开始逐步引导您的AI协作伙伴进行专业的前后端开发！

## ✨ 核心理念

与您的"开发者角色转变"理念相呼应，这个工作流将开发者定位为**知识架构师**和**AI协调者**，而非传统的代码编写者。通过以下方式为复杂功能开发带来结构、清晰度和控制：

1. **定义范围：** 通过产品需求文档(PRD)清晰描述要构建的内容
2. **详细规划：** 将PRD分解为细致、可操作的任务列表
3. **迭代实现：** 引导AI逐个处理任务，允许您审查和批准每项更改

这种结构化方法确保AI始终在正轨上，简化问题调试，并增强您对生成代码的信心。

## 多项目工作流程：前后端协同开发 💡➡️💻

以下是针对**服务端**和**客户端**分别进行开发的工作流程：

## 📁 项目结构

```
aiProgrammer/
├── shared/                    # 共享的AI开发模板和示例
│   ├── ai-dev-templates/     # 所有项目共享的开发模板
│   └── examples/             # 示例文件
├── server/                   # 服务端项目
│   ├── knowledge/            # 服务端知识库
│   ├── ai-dev-templates/     # 软连接到 shared/ai-dev-templates
│   └── examples/             # 软连接到 shared/examples
├── client/                   # 客户端项目
│   ├── knowledge/            # 客户端知识库
│   ├── ai-dev-templates/     # 软连接到 shared/ai-dev-templates
│   └── examples/             # 软连接到 shared/examples
├── README.md                 # 总体项目说明
└── aiProgramer.md           # 开发者角色转变理念文档
```

## 🔄 服务端开发工作流

### 1️⃣ 创建服务端PRD

根据功能复杂度选择合适的模板：

**专业服务端功能**（推荐）：
```text
使用 @server/ai-dev-templates/create-server-prd.md
我想构建的服务端功能是：[详细描述API、数据库、业务逻辑需求]
```

**通用功能**：
```text
使用 @server/ai-dev-templates/create-prd.md
我想构建的功能是：[详细描述您的功能]
```

### 2️⃣ 生成服务端任务列表

```text
现在取 @server/knowledge/features/doing/server-prd-[功能名称].md 
并使用 @server/ai-dev-templates/generate-server-tasks.md 创建任务
```

### 3️⃣ 执行服务端开发

```text
请从任务1.1开始，使用 @server/ai-dev-templates/process-task-list.md
```

## 🎨 客户端开发工作流

### 1️⃣ 创建客户端PRD

根据功能复杂度选择合适的模板：

**专业客户端功能**（推荐）：
```text
使用 @client/ai-dev-templates/create-client-prd.md
我想构建的客户端功能是：[详细描述UI/UX、用户交互、响应式设计需求]
```

**通用功能**：
```text
使用 @client/ai-dev-templates/create-prd.md
我想构建的功能是：[详细描述您的功能]
```

### 2️⃣ 生成客户端任务列表

```text
现在取 @client/knowledge/features/doing/client-prd-[功能名称].md 
并使用 @client/ai-dev-templates/generate-client-tasks.md 创建任务
```

### 3️⃣ 执行客户端开发

```text
请从任务1.1开始，使用 @client/ai-dev-templates/process-task-list.md
```

## 🔄 协同开发建议

### 并行开发策略
1. **API优先设计**：服务端先设计API接口，客户端据此开发
2. **Mock数据开发**：客户端使用Mock数据先行开发UI
3. **渐进集成**：逐步用真实API替换Mock数据
4. **联调测试**：前后端集成测试和端到端测试

### 任务协调
- 服务端专注：数据库设计 → API开发 → 业务逻辑 → 性能优化
- 客户端专注：设计系统 → 组件开发 → 页面实现 → 用户体验优化

### 沟通机制
- 共享API文档和数据格式约定
- 定期进行前后端联调会议
- 使用统一的错误码和响应格式

## 🗂️ 共享模板文件

### 通用模板 (`shared/ai-dev-templates/`)
* **`create-prd.md`**：通用PRD创建指导，适用于所有类型的功能
* **`generate-tasks.md`**：通用任务列表生成指导
* **`process-task-list.md`**：任务处理和执行指导（所有项目通用）

### 服务端专用模板
* **`create-server-prd.md`**：专为后端API、数据库、业务逻辑设计的PRD模板
* **`generate-server-tasks.md`**：专为服务端开发流程设计的任务生成模板

### 客户端专用模板  
* **`create-client-prd.md`**：专为前端UI/UX、用户交互设计的PRD模板
* **`generate-client-tasks.md`**：专为客户端开发流程设计的任务生成模板

### 软连接机制
所有模板通过软连接方式在server和client项目中可用：
- `server/ai-dev-templates` → `../shared/ai-dev-templates`
- `client/ai-dev-templates` → `../shared/ai-dev-templates`

这确保了：
✅ 所有项目使用统一的工作流模板  
✅ 模板更新时自动同步到所有项目  
✅ 避免重复维护多份相同的文件

## 🌟 优势

* **结构化开发：** 从想法到代码强制执行清晰流程
* **分步验证：** 允许您在每个小步骤审查和批准AI生成的代码，确保质量和控制
* **管理复杂性：** 将大型功能分解为AI的较小、易消化任务，减少迷失或生成过于复杂、错误代码的机会
* **提高可靠性：** 相比单一大型提示，为重要开发工作提供更可靠的AI利用方法
* **清晰进度跟踪：** 提供已完成任务的可视化表示，便于查看已完成多少和接下来做什么
* **知识沉淀：** 符合"知识库管理者"理念，整个过程生成的PRD和任务列表都是宝贵的项目知识资产

## 🛠️ 使用方法

1. **克隆或下载：** 将这些 `.md` 文件放入您的项目或AI工具可访问的中央位置
2. **遵循工作流：** 在AI助手中系统性地使用上述工作流中描述的 `.md` 文件
3. **适应和迭代：**
    * 随意修改 `.md` 文件中的提示以更好地适应您的特定需求或编码风格
    * 如果AI在任务上遇到困难，尝试重新表述您的初始功能描述或进一步分解任务

## 工具特定说明

### Cursor

Cursor用户可以按照上述工作流，直接在Agent聊天中使用 `.md` 文件：

1. 确保可以访问本仓库中的文件
2. 在Cursor的Agent聊天中，使用 `@` 引用文件（例如：`@create-prd.md`）
3. 按照上述5步工作流
4. **PRD的MAX模式：** 如果预算支持，在Cursor中使用MAX模式创建PRD可以产生更全面的结果

### Claude Code

要在Claude Code中使用这些工具：

1. **将文件复制到您的仓库**：将三个 `.md` 文件复制到项目的子目录（例如：`/ai-dev-tasks`）

2. **在CLAUDE.md中引用**：将这些行添加到项目的 `./CLAUDE.md` 文件：
   ```
   # AI开发任务
   当我请求使用PRD进行结构化功能开发时使用这些文件：
   /ai-dev-tasks/create-prd.md
   /ai-dev-tasks/generate-tasks.md
   /ai-dev-tasks/process-task-list.md
   ```

3. **创建自定义命令**（可选）：为便于访问，在 `.claude/commands/` 中创建这些文件：
   - `.claude/commands/create-prd.md` 内容：
     ```
     请使用 /ai-dev-tasks/create-prd.md 中的结构化工作流帮助我为新功能创建PRD。
     ```
   - `.claude/commands/generate-tasks.md` 内容：
     ```
     请使用 /ai-dev-tasks/generate-tasks.md 从PRD生成任务
     如果没有明确告诉我使用哪个PRD，生成PRD列表并要求用户从 `/tasks` 下选择一个或使用 `create-prd.md` 创建新的：
     - 假设它存储在 `/tasks` 下并且文件名以 `prd-` 开头（例如：`prd-[名称].md`）
     - 它在 `/tasks` 中不应该已经有相应的任务列表（例如：`tasks-prd-[名称].md`）
     - **总是** 在继续之前要求用户确认PRD文件名
     确保以数字列表提供选项，这样我可以轻松回应（如果有多个选项）。
     ```
   - `.claude/commands/process-task-list.md` 内容：
     ```
     请使用 /ai-dev-tasks/process-task-list.md 处理任务列表
     ```

   添加这些文件后确保重启Claude Code (`/exit`)。
   然后使用像 `/create-prd` 这样的命令快速启动工作流。

### 其他工具

对于其他AI驱动的IDE或CLI：

1. 将 `.md` 文件复制到您的项目
2. 根据您工具的文档引用它们
3. 遵循相同的工作流原则

## 💡 成功秘诀

* **具体明确：** 您提供的上下文和明确指令越多（在初始功能描述和任何澄清中），AI的输出就越好
* **使用强大模型：** Cursor的免费版本目前使用较弱的AI模型，通常难以遵循此工作流中的结构化指令。为获得最佳结果，考虑升级到Pro计划以确保一致、准确的任务执行
* **PRD的MAX模式：** 如前所述，如果预算支持，在Cursor中使用MAX模式创建PRD (`create-prd.md`) 可以产生更全面和更高质量的结果
* **正确的文件标记：** 在生成任务时始终确保准确标记PRD文件名（例如：`@my-feature-prd.md`）
* **耐心和迭代：** AI是强大的工具，但不是魔法。准备好引导、纠正和迭代。此工作流旨在使迭代过程更顺畅

## 与"AI编程工具与开发者角色转变"的结合

这个工作流完美契合您提出的"知识库管理者"理念：

### 知识沉淀
- 每个PRD都成为项目knowledge目录下的永久资产
- 任务列表记录了实现的详细步骤
- 整个过程产生的文档是AI可读的结构化知识

### 推荐的多项目目录结构
```
aiProgrammer/
├── shared/                          # 共享模板和示例
│   ├── ai-dev-templates/
│   │   ├── create-prd.md
│   │   ├── create-server-prd.md
│   │   ├── create-client-prd.md
│   │   ├── generate-tasks.md
│   │   ├── generate-server-tasks.md
│   │   ├── generate-client-tasks.md
│   │   └── process-task-list.md
│   └── examples/
├── server/                          # 服务端项目
│   ├── knowledge/
│   │   ├── features/
│   │   │   ├── done/
│   │   │   │   └── 20250315-user-auth-api/
│   │   │   │       ├── server-prd-user-auth-api.md
│   │   │   │       ├── server-tasks-user-auth-api.md
│   │   │   │       └── api-documentation.md
│   │   │   └── doing/
│   │   │       └── 20250320-payment-service/
│   │   │           ├── server-prd-payment-service.md
│   │   │           └── server-tasks-payment-service.md
│   │   ├── architecture/
│   │   ├── apis/
│   │   └── database/
│   ├── ai-dev-templates/            # 软连接到 shared
│   └── examples/                    # 软连接到 shared
├── client/                          # 客户端项目
│   ├── knowledge/
│   │   ├── features/
│   │   │   ├── done/
│   │   │   │   └── 20250315-user-login-ui/
│   │   │   │       ├── client-prd-user-login-ui.md
│   │   │   │       ├── client-tasks-user-login-ui.md
│   │   │   │       └── design-specs.md
│   │   │   └── doing/
│   │   │       └── 20250320-dashboard-redesign/
│   │   │           ├── client-prd-dashboard-redesign.md
│   │   │           └── client-tasks-dashboard-redesign.md
│   │   ├── design-system/
│   │   ├── components/
│   │   └── user-flows/
│   ├── ai-dev-templates/            # 软连接到 shared
│   └── examples/                    # 软连接到 shared
└── aiProgramer.md                   # 开发者角色转变理念
```

### 多项目工作流整合

#### 服务端开发流程
1. **需求阶段**：使用`create-server-prd.md`在server/knowledge目录下生成API和后端逻辑PRD
2. **规划阶段**：使用`generate-server-tasks.md`将PRD转化为后端开发任务
3. **实现阶段**：使用`process-task-list.md`让AI逐步实现后端功能
4. **归档阶段**：完成后将所有文档移至server/knowledge/features/done/

#### 客户端开发流程  
1. **需求阶段**：使用`create-client-prd.md`在client/knowledge目录下生成UI/UX设计PRD
2. **规划阶段**：使用`generate-client-tasks.md`将PRD转化为前端开发任务
3. **实现阶段**：使用`process-task-list.md`让AI逐步实现前端功能
4. **归档阶段**：完成后将所有文档移至client/knowledge/features/done/

#### 协同开发优势
- **职责分明**：后端专注数据和逻辑，前端专注界面和体验
- **并行开发**：前后端可以同时进行开发，提高效率
- **知识专业化**：不同类型的知识分别管理，更加专业化
- **AI角色细分**：AI可以根据不同项目类型提供更专业的实现

这样，开发者真正成为了**分工明确的知识架构师**，AI成为了**专业的代码实现者**。

## 🤝 贡献

有改进这些 `.md` 文件的想法或有适合此工作流的新文件吗？欢迎贡献！

请随时：

* 开启issue讨论更改或建议新功能
* 提交pull request并提供您的增强功能

---

祝AI辅助开发愉快！让我们一起迎接开发者角色转变的新时代！ 🚀

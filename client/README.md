# 客户端项目

这是多项目结构中的客户端项目目录。

## 目录结构

```
client/
├── knowledge/              # 客户端知识库
│   ├── features/
│   │   ├── doing/         # 进行中的功能
│   │   └── done/          # 已完成的功能
│   ├── design-system/     # 设计系统文档
│   ├── components/        # 组件设计文档
│   └── user-flows/        # 用户流程文档
├── ai-dev-templates/      # AI开发模板（软连接到shared）
└── examples/              # 示例文件（软连接到shared）
```

## AI开发工作流

### 1. 创建客户端功能PRD

```text
使用 @ai-dev-templates/create-client-prd.md
我想构建的客户端功能是：[详细描述您的UI/UX和用户交互需求]
```

如果是更通用的功能，也可以使用：
```text
使用 @ai-dev-templates/create-prd.md
```

### 2. 生成客户端任务列表

```text
现在取 @knowledge/features/doing/client-prd-[功能名称].md 
并使用 @ai-dev-templates/generate-client-tasks.md 创建任务
```

### 3. 执行开发任务

```text
请从任务1.1开始，使用 @ai-dev-templates/process-task-list.md
```

## 推荐的工作流程

1. **需求分析**: 在knowledge/features/doing/目录下创建PRD
2. **设计规划**: 生成详细的客户端开发任务列表
3. **开发实现**: 按任务列表逐步实现
4. **测试验证**: 包含单元测试、集成测试、E2E测试
5. **部署上线**: 构建优化和CI/CD配置
6. **归档管理**: 完成后移至knowledge/features/done/

## 客户端开发重点

- **设计系统**: Design Token，组件库，主题系统
- **用户体验**: 交互设计，动画效果，加载状态
- **响应式设计**: 移动端适配，跨设备兼容
- **性能优化**: 代码分割，懒加载，缓存策略
- **可访问性**: 语义化HTML，键盘导航，屏幕阅读器
- **状态管理**: 全局状态，数据流，API集成

## 技术栈建议

- **框架**: React / Vue.js / Angular
- **语言**: TypeScript
- **状态管理**: Redux / Zustand / Vuex / Pinia
- **UI库**: Ant Design / Material-UI / Element Plus (可选)
- **样式方案**: CSS Modules / Styled Components / Tailwind CSS
- **构建工具**: Vite / Webpack / Create React App
- **测试**: Jest + Testing Library + Cypress
- **部署**: Vercel / Netlify / Nginx
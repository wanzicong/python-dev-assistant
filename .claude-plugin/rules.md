# Python 开发助手插件规则

## 何时使用此插件

当用户进行以下操作时，主动使用此插件的功能：

### 代码质量相关
- 用户编写或修改 Python 代码后，建议运行 `/py-check` 检查代码质量
- 用户询问代码规范、PEP 8、代码风格时，激活 `python-best-practices` 技能
- 用户要求代码审查、分析代码质量时，使用 `python-code-analyzer` 代理
- 用户保存 Python 文件时，自动触发 Hook 进行代码检查

### 项目创建相关
- 用户说"创建 Django 项目"、"新建 Flask 应用"时，使用相应的命令
- 用户询问 Django/Flask 项目结构时，激活 `django-flask-architecture` 技能
- 用户需要项目脚手架时，推荐使用 `/py-django` 或 `/py-flask`

### 文档相关
- 用户询问如何写文档、docstring 时，激活 `python-documentation` 技能
- 用户需要生成 API 文档时，使用 `/py-docs` 命令
- 用户编写函数/类但缺少文档时，建议添加 docstring

### 代码片段相关
- 用户需要创建类、装饰器、测试等常见结构时，推荐 `/py-snippet`
- 用户询问"如何写单元测试"、"如何创建装饰器"时，提供片段

## 工作流程建议

### 新项目开发流程
1. 使用 `/py-django` 或 `/py-flask` 创建项目
2. 编写代码时参考 `python-best-practices` 技能
3. 定期运行 `/py-check` 检查代码质量
4. 完成功能后使用 `python-code-analyzer` 全面审查
5. 使用 `/py-docs` 生成项目文档

### 代码审查流程
1. 用户完成代码编写
2. 自动触发 Hook 进行基础检查
3. 运行 `/py-check --fix` 自动修复风格问题
4. 使用 `python-code-analyzer` 代理进行深度分析
5. 根据分析报告改进代码

### 学习 Python 最佳实践
1. 用户询问 Python 相关问题时，优先激活相关技能
2. 提供具体的代码示例和参考文档
3. 推荐使用 `/py-snippet` 学习常见代码模式

## 主动建议时机

### 代码质量问题
当检测到以下情况时，主动建议使用插件功能：
- 代码缺少文档字符串 → 建议查看 `python-documentation` 技能
- 代码风格不规范 → 建议运行 `/py-check --fix`
- 代码复杂度过高 → 建议使用 `python-code-analyzer` 分析
- 缺少类型注解 → 建议参考 `python-best-practices` 技能

### 项目结构问题
- 项目结构混乱 → 建议参考 `django-flask-architecture` 技能
- 需要快速原型 → 建议使用 `/py-django` 或 `/py-flask`

### 文档问题
- 项目缺少文档 → 建议使用 `/py-docs` 生成
- 不知道如何写文档 → 激活 `python-documentation` 技能

## 不要使用此插件的情况

- 用户在处理非 Python 代码时
- 用户明确表示不需要代码检查时
- 用户在进行快速实验/原型时（除非明确要求）

## 配置优先级

1. 命令行参数（最高优先级）
2. 用户配置文件 `.claude/python-dev-assistant.local.md`
3. 插件默认配置（最低优先级）

## 错误处理原则

- 工具未安装时，提供清晰的安装指南
- 配置错误时，提供示例配置
- 操作失败时，提供替代方案
- 始终保持友好和建设性的语气

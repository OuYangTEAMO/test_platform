# 测试平台 Test Platform

一个基于 Flask 的测试管理平台，支持测试用例管理、缺陷跟踪、AI 生成测试用例等功能。

## 功能特性

### 1. 用例管理
- 左侧分类列表（支持创建/选择分类）
- 右侧用例列表（支持搜索、筛选）
- 批量选择添加分类
- 导出 Excel（文件名以模块名称命名）
- 用例字段：名称、模块、类型、优先级、前置条件、测试步骤、预期结果、状态

### 2. AI 生成
- 上传需求文档或输入文本
- AI 自动生成 40+ 条测试用例
- 支持选择/创建分类后批量保存
- 基于 MiniMax API 实现

### 3. 缺陷管理
- 缺陷的提交、编辑、跟踪
- 按状态/严重程度统计
- 缺陷字段：标题、严重程度、优先级、状态、描述、复现步骤

### 4. 版本管理
- 版本创建、编辑、删除
- 用例按模块分组展示
- 模块折叠/展开功能
- 表格形式分配用例
- AJAX 无刷新移除用例

### 5. 测试计划
- 创建测试计划
- 关联测试用例
- 跟踪执行结果

## 技术栈

- **后端**：Flask + SQLAlchemy
- **数据库**：SQLite
- **前端**：HTML + CSS（黑金色调）
- **AI**：MiniMax API

## 快速启动

### 1. 安装依赖

```bash
cd D:\project\test_platform
pip install -r requirements.txt
```

### 2. 启动服务

```bash
python run.py
```

### 3. 访问平台

打开浏览器访问：http://127.0.0.1:5001

### 4. 登录账号

- 用户名：`admin`
- 密码：`123456`

## 项目结构

```
test_platform/
├── test_platform/
│   ├── auth/          # 认证模块
│   ├── bug/           # 缺陷管理
│   ├── main/          # 主页面
│   ├── models/        # 数据模型
│   ├── plan/          # 版本管理
│   ├── testcase/      # 用例管理
│   ├── static/
│   │   └── templates/ # HTML 模板
│   ├── config.py      # 配置文件
│   └── parser.py      # 文档解析
├── config.yaml        # 应用配置
├── requirements.txt   # 依赖列表
└── run.py            # 启动入口
```

## 配置说明

在 `config.yaml` 中配置 MiniMax API：

```yaml
minimax:
  api_key: "your-api-key"
  base_url: "https://api.minimax.chat"
  model: "abab6.5s-chat"
```

## 许可证

MIT License

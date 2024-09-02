# EasyLogin: 一个基于JWT，无感刷新token机制的登录认证系统
## 项目截图

以下是 EasyLogin 系统的一些主要界面截图：

### 功能概览
EasyLogin 提供全面的用户认证功能，确保您的应用安全可靠。
![功能概览][image-1]

### 登录界面
简洁直观的登录界面，提供用户友好的体验。
![登录界面][image-2]

### 控制中心
强大的控制中心，实时监控系统状态和令牌信息。
![控制中心][image-3]

### 个人信息
用户可以方便地查看和管理个人信息。
![个人信息][image-4]

[![Vue Version][image-5]][1]
[![Express Version][image-6]][2]
[![Docker][image-7]][3]
[![License: MIT][image-8]][4]

EasyLogin 是一个现代化、安全、可扩展的登录系统，采用 Vue 3 和 Express 构建，并使用 Docker 进行容器化部署。本系统提供全面的用户认证功能，包括注册、登录、令牌刷新、密码重置等，并具有优雅的用户界面和强大的后端支持。

## 📚 目录

- [主要特性][5]
- [快速开始][6]
- [技术栈][7]
- [项目结构][8]
- [详细功能][9]
- [安全性][10]
- [配置][11]
- [开发指南][12]
- [部署][13]
- [测试][14]
- [贡献][15]
- [许可证][16]
- [联系方式][17]

## 🌟 主要特性

- 💻 响应式前端界面，基于 Vue 3 和 Tailwind CSS
- 🔐 JWT 认证，支持访问令牌和刷新令牌
- 🔄 无感刷新机制，提升用户体验
- 🛡️ 密码强度检测和安全存储
- 📊 用户仪表板，展示令牌状态和系统日志
- 🐳 Docker 支持，简化部署和环境管理
- 🔍 详细的系统日志，便于监控和调试

## 🚀 快速开始

### 前提条件

- Docker 和 Docker Compose
- Node.js (推荐 v20.16.0)
- pnpm 包管理器

### 使用 Docker 运行

1. 克隆仓库：
```bash
git clone https://github.com/JoJo20040325/easylogin.git
cd easylogin
```

2. 创建并编辑 `.env` 文件：
```bash
cp .env.example .env
```
   根据需求修改环境变量。

3. 构建和运行 Docker 容器：
```bash
docker-compose up --build
```

4. 访问应用：
   2. 前端：http://localhost:8080
   3. 后端 API：http://localhost:3000

## 📚 技术栈

### 前端
- Vue 3.4
- Pinia (状态管理)
- Vue Router
- Tailwind CSS
- Axios

### 后端
- Express.js
- MySQL
- JWT (jsonwebtoken)
- bcrypt (密码加密)

### 开发工具
- Vite

## 📂 项目结构

```
easylogin/
│
├── frontend/                # 前端 Vue 应用
│   ├── src/
│   │   ├── components/      # Vue 组件
│   │   ├── views/           # 页面视图
│   │   ├── store/           # Pinia 存储
│   │   ├── router/          # Vue Router 配置
│   │   └── utils/           # 工具函数
│   └── ...
│
├── backend/                 # 后端 Express 应用
│   ├── controllers/         # 路由控制器
│   │   ├── authController.js
│   │   └── userController.js
│   ├── models/              # 数据模型
│   │   ├── user.js
│   │   └── refreshToken.js
│   ├── routes/              # API 路由定义
│   │   ├── authRoutes.js
│   │   └── userRoutes.js
│   ├── middleware/          # 中间件
│   │   ├── authMiddleware.js
│   │   └── validationMiddleware.js
│   └── utils/               # 工具函数
│       ├── tokenUtils.js
│       └── errorHandler.js
│
├── docker-compose.yml       # Docker Compose 配置
└── README.md                # 项目文档
└── init.sql                 # 数据库初始化文件
```

## 🔎 详细功能

1. **用户认证**
   2. 注册新用户
   3. 用户登录
   4. 访问令牌和刷新令牌机制
   5. 无感刷新实现

2. **用户管理**
   2. 查看和更新用户资料
   3. 更改密码
   4. 删除账户

3. **安全特性**
   2. 密码强度检查
   3. JWT 认证
   4. 防止暴力攻击的速率限制

4. **仪表板功能**
   2. 显示令牌状态
   3. 令牌刷新日志
   4. API 调用日志

5. **其他功能**
   2. 忘记密码 / 密码重置
   3. 响应式设计，适配移动设备

## 🔒 安全性

- 使用 bcrypt 进行密码哈希
- JWT 用于安全的用户认证
- 实现了访问令牌和刷新令牌机制
- 全面的输入验证和 SQL 注入防护
- HTTPS 支持（在生产环境中配置）

## 🛠️ 配置

主要配置项在 `.env` 文件中，包括：

- `DB_HOST`: 数据库主机
- `DB_USER`: 数据库用户名
- `DB_PASSWORD`: 数据库密码
- `DB_NAME`: 数据库名称
- `JWT_SECRET`: JWT 签名密钥
- `JWT_REFRESH_SECRET`: 刷新令牌签名密钥
- `PORT`: 后端服务器端口
- `FRONTEND_URL`: 前端应用 URL

请确保在生产环境中使用强密钥和安全的配置。

## 💻 开发指南

### 本地开发

1. 前端开发：
```bash
cd frontend
pnpm install
pnpm run dev
```

2. 后端开发：
```bash
cd backend
pnpm install
pnpm run dev
```
## 🚢 部署

1. 确保已安装 Docker 和 Docker Compose。
2. 修改 `.env` 文件中的配置，适应生产环境。
3. 运行以下命令启动服务：
```bash
docker-compose up --build
```
4. 可以在[docker hub][18]上搜索**vue20040325/easylogin-backend**和**vue20040325/easylogin-frontend**分别下载后端和前端镜像，还有mysql的官方镜像，再通过docker-compose.images.yml(docker-compose -f docker-compose.images.yml up -d)将前后端联系起来运行整个应用。
## 🤝 贡献

我们欢迎所有形式的贡献，无论是新功能、bug 修复还是文档改进。请遵循以下步骤：

1. Fork 项目
2. 创建您的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建一个 Pull Request

## 📄 许可证

本项目采用 MIT 许可证。详情请见 [LICENSE][19] 文件。

感谢您对 EasyLogin 项目的关注！我们期待您的反馈和贡献。


[1]:	https://vuejs.org/
[2]:	https://expressjs.com/
[3]:	https://www.docker.com/
[4]:	https://opensource.org/licenses/MIT
[5]:	#-%E4%B8%BB%E8%A6%81%E7%89%B9%E6%80%A7
[6]:	#-%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B
[7]:	#-%E6%8A%80%E6%9C%AF%E6%A0%88
[8]:	#-%E9%A1%B9%E7%9B%AE%E7%BB%93%E6%9E%84
[9]:	#-%E8%AF%A6%E7%BB%86%E5%8A%9F%E8%83%BD
[10]:	#-%E5%AE%89%E5%85%A8%E6%80%A7
[11]:	#-配置
[12]:	#-%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97
[13]:	#-%E9%83%A8%E7%BD%B2
[14]:	#-%E6%B5%8B%E8%AF%95
[15]:	#-%E8%B4%A1%E7%8C%AE
[16]:	#-%E8%AE%B8%E5%8F%AF%E8%AF%81
[17]:	#-%E8%81%94%E7%B3%BB%E6%96%B9%E5%BC%8F
[18]:	https://hub.docker.com/
[19]:	LICENSE

[image-1]:	./screenshots/features.png
[image-2]:	./screenshots/login.png
[image-3]:	./screenshots/dashboard.png
[image-4]:	./screenshots/profile.png
[image-5]:	https://img.shields.io/badge/Vue-3.4-brightgreen.svg
[image-6]:	https://img.shields.io/badge/Express-4.19-blue.svg
[image-7]:	https://img.shields.io/badge/Docker-Ready-blue.svg
[image-8]:	https://img.shields.io/badge/License-MIT-yellow.svg
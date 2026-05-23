# 基于React的高校社团管理平台

一个基于 React + Express + MySQL 的大学社团管理系统，提供社团活动管理、成员管理、地图定位等功能。

## 功能特性

- 社团信息管理
- 社团活动发布与管理
- 成员管理与权限控制
- 活动地点地图定位（高德地图）
- 文件上传功能
- 邮件通知功能
- 响应式界面设计

## 技术栈

### 前端
- **React 19** - 用户界面框架
- **Vite** - 构建工具
- **Ant Design** - UI 组件库
- **React Router** - 路由管理
- **Axios** - HTTP 客户端
- **高德地图 API** - 地图服务

### 后端
- **Express.js** - Web 框架
- **MySQL** - 数据库
- **CORS** - 跨域资源共享
- **Nodemailer** - 邮件发送
- **Multer** - 文件上传
- **Day.js** - 日期处理
- **Dotenv** - 环境变量管理

## 项目结构

```
University-Club-Management/
├── backend/                 # 后端服务
│   ├── routes/             # 路由文件
│   ├── utils/              # 工具函数
│   │   └── mysql.js        # MySQL 连接配置
│   ├── public/             # 静态文件
│   │   └── uploads/        # 上传文件存储
│   ├── server.js           # 服务器入口
│   └── package.json
├── frontend/               # 前端应用
│   ├── src/
│   │   ├── components/     # React 组件
│   │   ├── router/         # 路由配置
│   │   ├── api.js          # API 接口
│   │   ├── App.jsx         # 应用入口
│   │   └── main.jsx        # React 挂载
│   ├── public/             # 静态资源
│   ├── index.html
│   └── package.json
└── package.json            # 根依赖
```

## 安装步骤

### 1. 克隆项目

```bash
git clone <repository-url>
cd University-Club-Management
```

### 2. 安装依赖

```bash
# 安装根目录依赖
npm install

# 安装后端依赖
cd backend
npm install

# 安装前端依赖
cd ../frontend
npm install
```

### 3. 配置数据库

在 `backend/utils/mysql.js` 中配置 MySQL 数据库连接：

```javascript
const pool = mysql.createPool({
  host: 'localhost',
  user: 'your_username',
  password: 'your_password',
  database: 'your_database',
  waitForConnections: true,
  connectionLimit: 10,
  queueLimit: 0
});
```

### 4. 配置环境变量

在项目根目录创建 `.env` 文件：

```
PORT=5000
```

## 运行项目

### 启动后端服务

```bash
cd backend
npm run dev    # 开发模式（使用 nodemon）
# 或
npm start      # 生产模式
```

后端服务将在 `http://localhost:5000` 运行

### 启动前端应用

```bash
cd frontend
npm run dev    # 开发模式
# 或
npm run build  # 构建生产版本
npm run preview  # 预览生产构建
```

前端应用将在 `http://localhost:5173` 运行（Vite 默认端口）

## API 接口

后端 API 基础路径为 `http://localhost:5000`

主要接口：
- `GET /` - 健康检查
- `POST /uploads` - 文件上传
- 其他业务接口（具体见 `backend/routes/` 目录）

## 开发说明

### 前端开发

- 使用 React 19 和 Vite 进行开发
- Ant Design 组件库提供 UI 支持
- React Router 管理页面路由
- Axios 处理 HTTP 请求

### 后端开发

- Express.js 提供 RESTful API
- MySQL 存储数据
- 支持事务处理
- CORS 配置允许跨域请求

## 注意事项

1. 确保已安装 Node.js (推荐 v18 或更高版本)
2. 确保已安装 MySQL 数据库
3. 高德地图 API 需要配置有效的 API Key
4. 邮件功能需要配置 SMTP 服务器信息

## 许可证

ISC

## 贡献

欢迎提交 Issue 和 Pull Request！

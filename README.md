# Gemini 2.5 Flash Image Preview API

一个基于 Flask 的 Gemini API 工具，支持文本和图像输入，可以一键部署到 Vercel。

## 功能特性

- 🖼️ 支持多种图像格式上传和处理
- 💬 文本和图像混合输入
- 🎛️ 可调节的生成参数（温度、最大输出长度等）
- 🔒 安全设置配置
- 🌐 支持 Vercel 一键部署
- 🔑 环境变量管理 API 密钥

## 本地开发

### 环境要求

- Python 3.8+
- Flask
- Google Generative AI SDK

### 安装依赖

```bash
pip install -r requirements.txt
```

### 配置 API 密钥

#### 方法1：环境变量（推荐）
```bash
export GEMINI_API_KEY="your-api-key-here"
```

#### 方法2：创建 key.txt 文件
在项目根目录创建 `key.txt` 文件，将 API 密钥写入其中。

### 运行应用

```bash
python app.py
```

应用将在 `http://localhost:5010` 启动。

## Vercel 部署

### 一键部署

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/your-username/gemini-2.5-flash-image-preview-API)

### 手动部署步骤

1. **Fork 或克隆此仓库**

2. **在 Vercel 中导入项目**
   - 访问 [Vercel Dashboard](https://vercel.com/dashboard)
   - 点击 "New Project"
   - 导入你的 GitHub 仓库

3. **配置环境变量**
   在 Vercel 项目设置中添加以下环境变量：
   
   | 变量名 | 值 | 说明 |
   |--------|----|---------|
   | `GEMINI_API_KEY` | 你的 Gemini API 密钥 | 必需 |
   | `FLASK_SECRET_KEY` | 随机字符串 | 可选，用于 Flask 会话 |

4. **部署**
   - Vercel 会自动检测到 `vercel.json` 配置文件
   - 点击 "Deploy" 开始部署

### 获取 Gemini API 密钥

1. 访问 [Google AI Studio](https://aistudio.google.com/)
2. 登录你的 Google 账户
3. 创建新的 API 密钥
4. 复制密钥并在 Vercel 中配置为环境变量

## 项目结构

```
.
├── app.py              # 主应用文件
├── requirements.txt    # Python 依赖
├── vercel.json        # Vercel 配置文件
├── templates/         # HTML 模板
│   └── index.html     # 主页面
└── README.md          # 项目说明
```

## API 端点

- `GET /` - 主页面
- `POST /api/generate` - 生成内容
- `GET /api/models` - 获取可用模型
- `GET /api/test` - 测试 API 连接
- `GET /uploads/<filename>` - 访问上传的文件

## 环境变量说明

| 变量名 | 必需 | 默认值 | 说明 |
|--------|------|--------|---------|
| `GEMINI_API_KEY` | 是 | - | Gemini API 密钥 |
| `FLASK_SECRET_KEY` | 否 | `your-secret-key-here` | Flask 会话密钥 |
| `VERCEL` | 否 | - | Vercel 环境标识（自动设置） |

## 注意事项

- Vercel 的免费计划有执行时间限制（10秒），大文件处理可能需要升级到付费计划
- 上传的文件在 Vercel 环境中会保存到 `/tmp` 目录，重启后会清除
- 建议在生产环境中使用 HTTPS

## 许可证

MIT License

## 预览截图

<img width="3840" height="1919" alt="image" src="https://github.com/user-attachments/assets/3e373830-414d-47bd-9e84-2f1825e2a64e" />

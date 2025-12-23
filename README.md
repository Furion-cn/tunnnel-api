<div align="center">

![tunnel-api](/web/public/logo.png)

# Tunnel API

🍥 **新一代大模型网关与AI资产管理系统**

<p align="center">
  <strong>中文</strong>
</p>


<p align="center">
  <a href="#-快速开始">快速开始</a> •
  <a href="#-主要特性">主要特性</a> •
  <a href="#-部署">部署</a> •
  <a href="#-文档">文档</a> •
  <a href="#-帮助支持">帮助</a>
</p>

</div>

## 📝 项目说明

> [!NOTE]  
> 本项目为开源项目，在 One API 的基础上进行二次开发

> [!IMPORTANT]  
> - 本项目仅供个人学习使用，不保证稳定性，且不提供任何技术支持
> - 使用者必须在遵循 OpenAI 的 [使用条款](https://openai.com/policies/terms-of-use) 以及**法律法规**的情况下使用，不得用于非法用途
> - 根据 [《生成式人工智能服务管理暂行办法》](http://www.cac.gov.cn/2023-07/13/c_1690898327029107.htm) 的要求，请勿对中国地区公众提供一切未经备案的生成式人工智能服务

---

## 🙏 特别鸣谢

<p align="center">
  <img src="https://resources.jetbrains.com/storage/products/company/brand/logos/jb_beam.png" alt="JetBrains Logo" width="120" />
</p>

<p align="center">
  <strong>感谢 JetBrains 为本项目提供免费的开源开发许可证</strong>
</p>

---

## 🚀 快速开始

### 使用 Docker 部署

```bash
# 构建镜像
docker build -t tunnel-api:latest .

# 启动服务
docker run --name tunnel-api -d --restart always \
  -p 3000:3000 \
  -e SQL_DSN="root:123456@tcp(localhost:3306)/tunnelapi" \
  -e TZ=Asia/Shanghai \
  tunnel-api:latest
```

---

🎉 部署完成后，访问 `http://localhost:3000` 即可使用！

---

## 📚 文档

更多文档请参考项目内的文档目录。

---

## ✨ 主要特性

### 🎨 核心功能

| 特性 | 说明 |
|------|------|
| 🎨 全新 UI | 现代化的用户界面设计 |
| 🌍 多语言 | 支持中文、英文、法语、日语 |
| 🔄 数据兼容 | 完全兼容原版 One API 数据库 |
| 📈 数据看板 | 可视化控制台与统计分析 |
| 🔒 权限管理 | 令牌分组、模型限制、用户管理 |

### 💰 支付与计费

- ✅ 在线充值（易支付、Stripe）
- ✅ 模型按次数收费
- ✅ 缓存计费支持（OpenAI、Azure、DeepSeek、Claude、Qwen等所有支持的模型）
- ✅ 灵活的计费策略配置

### 🔐 授权与安全

- 😈 Discord 授权登录
- 🤖 LinuxDO 授权登录
- 📱 Telegram 授权登录
- 🔑 OIDC 统一认证
- 🔍 Key 查询使用额度

### 🚀 高级功能

**API 格式支持：**
- ⚡ OpenAI Responses
- ⚡ OpenAI Realtime API（含 Azure）
- ⚡ Claude Messages
- ⚡ Google Gemini
- 🔄 Rerank 模型（Cohere、Jina）

**智能路由：**
- ⚖️ 渠道加权随机
- 🔄 失败自动重试
- 🚦 用户级别模型限流

**格式转换：**
- 🔄 OpenAI ⇄ Claude Messages
- 🔄 OpenAI ⇄ Gemini Chat
- 🔄 思考转内容功能

**Reasoning Effort 支持：**

<details>
<summary>查看详细配置</summary>

**OpenAI 系列模型：**
- `o3-mini-high` - High reasoning effort
- `o3-mini-medium` - Medium reasoning effort
- `o3-mini-low` - Low reasoning effort
- `gpt-5-high` - High reasoning effort
- `gpt-5-medium` - Medium reasoning effort
- `gpt-5-low` - Low reasoning effort

**Claude 思考模型：**
- `claude-3-7-sonnet-20250219-thinking` - 启用思考模式

**Google Gemini 系列模型：**
- `gemini-2.5-flash-thinking` - 启用思考模式
- `gemini-2.5-flash-nothinking` - 禁用思考模式
- `gemini-2.5-pro-thinking` - 启用思考模式
- `gemini-2.5-pro-thinking-128` - 启用思考模式，并设置思考预算为128tokens
- 也可以直接在 Gemini 模型名称后追加 `-low` / `-medium` / `-high` 来控制思考力度（无需再设置思考预算后缀）

</details>

---

## 🤖 模型支持

| 模型类型 | 说明 |
|---------|------|
| 🤖 OpenAI GPTs | gpt-4-gizmo-* 系列 |
| 🎨 Midjourney-Proxy | Midjourney-Proxy(Plus) |
| 🎵 Suno-API | Suno API |
| 🔄 Rerank | Cohere、Jina |
| 💬 Claude | Messages 格式 |
| 🌐 Gemini | Google Gemini 格式 |
| 🔧 Dify | ChatFlow 模式 |
| 🎯 自定义 | 支持完整调用地址 |

### 📡 支持的接口

- 聊天接口 (Chat Completions)
- 响应接口 (Responses)
- 图像接口 (Image)
- 音频接口 (Audio)
- 视频接口 (Video)
- 嵌入接口 (Embeddings)
- 重排序接口 (Rerank)
- 实时对话 (Realtime)
- Claude 聊天
- Google Gemini 聊天

---

## 🚢 部署

### 📋 部署要求

| 组件 | 要求 |
|------|------|
| **数据库** | MySQL ≥ 5.7.8 或 PostgreSQL ≥ 9.6 |
| **容器引擎** | Docker |

### ⚙️ 环境变量配置

<details>
<summary>常用环境变量配置</summary>

| 变量名 | 说明                                                           | 默认值 |
|--------|--------------------------------------------------------------|--------|
| `SESSION_SECRET` | 会话密钥（多机部署必须）                                                 | - |
| `CRYPTO_SECRET` | 加密密钥（Redis 必须）                                               | - |
| `SQL_DSN` | 数据库连接字符串                                                     | - |
| `REDIS_CONN_STRING` | Redis 连接字符串                                                  | - |
| `STREAMING_TIMEOUT` | 流式超时时间（秒）                                                    | `300` |
| `STREAM_SCANNER_MAX_BUFFER_MB` | 流式扫描器单行最大缓冲（MB），图像生成等超大 `data:` 片段（如 4K 图片 base64）需适当调大 | `64` |
| `MAX_REQUEST_BODY_MB` | 请求体最大大小（MB，**解压后**计；防止超大请求/zip bomb 导致内存暴涨），超过将返回 `413` | `32` |
| `AZURE_DEFAULT_API_VERSION` | Azure API 版本                                                 | `2025-04-01-preview` |
| `ERROR_LOG_ENABLED` | 错误日志开关                                                       | `false` |

📖 **完整配置：** 请参考项目内的环境变量文档

</details>

### 🔧 部署方式

**构建镜像：**
```bash
docker build -t tunnel-api:latest .
```

**启动服务：**
```bash
docker run --name tunnel-api -d --restart always \
  -p 3000:3000 \
  -e SQL_DSN="root:123456@tcp(localhost:3306)/tunnelapi" \
  -e TZ=Asia/Shanghai \
  tunnel-api:latest
```

### ⚠️ 多机部署注意事项

> [!WARNING]
> - **必须设置** `SESSION_SECRET` - 否则登录状态不一致
> - **公用 Redis 必须设置** `CRYPTO_SECRET` - 否则数据无法解密

### 🔄 渠道重试与缓存

**重试配置：** `设置 → 运营设置 → 通用设置 → 失败重试次数`

**缓存配置：**
- `REDIS_CONN_STRING`：Redis 缓存（推荐）
- `MEMORY_CACHE_ENABLED`：内存缓存

---


---

## 💬 帮助支持

### 📖 文档资源

更多帮助信息请参考项目内的文档目录。

### 🤝 贡献指南

欢迎各种形式的贡献！

- 🐛 报告 Bug
- 💡 提出新功能
- 📝 改进文档
- 🔧 提交代码

---


---

<div align="center">

### 💖 感谢使用 Tunnel API

如果这个项目对你有帮助，欢迎给我们一个 ⭐️ Star！

<sub>Built with ❤️ by QuantumNous</sub>

</div>

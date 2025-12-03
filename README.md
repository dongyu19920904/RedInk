![](images/logo.png)

---

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Vue 3](https://img.shields.io/badge/vue-3.x-green.svg)](https://vuejs.org/)

# 医墨 MedInk - AI医学科普图文生成器

> 专业知识，轻松传播；健康科普，触手可及

![](images/index.gif)

<p align="center">
  <em>医墨首页 - 输入医学主题，一键生成专业科普长图</em>
</p>

<p align="center">
  <img src="images/showcase-grid.png" alt="使用医墨生成的医学科普图文" width="600"/>
</p>

<p align="center">
  <em>使用医墨生成的医学科普图文 - AI驱动，风格统一，专业可信</em>
</p>

---

## 🏥 项目简介

**医墨（MedInk）** 是一款基于 AI 的医学科普图文生成工具，专为医学生、医护人员、健康科普创作者和医疗机构设计。

**一句话生成一整套医学科普长图**——输入医学主题，AI 自动生成 6-12 页风格统一、排版精美的健康教育图文内容。

### 🎯 适用人群

| 用户群体 | 使用场景 |
|---------|---------|
| 🎓 **医学生** | 制作考试复习笔记、知识点卡片、学习总结图 |
| 🏥 **医院宣传科** | 制作公众号科普文章、健康教育海报、疾病防治宣传 |
| 👨‍⚕️ **临床医生/护士** | 制作患者教育材料、术前术后指导、用药说明 |
| 💪 **健康管理师** | 制作健康指导图卡、饮食运动建议、慢病管理方案 |
| 📚 **医学教育机构** | 制作教学课件配图、知识点可视化、培训材料 |

### ✨ 核心优势

| 优势 | 说明 |
|------|------|
| ⚡ **效率提升 100x** | 从 2-4 小时手动制作 → 1-2 分钟 AI 生成 |
| 🎨 **零设计门槛** | 不需要 PS/Canva 技能，输入文字即可出图 |
| 🎯 **风格统一** | 全套长图自动保持一致的配色、排版、视觉风格 |
| 🏥 **医学专业性** | Prompt 针对医学场景优化，内容结构符合医学逻辑 |
| ✏️ **灵活可编辑** | 支持调整大纲、单页重绘、批量补全 |

---

## 📸 效果展示

### 输入医学主题，就能生成完整的科普长图

#### 示例主题：高血压的预防与治疗

**第一步：输入主题**

在首页输入医学主题，例如「高血压的预防与治疗」、「糖尿病饮食指南」、「胃镜检查注意事项」等。

![示例1](./images/example-1.png)

**第二步：AI 生成大纲**

等待 10-20 秒，AI 会自动生成结构化的内容大纲，包括：
- 📖 疾病定义/概述
- 🔬 病因/危险因素
- 🩺 症状/临床表现
- 📋 诊断/检查
- 💊 治疗/管理
- 🛡️ 预防/建议
- ✅ 总结/就医提醒

你可以根据需要调整每页内容。

![示例2](./images/example-2.png)

**第三步：生成科普长图**

点击生成后，AI 会并发生成所有页面的配图，风格统一、排版专业。

![示例3](./images/example-3.png)

![示例4](./images/example-4.png)

---

## 🏗️ 技术架构

### 后端
- **语言**: Python 3.11+
- **框架**: Flask
- **AI 模型**:
  - 文本生成：Gemini / GPT-4 / 通用 OpenAI 兼容接口
  - 图片生成：Gemini / DALL·E / Flux / 通用图片 API
- **包管理**: uv

### 前端
- **框架**: Vue 3 + TypeScript
- **构建**: Vite
- **状态管理**: Pinia
- **设计风格**: 医疗蓝专业配色

---

## 📦 快速部署

### 方式一：Docker 部署（推荐）

**最简单的部署方式，一行命令即可启动：**

```bash
docker run -d -p 12398:12398 -v ./history:/app/history -v ./output:/app/output histonemax/redink:latest
```

访问 http://localhost:12398，在 Web 界面的**设置页面**配置你的 API Key 即可使用。

**使用 docker-compose（可选）：**

```bash
docker-compose up -d
```

**Docker 部署说明：**
- 容器内不包含任何 API Key，需要在 Web 界面配置
- 使用 `-v ./history:/app/history` 持久化历史记录
- 使用 `-v ./output:/app/output` 持久化生成的图片

---

### 方式二：本地开发部署

**前置要求：**
- Python 3.11+
- Node.js 18+
- pnpm
- uv

**1. 克隆项目**
```bash
git clone https://github.com/HisMax/RedInk.git
cd RedInk
```

**2. 配置 API 服务**
```bash
cp text_providers.yaml.example text_providers.yaml
cp image_providers.yaml.example image_providers.yaml
```

**3. 安装依赖**
```bash
# 后端
uv sync

# 前端
cd frontend
pnpm install
```

**4. 启动服务**
```bash
# 后端
uv run python -m backend.app
# 访问: http://localhost:12398

# 前端（开发模式）
cd frontend && pnpm dev
# 访问: http://localhost:5173
```

---

## 🎮 使用指南

### 基础使用

1. **输入医学主题**: 在首页输入想要科普的主题，如「糖尿病的分型与诊断」
2. **生成大纲**: AI 自动生成 6-12 页的医学科普大纲
3. **编辑调整**: 可以编辑和调整每一页的内容描述
4. **生成图片**: 点击生成，实时查看进度
5. **下载使用**: 一键下载所有图片

### 推荐主题示例

| 类别 | 示例主题 |
|------|---------|
| 🩺 疾病科普 | 高血压防治指南、糖尿病的分型与诊断、冠心病的预防 |
| 🔬 检查指南 | 胃镜检查注意事项、体检报告解读、CT/MRI 检查须知 |
| 💊 用药指导 | 抗生素的正确使用、降压药服用注意事项、胰岛素注射方法 |
| 🥗 健康管理 | 高血压患者饮食指南、糖尿病运动处方、备孕期营养指导 |
| 🏥 手术须知 | 术前准备事项、术后康复指导、伤口护理方法 |

### 进阶使用

- **上传参考图片**: 保持品牌视觉风格一致
- **修改内容描述**: 精确控制每一页的内容和构图
- **单页重绘**: 对不满意的页面单独重新生成

---

## 🔧 配置说明

### 文本生成配置

配置文件: `text_providers.yaml`

```yaml
active_provider: openai

providers:
  openai:
    type: openai_compatible
    api_key: sk-xxxxxxxxxxxxxxxxxxxx
    base_url: https://api.openai.com/v1
    model: gpt-4o

  gemini:
    type: google_gemini
    api_key: AIzaxxxxxxxxxxxxxxxxxxxxxxxxx
    model: gemini-2.0-flash
```

### 图片生成配置

配置文件: `image_providers.yaml`

```yaml
active_provider: gemini

providers:
  gemini:
    type: google_genai
    api_key: AIzaxxxxxxxxxxxxxxxxxxxxxxxxx
    model: gemini-3-pro-image-preview
    high_concurrency: false
```

---

## ⚠️ 免责声明

> **重要提示**：本工具生成的所有内容仅供科普学习参考，**不作为医疗诊断、治疗或用药依据**。如有健康问题，请咨询专业医疗机构或医生。

- 生成内容由 AI 自动产出，可能存在不准确之处
- 请专业人士审核后再用于公开发布
- 禁止将生成内容用于虚假医疗宣传

---

## 🤝 参与贡献

欢迎提交 Issue 和 Pull Request！

如果这个项目对你有帮助，欢迎给个 Star ⭐

### 未来计划

- [ ] 预设医学主题模板（疾病科普/检查指南/用药说明）
- [ ] 医学术语「专业版/通俗版」切换
- [ ] 导出为 PDF、长图拼接
- [ ] 接入医学知识库 RAG，提升内容准确性
- [ ] 支持品牌定制（医院 Logo、自定义配色）
- [x] 历史记录管理
- [x] 单页重绘功能
    type: google_gemini
    api_key: AIzaxxxxxxxxxxxxxxxxxxxxxxxxx
    model: gemini-2.0-flash
```

### 图片生成配置

配置文件: `image_providers.yaml`

```yaml
# 当前激活的服务商
active_provider: gemini

providers:
  # Google Gemini 图片生成
  gemini:
    type: google_genai
    api_key: AIzaxxxxxxxxxxxxxxxxxxxxxxxxx
    model: gemini-3-pro-image-preview
    high_concurrency: false  # 高并发模式

  # OpenAI 兼容接口
  openai_image:
    type: image_api
    api_key: sk-xxxxxxxxxxxxxxxxxxxx
    base_url: https://your-api-endpoint.com
    model: dall-e-3
    high_concurrency: false
```

### 高并发模式说明

- **关闭（默认）**：图片逐张生成，适合 GCP 300$ 试用账号或有速率限制的 API
- **开启**：图片并行生成（最多15张同时），速度更快，但需要 API 支持高并发

⚠️ **GCP 300$ 试用账号不建议启用高并发**，可能会触发速率限制导致生成失败。

---

## ⚠️ 注意事项

1. **API 配额限制**:
   - 注意 Gemini 和图片生成 API 的调用配额
   - GCP 试用账号建议关闭高并发模式

2. **生成时间**:
   - 图片生成需要时间,请耐心等待（不要离开页面）

---

## 🤝 参与贡献

欢迎提交 Issue 和 Pull Request!

如果这个项目对你有帮助,欢迎给个 Star ⭐

### 未来计划
- [ ] 支持更多图片格式，例如一句话生成一套PPT什么的
- [x] 历史记录管理优化
- [ ] 导出为各种格式(PDF、长图等)

---

## 🔄 更新日志

### v2.0.0 - MedInk 医学科普版 (2025-12-03)
- 🏥 **全新定位**：从小红书图文工具转型为医学科普图文生成器
- ✨ 医学科普专用 Prompt，支持疾病科普/检查指南/健康管理等场景
- ✨ 医疗蓝专业配色，清新可信的视觉风格
- ✨ 新增免责声明组件，确保内容合规
- ✨ 医学主题示例引导，降低使用门槛
- 🔧 内容结构优化：定义→病因→症状→诊断→治疗→预防→总结

### v1.4.0 (2025-11-30)
- 🏗️ 后端架构重构：拆分单体路由为模块化蓝图
- 🏗️ 前端组件重构：提取可复用组件
- ✨ 优化首页设计，背景图片预加载
- ✨ 历史记录持久化支持（Docker部署）
- 🧪 新增65个后端单元测试

### v1.3.0 (2025-11-26)
- ✨ 新增 Docker 支持，一键部署
- ✨ 发布官方 Docker 镜像: `histonemax/redink`

### v1.2.0 (2025-11-26)
- ✨ 新增 Web 界面配置功能
- ✨ 图片重新生成功能，支持单张重绘
- ✨ 高并发模式开关

---

## 📞 交流与支持

- **GitHub Issues**: [提交问题或建议](https://github.com/HisMax/RedInk/issues)

### 联系作者

- **Email**: histonemax@gmail.com
- **微信**: Histone2024（添加请注明来意）
- **GitHub**: [@HisMax](https://github.com/HisMax)

### 用爱发电 ☕

如果这个项目对你有帮助，请作者喝一杯咖啡吧！

<img src="images/coffee.jpg" alt="赞赏码" width="300"/>

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=HisMax/RedInk&type=Date)](https://star-history.com/#HisMax/RedInk&Date)

---

## 📄 开源协议

本项目采用 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 协议

**你可以：**
- ✅ 个人使用 - 用于学习、研究、个人项目
- ✅ 分享 - 在任何媒介以任何形式复制、发行
- ✅ 修改 - 修改、转换或以本作品为基础进行创作

**但需要：**
- 📝 署名 - 给出适当的署名
- 🚫 非商业性使用 - 不得用于商业目的
- 🔄 相同方式共享 - 以相同协议分发衍生作品

**商业授权**：如需商业使用，请联系 histonemax@gmail.com

---

## 🙏 致谢

- [Google Gemini](https://ai.google.dev/) - 强大的 AI 能力
- [OpenAI](https://openai.com/) - 优秀的语言模型
- 原项目 [RedInk](https://github.com/HisMax/RedInk) - 默子的开源贡献

---

## 👨‍💻 作者

**默子 (Histone)** - AI 创业者 | Python & 深度学习

- 📧 Email: histonemax@gmail.com
- 💬 微信: Histone2024
- 🐙 GitHub: [@HisMax](https://github.com/HisMax)

*"让 AI 帮助医学知识更好地传播"*

---

**如果这个项目帮到了你，欢迎 Star ⭐ 和分享给更多人！**

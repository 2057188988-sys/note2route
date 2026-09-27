# Developer Log · note2route

> note2route — 把小红书笔记自动转成「能照着走的地图路线 + 行程单」。
> 目标岗位方向：Agent 应用工程师（对日 IT）。本日志记录每天的实际进展，作为成长轨迹与简历素材。

---

## 2026-09-27 · 项目立项 + M0 环境搭建

**Summary / 摘要：** Kicked off the note2route project — fixed product scope & architecture, set up a learning-by-doing workflow, and completed most of milestone M0 (git, venv, requirements, secrets config).

### 今日目标
- 把「前端学习路线 / TodoList 指南 / note2route 方案」三份材料整合成一条可执行的成长路径。
- 完成 M0（立项与环境）的大部分搭建。

### 完成的工作
- **立项**：确定产品定位（小红书笔记 → 地图路线 + 行程单）与架构（H5 + FastAPI + openai-agents + DeepSeek + 高德 Web 服务）。
- **学习方法论**：确立「以 note2route 为主线、缺啥补啥、边做边记」的闭环：学 → 做 → 观察 → 记录 → 复盘。
- **文档产出**：
  - `TODO.md` —— 每日打卡清单 + M0~M5 里程碑 + Agent 知识点清单。
  - `M0-环境搭建.md` —— 7 步环境搭建操作手册。
- **M0 环境搭建**：
  - `git init` 初始化仓库。
  - 建立目录结构 `backend/app`、`frontend`、`examples`。
  - 创建 Python 虚拟环境 `.venv`。
  - 编写 `backend/requirements.txt`（fastapi / uvicorn / openai-agents / python-dotenv / httpx）。
  - 编写 `.gitignore`（排除 `.env`、`.venv` 等敏感/可再生文件）。
  - 申请高德 Web 服务 Key 与 DeepSeek API Key。
  - 配置 `.env.example`（占位模板）与 `.env`（真实密钥，**不入库**）。

### 学到的知识
- 后端技术栈五件套各自的职责（fastapi=接口框架、uvicorn=服务器、openai-agents=Agent 框架、python-dotenv=读密钥、httpx=发 HTTP 请求）。
- 网络基础概念：端口 / IP / TCP、返回 JSON、密钥（身份凭证）的作用与安全边界。

### 遇到的问题 & 解决
- 密钥不得写入代码或提交到仓库 → 用 `.env` 存真实值 + `.gitignore` 排除，只提交 `.env.example` 模板。

### 下一步
- 安装依赖（`pip install -r backend/requirements.txt`）。
- 编写 `test_amap.py` 调通一次高德 geocode，完成 M0 验收。
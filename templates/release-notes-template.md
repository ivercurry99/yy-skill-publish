# Release Notes 模板 · v1.0.0 首次公开发布专用

> 复制整个模板到 `release-notes.md`，替换三处 `<占位符>` → 执行 gh release create 即可。
> 适用：项目初次公开发布的 v1.0.0 正式版（非 draft、非 prerelease）。

---

## vX.Y.Z：<版本标题，核心一句话，20–30 字>

> 用一句话告诉用户「这个版本我终于能干嘛了」。
> 例：v1.0.0：一句话 vibe coding 完整项目，五角色×五道门禁×进度记忆

### ✨ 核心特性（4–6 条 bullets，量化优先）

- **<特性 1 分类标签>**：<具体价值 + 量化数字>。例：**五角色协作引擎** — Product / Architect / Dev / QA / DevOps 自动流转，项目从 idea 到完整仓库只需 1 次启动。
- **<特性 2 分类标签>**：<具体价值 + 量化数字>。例：**五道门禁 Gate 机制** — 每阶段不达标自动打回，不会硬往下堆垃圾产物，整体返工率 ↓60%。
- **<特性 3 分类标签>**：<具体价值 + 量化数字>。例：**进度持久化记忆** — PROGRESS.md + GATES.md 双文件存档，代理断了/切了/换了/重启了都能在断点精准续跑。
- **<特性 4 分类标签>**：<具体价值 + 量化数字>。例：**多 Agent 自动降级链** — 首选 TRAE → Cursor → 通用 LLM，3 路自动切换，不会半路卡死（鲁棒性测试 20 个项目通过率 100%）。
- **（可选）** 零依赖卖点：**0 pip install** — 纯 Python 标准库实现，Mac / Windows / Linux 任意环境 clone 完即跑，避免依赖战争。

### 🚀 开箱即用（3 行法复制粘贴可跑）

```bash
# 1. 克隆项目
git clone https://github.com/<owner>/<repo>.git
cd <repo>

# 2. 启动（有 requirements.txt 才加 pip install）
python run.py

# 3. 典型输出片段（贴 5–10 行真实 stdout 节选）
# [GATE-1] PRD 完整性检查       PASS (score 92/100)
# [GATE-2] 技术方案确认         PASS (3 diagrams generated)
# ...
# [DONE] 项目构建完成，用时 4 min 12 s
```

### 📚 阅读更多
- 项目说明：[README.md](./README.md)
- 使用教程：[docs/getting-started.md](./docs/getting-started.md)（如果有）

### 🤝 交流反馈
欢迎提 issue 交流你在实际项目里遇到的任何卡点：
- <场景 1 你关心的问题> 例：真实业务中总是在 Gate-3 设计评审被打回，希望增加"自动生成时序图"辅助
- <场景 2 你关心的问题> 例：希望直接支持 Python 之外的技术栈脚手架
- <场景 3 你关心的问题> 例：想对接到自己公司已有的内部 CI/CD 流程

直接开 issue 描述清楚，都会跟进！ 🙌

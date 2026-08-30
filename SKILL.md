---
name: "skill-publish"
description: "将个人 Skill 或小型开源项目发布到公开 GitHub，一站式完成商标合规检查、仓库包装、README 美化、Release 发版、推广物料生成。写完项目后要公开上线时调用。"
---

# skill-publish · 开源项目发布到 GitHub 一站式流水线

一套把「本地写完的 Skill / 开源项目」变成「GitHub 上能搜到、能看懂、愿意点开看、愿意下载试用」的**标准操作流程**。全流程 6 个 Phase，按顺序执行即可。

---

## 什么时候用（触发条件）

- ✅ 你刚写完一个本地 Skill（例如知识管理工具、出图脚本、Agent 工作流），准备公开到 GitHub 时
- ✅ 你想给已有仓库做一次"星增长体检"，重新包装 About / Topics / README 时
- ✅ 你想发布一次带版本号的 Release，并配套写好 Release Notes 时
- ✅ 你想同步生成 掘金 / V2EX / 小红书 / 即刻等平台的分享帖物料时
- ❌ 不是写代码 / 修 Bug / 做 Code Review（那些走别的技能）

---

## Phase 1 — 法律合规体检（先做，不然后面改成本很高）

### 1.1 商标 & 品牌词扫描
扫一遍 README.md / SKILL.md / 脚本文件里是否出现以下风险词：
- **禁止当作产品名**的注册商标：`ChatGPT`、`GPT-4`、`抖音`、`微信`、`App Store`、`YouTube`、`Google`、`Facebook` 等
  - ✅ 正确写法：用"兼容 OpenAI 系列大模型"、"可调用 xx 平台接口"这类描述句式，不要把品牌当产品名字段
- **商标符号**：除非你真的持有注册证，否则自己的项目名后面**不要加 ® / ™**
- **GitHub 相关标识**：GitHub Logo、Octocat 形象**禁止直接放进仓库作为装饰**（除非你拿到 GitHub 授权）；"GitHub"这四个字作为平台名称可以正常提及
- **API 厂商名称**：写 "Seedream / DALL·E 3 / FLUX 等出图服务" 是正常描述用法；**不要把它们的 Logo 直接扒进 README 做装饰图**
- **字体**：如果 README 里有演示截图，截图中的装饰字体必须是开源免费可商用字体（思源黑体 / Noto Sans / 站酷快乐体等），**不要用未授权的方正/汉仪/蒙纳字体**
- **人像**：示例图里用的真人头像/照片必须是自己拍的、或 Unsplash / Pexels 授权 CC0；**禁止直接从社交平台扒别人的照片**
- **敏感词**：政治/色情/毒品/暴力/赌博/未成年人相关 → 0 容忍，直接删除

### 1.2 License 格式 & 选择合规
开源项目**必须有 LICENSE 文件**，没有就默认"版权所有"，别人不敢用。
- 默认推荐：**MIT License**（最宽松、星增长友好，企业和个人都敢用）
- LICENSE 文件首行必须严格是 `MIT License`，**首行空着或写"MIT协议"中文会导致 GitHub 识别不到 License 徽标**
- 标准 MIT 模板（复制替换掉 `[年份]` `[你的用户名]` 即可）：
  ```
  MIT License

  Copyright (c) [年份] [你的 GitHub 用户名]

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files (the "Software"), to deal
  in the Software without restriction, including without limitation the rights
  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the Software is
  furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in all
  copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
  SOFTWARE.
  ```
- 校验：`gh repo view <owner>/<repo> --json licenseInfo` 输出必须显示 `MIT`；否则修正 LICENSE 后重新 push

### 1.3 敏感信息 & 隐私清理
全局 grep 以下模式，发现就删除或改成占位符：
- 硬编码密钥：`ghp_`、`sk-`、`xoxb-`、`AKIA`、`Bearer ` 开头的长 token
- 个人隐私：手机号、真实姓名非必要不放、邮箱、身份证、银行卡、具体住址
- 内部链接：内网 `192.168.*` / `10.*`、带 internal 关键字的 URL、未公开私有仓库地址
- 临时文件路径：用户本地目录 `C:\Users\xxx\` 这类绝对路径 → 改成通用示例 `$HOME/project`

---

## Phase 2 — GitHub 仓库包装（About 栏三件套）

### 2.1 Description 公式（直接套）
> **英文一句话核心卖点 + 句号 + 中文补充说明**。长度 80–160 字符。
- 开头 40 个字符最重要（手机端 GitHub App 搜索结果页只截断显示这么多）
- 开头一定要含**搜索关键词**，别写"一个有用的小工具"这种空话
- 示例：
  - ❌ 坏："小红书作图工具，很好用，快来用"
  - ✅ 好："Structured prompts + multi-model adapter for Xiaohongshu AI carousels. 8 style presets, 4 vendor fallback, stability first. 结构化 Prompt + 多模型适配器生成小红书图文素材，出图稳定优先"

### 2.2 Website 字段（不要留空！）
优先级：
1. 项目真实 Demo URL / 线上作品地址 / 作者小红书主页
2. 作者自己的 GitHub Profile：`https://github.com/<username>`
3. **兜底**：填仓库自己的 URL（空着 = About 栏少一行信息 + 少一个点击入口）

### 2.3 Topics 组合公式（8–12 个）
> **4 类搭配，缺一不可：大分类(3–4) + 业务场景(3–5) + 热门高频(2–3) + 小众 niche(1–2)**

- 字符规则：GitHub 官方只接受**小写字母 / 数字 / 单个连字符 `-`**；不能中文、不能大写、不能空格、不能以下划线或 `-` 开头结尾
- 分类定义与示例：
  | 类别 | 作用 | 示例 |
  |------|------|------|
  | 大分类技术栈 | 让用户搜"python"这类大类词能命中 | `python`, `javascript`, `typescript`, `rust`, `go`, `cli` |
  | 业务场景 | 让用户搜"我做第二大脑能用什么"能命中 | `second-brain`, `knowledge-management`, `xiaohongshu`, `llm-agent`, `note-taking` |
  | 热门高频 | GitHub 搜出来最多人用的 tag，带流量 | `prompt-engineering`, `stable-diffusion`, `agent-skill`, `workflow-automation`, `ai-coding-assistant` |
  | 小众 niche | 精准人群、竞争少、转化高 | `para-method`, `zettelkasten`, `harness`, `scaffolding`, `pkm`, `seedream` |

完整示例见 `templates/topics-formula.md`。

---

## Phase 3 — README 视觉美化（5 个标准模块）

> 目标：**用户滚动到第一屏能在 3 秒内看懂"这是啥、我能用吗、怎么跑"**。

### 3.1 Hero 首屏（必做）
```
# 项目名（<30 字，中英双语可选）

<项目 Hero 图 / 装饰 SVG —— 宽度铺满 900px>

> Slogan 一句话（<50 字）
> 例：3 分钟搭好结构化第二大脑知识库，0 配置 0 网络，100% 纯 Python 标准库。

核心特性 3–4 条 bullets：
- ✨ 特性 1：具体写价值，不要写"功能丰富"
- 🚀 特性 2：量化数字优先（3 min / 0 dependency / 4-tier fallback / 8 presets）
- 🛡️ 特性 3：工程化或稳定卖点（自动降级 / 进度记忆 / 幂等安全）
```

### 3.2 Badge 三件套（必做）
统一用 shields.io 风格，放在项目名下面一行：
- `![License](https://img.shields.io/badge/license-MIT-green)`
- `![Python](https://img.shields.io/badge/python-3.8%2B-blue)`
- `![Platform](https://img.shields.io/badge/platform-win%20%7C%20mac%20%7C%20linux-lightgrey)`
- 可选：`![CI](https://github.com/<owner>/<repo>/actions/workflows/ci.yml/badge.svg)`

### 3.3 截图/演示区（必做）
- 至少 1 张，放 Features 段最顶部；最好是 GIF 展示核心流程
- ALT 文本写清楚：`![知识库4层流程图——从 Capture 到 Express 四个阶段流转]`
- 如果暂时没图：**先用明确的占位注释 `<!-- TODO: 插入 XX 演示截图（建议：长宽 1600x900 png） -->`**，不要真的留空

### 3.4 安装 & 运行（必做）
**3 行法，复制粘贴就能跑**：
```bash
# 1. 克隆
git clone https://github.com/<owner>/<repo>.git
cd <repo>

# 2. 运行（如果有依赖才加 pip install）
python run.py

# 3. 输出长这样（贴 5–10 行真实 stdout 示例）
[Phase 1/4] Capture       ... OK → 3 files imported
[Phase 2/4] Index         ... OK → 18 notes indexed
...
[DONE] 知识库构建完成，用时 2 min 34 s
```

### 3.5 对比表 / 为什么又造轮子（强烈推荐）
回答第一个访客的灵魂拷问"为什么我不用现成的 XX 非要用你这个"：

| 维度 | 本项目 | 手写笔记 / 传统脚手架 | 商业 SaaS |
|------|--------|----------------------|-----------|
| 配置成本 | 0 | 数天 | 数小时 |
| 数据隐私 | 100% 本地文件 | 本地 | 上传到云端 |
| 可定制 | 全开源可改 | 难改 | 黑盒 |
| 价格 | 免费 | 免费 | 月/年订阅 |

---

## Phase 4 — 语义化版本 Release 发布

### 4.1 版本号规则（SemVer）
- 首次发布：**固定 `v1.0.0`**（0.x.x 给人的感觉"还在 alpha 不稳定"）
- 后续：
  - `PATCH  v1.0.1`：修 Bug，向后兼容
  - `MINOR  v1.1.0`：新增功能，向后兼容
  - `MAJOR  v2.0.0`：破坏性变更，升级会报错

### 4.2 Release Notes 三段式模板
详见 `templates/release-notes-template.md`。
- **标题**：`vX.Y.Z：版本核心一句话卖点（<30 字）`
- **正文**：核心特性 bullets → 快速启动 3 行 → 欢迎提 issue 邀请
- **正式版**：不勾 Draft / 不勾 Pre-release / 勾 Set as latest release

### 4.3 发布命令
```bash
# 写好 notes.md 后
gh release create v1.0.0 --target main \
  --title "v1.0.0：初次公开发布，核心特性上线" \
  --notes-file release-notes.md \
  --latest
```

---

## Phase 5 — 多平台推广物料生成

### 5.1 目录结构（标准）
```
tiezi/
└── <项目名>/
    ├── juejin.md      # 掘金：最完整 + 技术深度最强
    ├── v2ex.md        # V2EX：精简版 + 程序员社区口吻
    ├── jike.md        # 即刻：短平快 + 个人分享口吻
    └── xiaohongshu.md # 小红书：如果是生活/创作/效率类内容才投
```

### 5.2 选 3 个平台的策略
- **技术 / AI Coding / Agent 类项目**：掘金 + V2EX + 即刻
- **AI 出图 / 内容创作 / 知识管理类**：小红书 + 掘金 + V2EX
- **CLI / 纯程序员工具**：掘金 + V2EX + 知乎（可选）

### 5.3 分享帖结构铁律（违者重写）
**a → b → c → d 四段，顺序不能乱**：

> **a. 开篇：开发背景 / 现实痛点**（4–6 条具体、真实、读者能共鸣的痛点，不要空话）

> **b. 核心功能介绍 + 2–3 截图占位**（每张占位写清楚「这张应该放什么内容 + 推荐尺寸」，不要只写个"放截图"）

> **c. 实现过程里踩过的关键技术坑**（3–4 个，含：具体表现 → 根因 → 解决方法 → 思考启示）

> **d. 结尾**：项目已经开源 → 欢迎下载试用 → 欢迎提 issue 交流反馈 → 附上 GitHub 仓库链接

### 5.4 铁律红线
- ❌ 绝对禁止：「求 star」「帮点 star」「star 一下」「随手点 star」这类直白乞求（任何变体都不行，包括 emoji 暗示 🥺👉👈 也不行）
- ❌ 禁止：广告口吻（"市面上最好的""秒杀竞品""全网首发"这类自吹词）
- ✅ 正确语气：个人开发者真实踩坑分享，有缺点也可以坦白说"目前还没支持 XX，下一个 Release 补"

详细 Markdown 模板见 `templates/share-post-template.md`。

---

## Phase 6 — Skill 项目自身打包 & 发布到 GitHub

### 6.1 Skill 格式必须合规
- 标准目录：`.trae/skills/<skill-name>/`
- 必须有：`SKILL.md`（frontmatter 含 `name` + `description`，description 必须同时写「做什么 + 什么时候调用」）
- 可选子目录：
  - `scripts/` Python/Bash 辅助脚本
  - `templates/` Markdown / JSON / SVG 模板
  - `assets/` 图片、图标、示例输出

### 6.2 SKILL.md 内容清理（敏感信息检查最后一次）
- ❌ 不能包含：用户本地临时路径（`C:\Users\xxx\AppData\Local\Temp\...`）、真实 token、私有仓库 URL、项目临时进度
- ✅ 必须全是：可复用的流程说明、触发条件、安全示例、占位符

### 6.3 公开仓库必备文件
推到 GitHub 之前，根目录必须补齐：
- `LICENSE`（MIT，按 Phase 1.2）
- `README.md`（中文，按 Phase 3 的 5 模块）
- `.gitignore`（Python 项目必加 `__pycache__/ *.pyc .DS_Store` 等）

### 6.4 推送后「自举」执行
Skill 项目本身推到 GitHub 之后，**立刻重新跑一遍本流程的 Phase 2 → Phase 4**：
1. 改 Description / Website / Topics
2. 检查 License 徽标显示
3. 发 v1.0.0 Release

→ 完成后这个 Skill 自己就是一个合格的"skill-publish 流程示范作品"。

---

## 执行清单（调用方照跑）

| 步骤 | 动作 | 输出物 | Done |
|------|------|--------|:----:|
| 1 | Phase 1 法律合规体检：商标 / LICENSE 格式 / 敏感词 / 隐私 | 一份 clean 的仓库 | ☐ |
| 2 | Phase 2 About 三件套：Description 按公式写 + Website 填充 + Topics 8-12 个按公式组合 | About 栏更新完成 | ☐ |
| 3 | Phase 3 README 视觉美化：Hero + Badge + Screenshot + Install 3 行 + 对比表 | README.md 定稿 | ☐ |
| 4 | Phase 4 Release：语义化版本号 v1.0.0 + Release Notes 三段式发布 | GitHub Release 页 | ☐ |
| 5 | Phase 5 推广物料：tiezi/<项目>/<平台>.md 生成 3 篇，严格 a-b-c-d 结构 | 3 篇 Markdown 帖 | ☐ |
| 6 | 如果是 Skill → Phase 6 打包发布 + 自举执行一遍 2-4 步骤 | 公开仓库上线 | ☐ |

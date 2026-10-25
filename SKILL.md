---
name: "yy-skill-publish"
description: "把本地写完的 Skill 或小型开源项目发布到公开 GitHub：商标与许可证自查、About 栏与 Topics 填写、README 改写、版本发布、各平台分享帖草稿。产出可直接公开的仓库、一份定稿 README、一个正式 Release 和 3 篇分享帖。项目写完准备公开上线时使用；写代码、修 Bug、Code Review 不要用本技能处理，它们属于其他技能范围。"
---

# yy-skill-publish

把本地项目发布到公开 GitHub 的操作流程，共 6 个阶段，按顺序执行。每个阶段有具体的检查项、命令和模板。

## 什么时候用

- 写完一个本地 Skill（知识管理工具、出图脚本、Agent 工作流等），准备公开到 GitHub
- 给已有仓库重新填写 About 栏和 Topics，改写 README
- 发布一个带版本号的 Release，并写好 Release Notes
- 为项目起草掘金 / V2EX / 小红书 / 即刻等平台的分享帖

写代码、修 Bug、Code Review 属于其他技能的范围。

---

## Phase 1 — 法律与合规自查

发布后再处理侵权投诉，成本远高于现在，所以这一步放在最前面。

### 1.1 商标与品牌词扫描
检查 README.md、SKILL.md 和脚本文件中是否出现以下内容：
- 不得把他人注册商标当作产品名：`ChatGPT`、`GPT-4`、`抖音`、`微信`、`App Store`、`YouTube`、`Google`、`Facebook` 等。需要提及这些产品时，用「兼容 OpenAI 系列大模型」「可调用 xx 平台接口」这类描述句式
- 项目名后面不加 ® / ™，除非持有商标注册证
- GitHub Logo、Octocat 不直接放进仓库作装饰；「GitHub」一词作为平台名称可以正常提及
- API 厂商名称（Seedream、DALL·E 3、FLUX 等）作为服务名描述是正常用法；不把它们的 Logo 贴进 README 作装饰
- README 截图中的字体使用开源可商用字体（思源黑体、Noto Sans 等），不用未授权的方正、汉仪、蒙纳字体
- 示例图人像来源：自己拍摄，或 Unsplash / Pexels 授权内容；不从社交平台下载他人照片
- 政治、色情、毒品、暴力、赌博、未成年人相关内容：发现即删除

### 1.2 LICENSE 文件
开源项目必须有 LICENSE 文件。没有许可证时默认版权保留，多数用户和企业不会使用。
- 默认推荐 MIT License
- 首行必须严格是 `MIT License`；首行为空或写中文会导致 GitHub 识别不到许可证徽标
- 使用官方 19 行英文版本，替换 `[年份]` 和 `[你的用户名]`：

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

- 校验：`gh repo view <owner>/<repo> --json licenseInfo` 输出显示 `MIT`；否则修正后重新推送

### 1.3 敏感信息与隐私
全局搜索以下模式，发现就删除或改为占位符：
- 硬编码密钥：`ghp_`、`sk-`、`xoxb-`、`AKIA`、`Bearer ` 开头的长 token
- 个人隐私：手机号、身份证、银行卡、具体住址；真实姓名和邮箱非必要不放
- 内部链接：内网 `192.168.*` / `10.*`、带 internal 关键字的 URL、未公开的私有仓库地址
- 本地绝对路径：写死的用户主目录（`C:\Users\<用户名>\`、`/home/<用户名>/`）改为通用示例 `$HOME/project`

---

## Phase 2 — About 栏与 Topics

### 2.1 Description 写法
英文一句话说明项目做什么 + 中文补充，总长 80–160 字符。开头 40 个字符内包含搜索关键词（GitHub App 搜索结果只显示这么多），不写「一个有用的小工具」这类空话。

示例：
- 不好：「小红书作图工具，很好用，快来用」
- 好：「Generate Xiaohongshu-ready 3:4 images from short text. 8 built-in style presets. 依据简短文本生成小红书常用 3:4 图文，内置 8 套风格预设」

### 2.2 Website 字段
优先级：项目 Demo 地址 → 作者主页（`https://github.com/<username>`）→ 仓库自身 URL。留空会少一个点击入口。

### 2.3 Topics 组合
8–12 个，按 4 类搭配：大分类技术栈 3–4 个 + 业务场景 3–5 个 + 热门高频 2–3 个 + 小众 1–2 个。字符规则：GitHub 只接受小写字母、数字、单个连字符；不能中文、大写、空格、下划线。完整示例见 `templates/topics-formula.md`。

---

## Phase 3 — README 改写

目标：首屏说明项目是什么、给谁用、怎么跑起来；示例放在长解释前面；卖点只写真实存在的能力。

### 3.1 首屏结构
```
# 项目名（30 字以内，中英双语可选）

<项目 Hero 图 / 装饰 SVG，宽度约 900px>

> 一句话说明项目做什么（50 字以内）

核心特性 3–4 条：写具体行为和数字（3 分钟、0 依赖、8 套预设），不写「功能丰富」
```

### 3.2 Badge
放在项目名下方，用 shields.io：
- `![License](https://img.shields.io/badge/license-MIT-green)`
- `![Python](https://img.shields.io/badge/python-3.8%2B-blue)`
- `![Platform](https://img.shields.io/badge/platform-win%20%7C%20mac%20%7C%20linux-lightgrey)`
- 可选：CI 徽章 `https://github.com/<owner>/<repo>/actions/workflows/ci.yml/badge.svg`

### 3.3 截图与示例
至少 1 张，放在特性说明前；最好用 GIF 展示核心流程。ALT 文本写清楚内容。暂时没有图时，用明确的占位注释 `<!-- 待插入：XX 演示截图（建议 1600x900 png） -->`，不留空。

工具类项目（出图、渲染、生成器）必须**用自己产出的真实结果**当示例，不用示意图或占位图：先跑一遍工具拿到真实产物，再挑 3–4 个代表性输出放进 README，并注明「以下示例由本工具生成」。这比任何文字介绍都有说服力。Hero 主图也用项目自身风格生成，不加 AI 生成容易写错的文字。

### 3.4 安装与运行
3 行以内，复制即可执行：
```bash
git clone https://github.com/<owner>/<repo>.git
cd <repo>
python run.py

# 输出示例（贴 5–10 行真实 stdout）
[Phase 1/4] Capture       ... OK → 3 files imported
[Phase 2/4] Index         ... OK → 18 notes indexed
[DONE] 构建 完成，用时 2 min 34 s
```

### 3.5 对比表
回答「为什么不用现成的 XX」：从配置成本、数据隐私、可定制性、价格等维度，对照手写方案和商业产品，只写能核实的差异。

### 3.6 文风检查
写完 README 后自查一遍，出现下列写法就修改：
- 标题不用 emoji 开头：「## ✨ 核心能力」改为「## 核心能力」
- 不用这些词：一站式、全流程闭环、赋能、三件套、灵魂拷问、铁律红线、颗粒度、抓手
- 不做夸张表述：「访客 3 秒看不懂直接关掉」改写为「首屏说明项目用途」；「全部自动包圆」改为列出实际自动完成的事项
- 不编造数据：没有实测依据，不写「效率提升 X%」「通过率 100%」
- 少用连续排比句，改写为一句陈述或普通列表
- 加粗只用于术语和命令；介绍事实用陈述句

---

## Phase 4 — Release 发布

### 4.1 版本号（SemVer）
- 首次发布用 v1.0.0；0.x.x 会被读者理解为不稳定版本
- PATCH（v1.0.1）修 Bug，向后兼容；MINOR（v1.1.0）新增功能；MAJOR（v2.0.0）破坏性变更

### 4.2 Release Notes
见 `templates/release-notes-template.md`：标题写版本核心变化（30 字以内），正文为特性列表、快速启动命令、issue 邀请。不勾 Draft 和 Pre-release，勾选 latest。

### 4.3 发布命令
```bash
gh release create v1.0.0 --target main \
  --title "v1.0.0：初次公开发布" \
  --notes-file release-notes.md \
  --latest
```

---

## Phase 5 — 分享帖草稿

### 5.1 目录结构
```
tiezi/
└── <项目名>/
    ├── juejin.md      # 掘金：内容最完整、技术细节最多
    ├── v2ex.md        # V2EX：精简版、程序员社区口吻
    ├── jike.md        # 即刻：短、个人分享口吻
    └── xiaohongshu.md # 小红书：生活/创作/效率类内容才投
```

### 5.2 平台选择
- 技术 / AI 编程 / Agent 类项目：掘金 + V2EX + 即刻
- AI 出图 / 内容创作 / 知识管理类：小红书 + 掘金 + V2EX
- CLI / 纯程序员工具：掘金 + V2EX + 知乎（可选）

### 5.3 帖子结构
a → b → c → d 四段，顺序不变：

a. 开发背景与痛点（4–6 条，具体真实，读者能对照自己的经历）

b. 核心功能介绍 + 2–3 个截图占位（每个占位写清楚放什么内容、建议尺寸）

c. 实现过程中遇到的技术问题（3–4 个，按「表现 → 原因 → 解决方法 → 经验」写）

d. 结尾：项目已开源，附仓库链接，邀请下载试用和提 issue

### 5.4 语气要求
- 不出现「求 star」「帮点 star」及任何变体，包括 emoji 暗示；出现就重写该段
- 不用广告口吻：「市面上最好的」「秒杀竞品」「全网首发」
- 用个人开发者分享的语气；没做的能力写「下一版本计划支持」，可以如实说明当前缺点

模板见 `templates/share-post-template.md`。

---

## Phase 6 — Skill 打包与自举发布

### 6.1 格式要求
- 标准目录：`.trae/skills/<skill-name>/`
- SKILL.md frontmatter 含 `name` 和 `description`；description 写清做什么、什么时候调用、什么时候不触发
- 可选子目录：`scripts/`（辅助脚本）、`templates/`（模板）、`assets/`（图片示例）

### 6.2 内容检查
- 不包含本地临时路径、真实 token、私有仓库 URL、单次任务的进度记录
- 只保留可复用的流程说明、触发条件、示例和占位符

### 6.3 仓库必备文件
- `LICENSE`（按 Phase 1.2）
- `README.md`：面向使用者，说明价值、安装、配置、兼容范围、数据边界；不复制 Agent 的内部执行步骤，按 Phase 3 的结构写
- `.gitignore`（Python 项目加 `__pycache__/`、`*.pyc`、`.DS_Store`）
- 安装说明同时给两个入口：把仓库地址发给 Agent 安装，以及 `npx skills add <owner>/<repo>`

### 6.4 自举
Skill 仓库推送到 GitHub 后，对本仓库执行一遍 Phase 2 → Phase 4：更新 Description、Website、Topics，确认许可证徽标显示正常，发布 v1.0.0。完成后这个仓库本身就是流程的示范。

---

## 执行清单

| 步骤 | 动作 | 产出 | Done |
|---|---|---|:---:|
| 1 | Phase 1 自查：商标、LICENSE 格式、敏感信息 | 可公开的仓库 | ☐ |
| 2 | Phase 2：Description、Website、Topics 8–12 个 | About 栏完整 | ☐ |
| 3 | Phase 3：README 改写 + 文风检查 | README.md 定稿 | ☐ |
| 4 | Phase 4：v1.0.0 Release + Notes | GitHub Release 页 | ☐ |
| 5 | Phase 5：3 篇分享帖草稿 | tiezi/ 目录 | ☐ |
| 6 | Skill 项目执行 Phase 6 自举 | 公开仓库上线 | ☐ |

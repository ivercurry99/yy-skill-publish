# skill-publish · 把个人小项目发布到公开 GitHub 的 Checklist 与模板

> 一份我整理的逐步执行 Checklist 与 4 份 Markdown 模板，用于在本地项目开发完成后，发布到公开 GitHub。
>
> 内容覆盖商标与许可证自查、About 栏与 Topics 的写法、README 的改写方式、v1.0.0 版本的发布，以及各平台分享帖的起草；按顺序处理即可。

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-win%20%7C%20mac%20%7C%20linux-lightgrey)
![Skill Standard](https://img.shields.io/badge/skill%20format-.trae%2Fskills-blue)

---

## ✨ 核心能力（6 个 Phase 全流程）

| Phase | 内容 | 解决什么痛点 |
|-------|------|-------------|
| 1 · 法律合规体检 | 商标品牌词扫描 + LICENSE 格式校正 + 敏感信息隐私清理 + 免责声明模板 | 发布后收到侵权投诉 / GitHub 不认 License / 泄露 token 后悔 |
| 2 · 仓库包装三件套 | Description「英+中」公式写法 + Website 字段填写 + Topics「4 类 8–12 个」组合公式 | About 栏像三无项目、搜不到、没有 License 徽标 |
| 3 · README 视觉优化 | Hero 首屏 + Badge 三件套 + 截图占位规范 + 安装 3 行法 + 对比表模板 | 访客 3 秒看不懂直接关掉 |
| 4 · Release 发布 | 语义化版本号 v1.0.0 起步 + Release Notes 三段式模板 + 一键命令 | 没有版本号，用户不敢用、没法追踪兼容 |
| 5 · 推广物料生成 | tiezi 目录规范 + 选 3 个平台策略 + a-b-c-d 四段式帖子结构 + 禁直白求 star 红线 | 帖子发了没人看、被平台判广告限流 |
| 6 · Skill 自身打包发布 | .trae/skills/<name>/ 格式校验 + SKILL.md frontmatter 规范 + 自举执行一遍 Phase 2–4 | 技能本身打包不规范，别人装了用不了 |

---

## 🚀 用法

在兼容 `.trae/skills/` 目录结构的 AI 编程助手中：

1. 把这个仓库 clone / 下载到你的项目根目录
2. 确保路径结构是：
   ```
   你的项目/
   └── .trae/
       └── skills/
           └── skill-publish/
               ├── SKILL.md
               └── templates/
                   ├── legal-checklist.md
                   ├── topics-formula.md
                   ├── release-notes-template.md
                   └── share-post-template.md
   ```
3. 当你完成一个可发布的项目时，对 AI 说：**「用 skill-publish 流程把这个项目发布到我的公开 GitHub」** —— AI 会按 Phase 1–6 的清单逐项执行。

---

## 📦 目录结构

```
skill-publish/
├── LICENSE                                 MIT License
├── README.md                               你现在看的这个文件
├── SKILL.md                                技能主文件（含 frontmatter + 6 个 Phase 完整正文）
└── templates/
    ├── legal-checklist.md                  法律合规体检 Checklist（5 大类 20+ 条）
    ├── topics-formula.md                   GitHub Topics 8–12 个组合公式 + 3 个真实示例
    ├── release-notes-template.md           Release Notes v1.0.0 三段式 Markdown 模板
    └── share-post-template.md              掘金/V2EX/小红书/即刻 分享帖 a-b-c-d 四段式模板
```

---

## ⚠️ 铁律红线（违反则整个流程作废）

1. **商标**：不要把 `ChatGPT` / `抖音` / `GitHub Logo` / `Octocat` 等注册商标或官方图形直接当自己项目名/装饰图用
2. **Topics 字符**：只能用小写字母/数字/`-`，不能中文、不能大写、不能空格 —— 错一个服务器直接 403
3. **分享帖禁直白求 star**：任何变体都不行（含 emoji 暗示 🥺👉👈），违者整篇重写
4. **首次 Release 版本固定 v1.0.0**：0.x.x 让用户觉得不稳定；不打 Tag = 没有正式版本

---

## 项目声明

本技能仅封装「自己个人项目发布的标准操作流程」本身。流程内容、模板、Checklist 均为原创整理，不引用任何第三方实现细节或品牌标识。

### 免责声明
本项目仅供学习与个人工作流提效之用。提供的流程和模板按"原样"发布，不对任何形式的直接或间接损失承担责任。使用者需自行确保调用相关外部服务时遵守其服务条款与当地法律法规。

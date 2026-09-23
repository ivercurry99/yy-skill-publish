# skill-publish · 把个人小项目发布到公开 GitHub 的 Checklist 与模板

> 一份我整理的逐步执行 Checklist 与 4 份 Markdown 模板，用于在本地项目开发完成后，发布到公开 GitHub。
>
> 内容覆盖商标与许可证自查、About 栏与 Topics 的写法、README 的改写方式、v1.0.0 版本的发布，以及各平台分享帖的起草。

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-win%20%7C%20mac%20%7C%20linux-lightgrey)
![Skill Standard](https://img.shields.io/badge/skill%20format-.trae%2Fskills-blue)

---

## 这是什么

本地项目写完之后，从「能跑」到「别人能在 GitHub 上找到、看懂、装上」之间有一段固定要做的事：检查商标和许可证、填 About 栏、选 Topics、改 README、打版本号、写分享帖。这套流程把它们整理成 6 个阶段，每一步有具体的检查项、命令和模板，直接照着执行。

## 6 个阶段

| 阶段 | 做什么 | 产出 |
|---|---|---|
| 1 法律与合规自查 | 商标品牌词扫描、LICENSE 格式、敏感信息清理 | 可以直接公开的仓库 |
| 2 About 栏与 Topics | Description 写法、Website 填写、Topics 组合 | About 栏信息完整 |
| 3 README 改写 | 首屏结构、Badge、截图、安装说明、对比表、文风检查 | README.md 定稿 |
| 4 Release 发布 | 版本号规则、Release Notes 写法、发布命令 | GitHub Release 页 |
| 5 分享帖草稿 | 平台选择、帖子结构、语气要求 | 3 篇 Markdown 帖 |
| 6 Skill 打包 | 目录格式、SKILL.md 规范、自举检查 | 公开仓库上线 |

完整流程见 [SKILL.md](./SKILL.md)。

## 安装

方式 1：把仓库地址发给支持 Skill 的 Agent：

```text
帮我安装 https://github.com/ivercurry99/skill-publish 这个 Skill。
```

方式 2：命令行安装：

```shell
npx skills add ivercurry99/skill-publish
```

方式 3：手动克隆到技能目录：

```shell
git clone https://github.com/ivercurry99/skill-publish.git .trae/skills/skill-publish
```

## 使用

安装后，项目写完准备公开时对 Agent 说：

```text
用 skill-publish 流程把这个项目发布到我的公开 GitHub。
```

Agent 会按 SKILL.md 的 6 个阶段逐项执行：合规自查 → About 栏与 Topics → README 改写 → Release → 分享帖 →（Skill 项目）自举发布。

## 目录结构

```text
skill-publish/
├── LICENSE                    MIT License
├── README.md                  本文件
├── SKILL.md                   技能主文件（6 个阶段全文）
└── templates/
    ├── legal-checklist.md        合规自查清单（5 大类 20+ 条）
    ├── topics-formula.md         Topics 组合公式与 3 个示例
    ├── release-notes-template.md  Release Notes 模板
    └── share-post-template.md    分享帖四段式模板
```

## 注意事项

1. 商标：ChatGPT、抖音、GitHub Logo、Octocat 等注册商标和官方图形不用作项目名或装饰图
2. Topics 字符：只能用小写字母、数字、单个连字符；含中文、大写或空格的标签会被 GitHub 拒绝
3. 分享帖不出现「求 star」类表述，包括 emoji 暗示；出现就重写该段
4. 首次 Release 用 v1.0.0，并勾选 latest

## 兼容范围与数据边界

技能面向使用 `.trae/skills/` 目录结构的 AI 编程助手（TRAE 等）。SKILL.md 中的流程本身不依赖特定宿主，其他 Agent 可以直接读取 SKILL.md 按文档执行。

配置：技能本身不需要模型 API Key，也不读写本地私人数据；发布命令依赖 GitHub CLI（`gh`），使用前执行一次 `gh auth login` 完成认证，除此之外无需额外配置。

## 项目声明

本技能封装的是个人项目发布的标准操作流程。流程内容、模板、Checklist 为原创整理，不引用第三方实现细节或品牌标识。

### 免责声明

本项目仅供学习与个人工作流提效之用。提供的流程和模板按"原样"发布，不对任何形式的直接或间接损失承担责任。使用者需自行确保调用相关外部服务时遵守其服务条款与当地法律法规。

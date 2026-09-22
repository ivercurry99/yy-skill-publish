# GitHub Topics 组合公式 · 8–12 个标签

## 字符规则（不符合会被拒绝）

GitHub 只接受以下字符，其他写法提交时会失败：
- 允许：小写字母 `a-z`、数字 `0-9`、单个连字符 `-`
- 禁止：中文、大写字母、空格、下划线 `_`、点 `.`、开头或结尾用 `-`
- 长度：每个标签 35 字符以内
- 输入框用英文逗号 `,` 分隔：`python,second-brain,obsidian`

---

## 4 类搭配公式

| 类别 | 数量 | 作用 | 判断标准 |
|------|------|------|---------|
| 大分类技术栈 | 3–4 个 | 让搜「python」「cli」这类大类词能命中 | 换成任何同类项目都成立 |
| 业务场景 | 3–5 个 | 让搜「第二大脑用什么工具」这类问题能命中 | 是用户搜索时会想到的词，不是项目内部代号 |
| 热门高频 | 2–3 个 | GitHub 上使用量大、带来自然流量的标签 | 在 GitHub Topics 搜索框输入时自动补全排名靠前 |
| 小众 niche | 1–2 个 | 精准人群、竞争少 | 同行才知道的方法论/协议/特定名词 |

合计 8–12 个，每类至少 1 个；缺一类就失去对应的搜索入口。

---

## 3 个示例

### 示例 A：第二大脑知识库项目（11 个）
| 类别 | 标签 | 为什么选 |
|------|------|---------|
| 大分类技术栈 | `python` `cli` `markdown` | 用 Python 写、命令行运行、产物是 Markdown |
| 业务场景 | `second-brain` `knowledge-management` `note-taking` `pkm` `personal-knowledge-base` | 用户搜「个人知识管理/第二大脑/记笔记」的入口词 |
| 热门高频 | `obsidian` `zettelkasten` `agent-skill` | Obsidian 生态标签，zettelkasten 是方法论大标签 |
| 小众 niche | `para-method` `productivity` | PARA 是 Tiago Forte 提出的分层法，受众精准 |

### 示例 B：多 Agent 代码生成项目（11 个）
| 类别 | 标签 | 为什么选 |
|------|------|---------|
| 大分类技术栈 | `python` `workflow-automation` `code-generation` `harness` | Python 编写、自动化流程、生成代码 |
| 业务场景 | `llm-agent` `ai-coding-assistant` `multi-agent` `scaffolding` | 用户搜 AI 编码助手/脚手架的高频词 |
| 热门高频 | `agent-skill` `prompt-engineering` | 使用量较大的社区标签 |
| 小众 niche | `vibe-coding` | 该人群使用的特定说法 |

### 示例 C：小红书 AI 出图项目（12 个）
| 类别 | 标签 | 为什么选 |
|------|------|---------|
| 大分类技术栈 | `python` `text-to-image` `stable-diffusion` `ai-image-generation` | 出图类目的大分类词 |
| 业务场景 | `xiaohongshu` `little-red-book` `social-media-content` `ai-content-creation` | 中英双语覆盖两个搜索入口 |
| 热门高频 | `dalle3` `flux` `prompt-engineering` | 出图模型和提示词工程的常用标签 |
| 小众 niche | `seedream` | 特定供应商名称，抓精准搜索 |

---

## 自检 5 问（贴之前过一遍）

1. 有没有中文或大写标签？有就换成合法写法
2. 有没有和项目完全无关的凑数热门词？与项目无关的标签会降低整体标签的可信度
3. 4 类齐全吗？每类至少 1 个
4. 最想被搜到的核心词在第 1 梯队吗？核心词不要被挤掉
5. 数量在 8–12 吗？太少入口不足，太多会稀释权重

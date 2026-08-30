# GitHub Topics 组合公式 · 8–12 个标签一键配置

## 字符硬规则（错一个就 403）

GitHub 官方只接受以下字符，**其他任何写法都会被服务器拒绝**：
- 允许：**小写字母** `a-z`、**数字** `0-9`、**单个连字符** `-`
- 禁止：中文、大写字母、空格、下划线 `_`、点 `.`、开头/结尾用 `-`
- 长度：每个 tag 35 字符以内
- 输入框里用英文逗号 `,` 分隔：`python,second-brain,obsidian`

---

## 4 类搭配公式（每个项目都按这个配比凑）

| 类别 | 数量 | 作用 | 判断标准 |
|------|------|------|---------|
| ① 大分类技术栈 | 3–4 个 | 让搜"python" "cli" 这种大类词能命中 | 换成任何项目同类语言/范式都成立 |
| ② 业务场景 | 3–5 个 | 让搜"我做第二大脑用什么"能命中 | 必须是"用户搜的时候脑子里会出现的词"，不是你的内部代号 |
| ③ 热门高频 | 2–3 个 | GitHub 自带流量池的标签，最多人订阅 | 在 GitHub Topics 搜索框里输入时自动补全排名靠前 |
| ④ 小众 niche | 1–2 个 | 精准人群、竞争少，**转化率最高** | 同行才知道的黑话/方法论/特定协议名 |

合计：**8–12 个**，每个维度都要有，**缺 1 类就直接让那部分搜索流量永远 0**。

---

## 3 个真实落地示例（照抄的作业）

### 示例 A：第二大脑知识库项目（11 个）
| 类别 | 标签 | 为什么选 |
|------|------|---------|
| ① 大分类技术栈 | `python` `cli` `markdown` | 用 Python 写、命令行跑、产物全是 Markdown |
| ② 业务场景 | `second-brain` `knowledge-management` `note-taking` `pkm` `personal-knowledge-base` | 用户搜"个人知识管理/第二大脑/记笔记"时的入口词 |
| ③ 热门高频 | `obsidian` `zettelkasten` `agent-skill` | Obsidian 是当前第二大脑生态最大 App，zettelkasten 是方法论大号标签，agent-skill 是新趋势流量池 |
| ④ 小众 niche | `para-method` `productivity` | PARA 是 Tiago Forte 提出的经典分层法，精准受众 |

### 示例 B：多 Agent 代码生成项目（11 个）
| 类别 | 标签 | 为什么选 |
|------|------|---------|
| ① 大分类技术栈 | `python` `workflow-automation` `code-generation` `harness` | Python 写、自动化工作流、生成代码、工作流框架（harness 是新兴大类） |
| ② 业务场景 | `llm-agent` `ai-coding-assistant` `multi-agent` `vibe-coding` `scaffolding` | 真实用户搜"用一句话 vibe coding 生成项目"的高频词 |
| ③ 热门高频 | `agent-skill` `prompt-engineering` | 2025 年 GitHub 涨幅最高的两个标签之一 |
| ④ 小众 niche | `agent-skill` 已算跨类 → 可补 `code-generation` 做交叉 |  |

### 示例 C：小红书 AI 出图项目（12 个）
| 类别 | 标签 | 为什么选 |
|------|------|---------|
| ① 大分类技术栈 | `python` `text-to-image` `stable-diffusion` `ai-image-generation` | 4 个最大的出图分类词 |
| ② 业务场景 | `xiaohongshu` `little-red-book` `social-media-content` `ai-content-creation` `seedream` `prompt-engineering` | xiaohongshu/little-red-book 中英双语抓两个搜索入口，seedream 抓供应商搜索流量 |
| ③ 热门高频 | `dalle3` `flux` `prompt-engineering` | DALL·E 3 / FLUX 是 2024–2025 最火出图模型 tag |
| ④ 小众 niche | `seedream` 已经算 niche → 不用再加，总量刚好 12 |  |

---

## 自检 5 问（贴完问一遍自己）

1. [ ] **有没有中文 tag？** → 如果有，立刻换英文合法写法（用"中文"这个词作为 tag 就是非法）
2. [ ] **有没有 100% 不是自己项目领域的"凑数热门词"？** → 别为了蹭流量把 `web3` `blockchain` 乱加，GitHub 算法会把你判定为垃圾号降权
3. [ ] **4 类齐全吗？** → 技术栈/场景/热门/小众每类至少 1 个
4. [ ] **最想被搜到的那个词有没有放在第 1 梯队？** → 比如小红书项目必须有 `xiaohongshu`，不要把 niche 词放满把核心词挤没
5. [ ] **数量 8–12 吗？** → 少于 6 = 流量入口太少；多于 15 = 标签稀释 + GitHub 内部权重降低

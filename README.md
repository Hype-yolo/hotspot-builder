# Hotspot Builder

**告诉 Agent 你想做什么行业的热点站，让它先问清需求，再基于 AIHOT 完成开发。**

一个可安装的 Agent Skill，由 Hype 整理。适合想做 AI、法律、跨境、电商等行业资讯网站，但不想先研究整套技术栈的人。

它会指导有代码和终端能力的 Agent 复用 [AIHOT](https://github.com/KKKKhazix/AIHOT) 的采集、筛选、两次评分、事件归组、热度、日报与管理后台，再替换成你的读者、信源、标准和品牌。

## 安装

在准备用来建站的工作目录打开终端，运行：

```bash
npx -y skills add Hype-yolo/hotspot-builder
```

按安装器提示选择你的 Agent。需要 Node.js/npm 才能运行此命令。

为 Codex 和 Claude Code 直接安装到当前项目：

```bash
npx -y skills add Hype-yolo/hotspot-builder --skill hotspot-builder --agent codex claude-code -y
```

需要在所有项目中使用时，可在命令末尾增加 `-g`。安装完成后，若当前会话没有识别到新 Skill，重新开启一个会话。

## 怎么用

在支持 `$skill-name` 的 Agent 中发送：

```text
$hotspot-builder

我想做一个给跨境卖家看的行业热点网站，
重点关注平台规则、政策变化和有用的运营工具。
我不懂技术，请先问我必要的问题，再帮我做出来。
```

Claude Code 等支持斜杠调用的宿主可使用 `/hotspot-builder`。也可以明确说「使用 hotspot-builder 帮我建站」，具体调用方式以宿主为准。

已有项目也可以继续：

```text
使用 hotspot-builder 继续改造当前 AIHOT 项目。
我们已经确定面向独立开发者，保留现有信源和品牌。
请先检查当前实现，再补齐事件归组和真实数据验证。
```

## 它会问什么

每轮最多 5 个问题，已经回答过的不再问：

1. 网站给谁看？最想帮助读者解决什么问题？
2. 想叫什么名字，关注哪些来源？
3. 哪些消息值得推荐，哪些属于噪声？
4. **你想要做出的网站还要包括什么？**
5. 先在本地运行还是部署？已有模型服务和多少试运行预算？

你可以回答「暂时没有」「先默认」「你建议一个方案」。Agent 会先完成不依赖缺失条件的部分，再在真正需要密钥、预算或公开部署时落实条件。

## 做出来的是什么

```mermaid
flowchart LR
  A[信源采集] --> B[预筛与两次评分]
  B --> C[标题摘要与结构化]
  C --> D[事实和事件归组]
  D --> E[热度与刊物]
  E --> F[网站 / RSS / API / MCP]
```

- **网站**：精选、全部动态、热点、事件详情、主题、搜索和刊物，按需求增删。
- **后台**：信源管理、处理诊断、模型配置、回执用量、预算、人工修正和评测。
- **后端**：API 和 worker 分工，PostgreSQL 保存结果与任务，浏览页面读取已处理内容。
- **行业配置**：站名、分类、信源、评分品味、写作要求和品牌归到 `industry/`。
- **交付**：实际代码、本地运行、必要测试、配置说明，以及已授权的部署。

Agent 优先改造原仓库，保留其架构和提示词契约。源项目需要的 Docker、Node.js、数据库等条件，会在建站阶段检查，不会因安装 Skill 就自动安装或运行服务器。

## 使用条件和边界

- 需要能够读写项目、运行命令和获取 GitHub 源码的开发 Agent；普通纯聊天模式不能独立完成部署。
- 真实资讯处理需要你配置模型 API；完整向量召回需要 Embedding 接口。X、公众号等部分来源另有服务要求。
- API Key 通过私有配置输入，Skill 不需要你在公开聊天或仓库里粘贴密钥。
- 安装 Skill 不会自动采集、调用模型、购买云资源或发布网站。真实试运行和部署按你的范围与预算执行。
- Skill 提供工作方法与验收要求；模型效果仍需真实样本校准，不能承诺任何 Agent 一次调用都能无误完成整站。

## 文件结构

```text
skills/hotspot-builder/
├── SKILL.md                  # 按当前进度执行的入口
├── agents/openai.yaml        # Codex 展示与默认调用提示
└── references/
    ├── interview.md         # 分轮需求问答
    ├── architecture.md      # 上游复用与行业改造
    ├── editorial.md         # 评分、写作、归组、热度和刊物
    ├── delivery.md          # 模型、预算、验证与部署
    └── provenance.md        # 来源和许可
```

长说明按需读取，使用者无需把一份完整建站提示词反复复制进聊天。

## 来源与许可

本 Skill 基于对 [KKKKhazix/AIHOT](https://github.com/KKKKhazix/AIHOT) 的公开代码、文档和生产提示词分析整理。参考快照为 `8d5a39bb47c917616798a3fdd71688a80f6c9b6c`，核对日期 2026-10-01；实际开发以选定版本源码为准。

这是 Hype 整理的独立 Skill，不是 AIHOT 官方项目，也不是作者原始开发聊天记录。网站框架和生产提示词的原作者为数字生命卡兹克；新网站应使用自己的名称和标志。

本仓库采用 [MIT License](LICENSE)。改编参考资料的原许可随 Skill 保存在 [来源与许可](skills/hotspot-builder/references/provenance.md) 中。

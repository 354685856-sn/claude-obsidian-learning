# Claude + Obsidian 集成项目学习索引

**学习时间**: 2026-04-08
**学习者**: 楠哥 (354685856-sn)
**已关注作者**: YishenTu, heyitsnoah, ballred, coleam00
**已 Star 项目**: 7 个

---

## 🌟 高价值项目 (1000+ stars)

### 1. [YishenTu/claudian](https://github.com/YishenTu/claudian) - 6308⭐
**定位**: Obsidian 插件嵌入 AI coding agents
**核心能力**:
- ChatSidebar + Inline Edit 原地编辑
- @mention 文件/Agent/MCP
- Plan Mode 先设计后执行
- 支持 Claude Code 和 Codex

**学习要点**:
- Obsidian 插件架构
- Claude Code SDK 集成
- MCP 服务器管理

---

### 2. [heyitsnoah/claudesidian](https://github.com/heyitsnoah/claudesidian) - 2119⭐
**定位**: 预制 Obsidian vault 结构
**核心能力**:
- GitHub Actions 自动同步
- 预制 skills 和 agents
- Issues/PRs 中 @claude 触发

**学习要点**:
- Vault 结构设计
- GitHub Actions 集成

---

### 3. [ballred/obsidian-claude-pkm](https://github.com/ballred/obsidian-claude-pkm) - 1318⭐
**定位**: AI 问责系统（Cascade 目标管理）
**核心能力**:
- 3-Year Vision → Daily Tasks 层级连接
- `/daily`, `/weekly`, `/monthly`, `/project` 技能系统
- 4 个专属 Agent（goal-aligner, weekly-reviewer 等）
- `/adopt` 扫瞄现有 vault 自动适配

**学习要点**:
- Cascade 目标管理架构
- Agent 跨会话记忆
- Zero dependencies 设计哲学

---

## 💡 中价值项目 (100-1000 stars)

### 4. [coleam00/second-brain-starter](https://github.com/coleam00/second-brain-starter) - 308⭐
**定位**: AI 第二大脑 PRD 生成器
**核心能力**:
- 用户需求模板 → 个性化 PRD
- 9 阶段构建计划
- SOUL.md + USER.md + MEMORY.md 记忆层
- 心跳系统（$0.05/次低成本）

**学习要点**:
- PRD 生成器模式
- 主动性级别设计
- 低成本心跳架构

---

### 5. [coleam00/claude-memory-compiler](https://github.com/coleam00/claude-memory-compiler) - 279⭐
**定位**: Karpathy 风格知识编译器
**核心能力**:
- `daily/` → `knowledge/` 自动编译
- `index.md` 主目录 + `log.md` 构建日志
- `concepts/` + `connections/` + `qa/` 三分离
- Lint 健康检查（7 项）
- 无 RAG 查询（LLM 智能选择文章）

**学习要点**:
- Karpathy LLM Knowledge Base 架构
- 编译器类比设计
- Lint 健康检查实现

---

### 6. [iansinnott/obsidian-claude-code-mcp](https://github.com/iansinnott/obsidian-claude-code-mcp) - 233⭐
**定位**: MCP 协议连接 Obsidian
**核心能力**:
- Model Context Protocol 集成
- Claude Desktop 连接
- AI 驱动 vault 交互

**学习要点**:
- MCP 协议实现
- Claude Desktop 集成

---

### 7. [crimeacs/claude-note](https://github.com/crimeacs/claude-note) - 41⭐
**定位**: 后台服务同步 Claude 会话到 Obsidian
**核心能力**:
- 后台监控 Claude 会话
- 自动合成关键决策和教训
- 结构化笔记输出

**学习要点**:
- 后台服务架构
- 会话摘要生成

---

## 📊 架构对比表

| 项目 | 集成方式 | 记忆系统 | 特色功能 |
|------|----------|----------|----------|
| Claudian | Obsidian 插件 | 依赖原生 | Inline Edit, @mention |
| Claudesidian | Vault 结构 | 原生 | GitHub Actions |
| obsidian-claude-pkm | Skills | Agent 记忆 | Cascade 目标 |
| second-brain-starter | PRD 生成器 | SOUL/USER/MEMORY | 心跳系统 |
| claude-memory-compiler | 知识编译 | daily→knowledge | Lint 检查 |
| obsidian-mcp | MCP 协议 | 原生 | Model Context Protocol |
| claude-note | 后台服务 | Obsidian 同步 | 自动摘要 |

---

## 🔗 已保存的深入学习文档

- [obsidian-claude-integration-patterns.md](./.claude/memory/obsidian-claude-integration-patterns.md) - 5 种集成模式详解
- [Claude-Code-Complete-Architecture.canvas](./docs/architecture/Claude-Code-Complete-Architecture.canvas) - 完整架构画布

---

## 📝 下一步行动

1. **借鉴 Cascade 目标系统** → 创建楠哥的目标→项目→日常连接
2. **实现知识编译器** → 将 daily 对话自动编译为 knowledge
3. **开发 Lint 工具** → 健康检查记忆系统
4. **创建专属 Agent** → goal-aligner, weekly-reviewer
5. **实现心跳系统** → 每日主动提醒和反思

---

*此索引由 cc 自动维护和更新*

---

## 🎓 Thariq Shihipar - Claude Code 团队核心成员

**Thariq Shihipar** 是 Anthropic Claude Code 团队的 Member of Technical Staff，他分享了构建 Claude Code 的核心经验：

### 已关注
- LinkedIn: [thariqshihipar](https://www.linkedin.com/in/thariqshihipar)
- Twitter/X: [@trq212](https://x.com/trq212)

### 核心文章系列："Lessons from Building Claude Code"

1. **Prompt Caching Is Everything** (2026-02-19)
   - 缓存输入令牌便宜 10 倍
   - 缓存命中率下降 = 生产事件（SEV）
   - 7 条架构经验

2. **How We Use Skills** (2026-03-17)
   - Anthropic 内部使用数百个 Skills
   - 9 大 Skills 类型
   - 5 条核心经验

3. **Seeing like an Agent** (2026-02-27)
   - 行动空间（action space）设计
   - 渐进式披露用于工具发现

---

*最后更新：2026-04-08 - 已学习 Thariq Shihipar 文章并保存记忆*

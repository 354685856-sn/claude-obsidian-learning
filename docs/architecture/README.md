# Claude Code 架构文档索引

本目录包含 Claude Code 架构的详细文档，配合 Obsidian 画布使用。

## 核心文档

### 端到端流程
- [end_to_end_workflow.md](end_to_end_workflow.md) - 从用户输入到记忆落盘的完整生命周期

### 宿主工程
- [harness_engine_architecture.md](harness_engine_architecture.md) - Harness 运行时宿主工程全景

### 入口引导
- [entrypoint_architecture.md](entrypoint_architecture.md) - CLI 入口与命令分发

### 环境感知
- [context_architecture.md](context_architecture.md) - Git 状态注入与系统上下文

### 上下文压缩
- [compact_architecture.md](compact_architecture.md) - 三级防爆体系

### 推理主循环
- [query_architecture.md](query_architecture.md) - 主推理循环与工具调用编排
- [QueryEngine_architecture.md](QueryEngine_architecture.md) - QueryEngine 职责与状态流转

### 工具系统
- [Tool_architecture.md](Tool_architecture.md) - 工具插槽、权限拦截与执行沙盒
- [permissions_architecture.md](permissions_architecture.md) - 安全边界设计

### 记忆系统
- [sessionMemory_architecture.md](sessionMemory_architecture.md) - 会话级临时记忆
- [extractMemories_architecture.md](extractMemories_architecture.md) - 跨会话长期记忆
- [extractMemories_prompts_architecture.md](extractMemories_prompts_architecture.md) - 记忆提取提示词

### 扩展系统
- [hooks_architecture.md](hooks_architecture.md) - Hook 机制与扩展触发点
- [mcp_architecture.md](mcp_architecture.md) - MCP 外部能力接入层
- [prompts_architecture.md](prompts_architecture.md) - 系统提示词与上下文组织

## Obsidian 画布

- [Claude-Code-Complete-Architecture.canvas](Claude-Code-Complete-Architecture.canvas) - **完整架构图谱**（推荐）
- [架构可视化.canvas](架构可视化.canvas) - 基础架构概览

## 推荐阅读顺序

1. 先看画布 [Claude-Code-Complete-Architecture.canvas](Claude-Code-Complete-Architecture.canvas) 建立全局视图
2. 阅读 [end_to_end_workflow.md](end_to_end_workflow.md) 理解完整流程
3. 阅读 [harness_engine_architecture.md](harness_engine_architecture.md) 理解宿主工程
4. 按模块深入各专题文档

## 参考资源

- 非官方学习仓库：https://github.com/miaomiaomiao1113/claude-code-architecture-instruction
- 本仓库基于 CC BY 4.0 许可证

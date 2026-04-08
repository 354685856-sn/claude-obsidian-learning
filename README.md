# Claude Code 架构学习项目

**作者**: 楠哥 (354685856-sn)

本项目包含对 Claude Code 架构的深度学习和分析，基于 miaomiaomiao1113 的架构分析 + 本地部署实践。

## 项目内容

### 1. 完整架构图谱
- [Obsidian 画布](./docs/architecture/Claude-Code-Complete-Architecture.canvas) - 结合原始架构分析与本地实践的完整图谱
- 涵盖：终端输入 → 命令分发 → 环境感知 → 上下文压缩 → 大模型推理 → 工具执行 → 多轮对话 → 记忆保存

### 2. 核心架构文档
- 端到端流程
- 宿主工程架构
- 三级防爆体系
- 记忆系统（会话级 + 跨会话）
- 权限路由引擎
- MCP 协议层

### 3. 学习笔记
- [架构学习笔记](./docs/study-notes.md) - 核心概念总结

## 快速开始

1. 使用 Obsidian 打开 `docs/architecture/Claude-Code-Complete-Architecture.canvas`
2. 阅读 [架构文档索引](./docs/architecture/README.md)
3. 按推荐顺序深入学习各模块

## 核心概念

### 洋葱模型
```
最内层：query.ts → 直接与 API 对话
中间层：Tool + compact → 手脚 + 防爆
外围层：QueryEngine + Hooks → 生命周期管理
最外层：CLI + context → 入口感知
```

### 三大设计哲学
1. **洋葱模型** - 层层包裹大模型
2. **防御性设计** - 贯穿始终的三重保护
3. **异步影子系统** - 后台并发不阻塞

## 许可证

CC BY 4.0

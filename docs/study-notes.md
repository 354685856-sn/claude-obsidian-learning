# Claude Code 架构学习笔记

**学习时间**: 2026-04-08
**资料来源**: https://github.com/miaomiaomiao1113/claude-code-architecture-instruction

---

## 核心架构理解

### 1. Harness 工程架构

**Harness = 除了大模型本身之外的一切工程代码**

它是将 Claude 从"只会聊天的嘴"变成"有手有脚有记忆的 Agent"的完整脚手架。

#### 洋葱模型（层层包裹大模型）

```
最内层：query.ts → 直接与 API 对话
中间层：Tool + compact → 手脚 + 防爆
外围层：QueryEngine + Hooks → 生命周期管理
最外层：CLI + context → 入口感知
```

#### 三大设计哲学

1. **洋葱模型** - 层层包裹大模型
2. **防御性设计** - 贯穿始终的三重保护
3. **异步影子系统** - 后台并发不阻塞

---

### 2. 七大阶段端到端流程

| 阶段 | 模块 | 职责 |
|------|------|------|
| 1 | entrypoints/cli.tsx | 终端接收与命令分发 |
| 2 | context.ts & QueryEngine | 环境感知与物理世界挂载 |
| 3 | compact/ | 提示词预检与缓存折叠 |
| 4 | query.ts | 大模型推理主循环 |
| 5 | Tool.ts / Permissions | 工具审查与沙盒执行 |
| 6 | query.ts (stop_reason) | 多轮缠斗与主动完结 |
| 7 | Post Sampling Hooks | 背景幽灵善后（记忆保存） |

---

### 3. 核心模块详解

#### query.ts - 流式状态机（发动机）

- `async function*` 流式生成器
- `while(true)` 无限状态机循环
- 流式 Streaming 逐字 yield 给终端
- tool_use → 工具分发 → tool_result 回填
- 超 Token 自动续写（无损拼接 8K+）
- Error Recovery 自愈式韧性设计

#### Tool.ts - 工具插槽系统

- `inputSchema` - Zod 参数声明
- `isDestructive()` - 破坏性标记
- `checkPermissions()` - 运行时拦截
- UI 渲染钩子自描述

#### compact/ - 三级防爆体系

| 级别 | 模块 | 策略 |
|------|------|------|
| 第一级 | microCompact.ts | 时间断层清理旧工具结果 |
| 第二级 | sessionMemoryCompact.ts | 读取磁盘摘要，0 延迟注射 |
| 第三级 | compact.ts (Legacy) | 核弹级推倒重来 |

#### 双记忆系统

**Session Memory（会话级临时记忆）**
- 监控 Token 和工具调用阈值
- 后台 Fork 子代理总结
- 写入 SESSION_MEMORY.md
- 供 compact 第二级复用

**Extract Memories（跨会话持久记忆）**
- 会话结束后提炼项目经验
- 写入 `~/.claude/projects/.../memory/`
- 两阶索引：内容卡片 + MEMORY.md
- 60 秒宽限期抗 Ctrl+C

---

### 4. 权限路由引擎

```
YOLO 模式 → 自动放行
    ↓
yoloClassifier → 语义风险打分
    ↓
allow / deny / ask 三级决策
    ↓
紧急刹车安全网
```

---

### 5. 学习心得

1. **工程师思维的架构防御** - 不是粗暴切片，而是立体防缓存穿透阶梯网
2. **异步非阻塞的影子系统** - 用户感知丝滑，暗处大量"家务活"
3. **零信任权限锁死** - 后台子代理只能编辑指定文件
4. **Prompt Cache 寄生复用** - 节约 Token 费用

---

*笔记基于 CC BY 4.0 许可证*

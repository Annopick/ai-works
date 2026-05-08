## Engineering技能使用指引

### 前置配置（仅首次）

| 技能 | 触发场景 | 说明 |
|------|---------|------|
| `setup-matt-pocock-skills` | 首次使用工程技能前 | 配置issue tracker、triage标签、domain docs路径。`to-issues`/`to-prd`/`triage`/`diagnose`/`tdd`/`improve-codebase-architecture`/`zoom-out` 均依赖此配置 |

### 规划阶段

| 技能 | 触发场景 | 说明 |
|------|---------|------|
| `to-prd` | 将对话上下文固化为PRD | 从当前讨论和代码探索中提炼PRD，发布到issue tracker（标记ready-for-agent） |
| `to-issues` | 将PRD/计划拆分为任务 | 按垂直切片拆分为可独立执行的问题，每个切片穿透所有层（schema→API→UI→test） |
| `prototype` | 不确定设计是否可行时 | 快速构建丢弃原型验证数据模型/状态机（终端交互）或UI方案（多风格切换） |
| `grill-with-docs` | 对方案进行严格质询 | 逐项挑战你的决策树，用现有领域模型和ADR交叉验证，同步更新CONTEXT.md |

### 执行阶段

| 技能 | 触发场景 | 说明 |
|------|---------|------|
| `tdd` | 实现功能或修复bug | 红-绿-重构循环。每次只写一个测试，垂直切片推进。测试只验证公共接口行为，不耦合实现细节 |
| `diagnose` | 遇到困难bug或性能回退 | 构建反馈循环→重现→排名假设→逐个验证→修复+回归测试→清理+复盘。**没有反馈循环不推进** |

### 优化阶段

| 技能 | 触发场景 | 说明 |
|------|---------|------|
| `improve-codebase-architecture` | 发现架构摩擦、重构需求 | 识别浅模块（接口≈实现），发现深化机会，提升可测试性和AI可导航性。用删除测试衡量模块价值 |
| `zoom-out` | 对某段代码不熟悉 | 请求宏观视角，给出相关模块和调用方的全景图 |

### 项目管理

| 技能 | 触发场景 | 说明 |
|------|---------|------|
| `triage` | 管理问题、审视bug/需求 | 通过状态机驱动问题流转：needs-triage → needs-info → ready-for-agent → ready-for-human / wontfix |

### 典型工作流

```
新功能：to-prd → to-issues → prototype（可选）→ tdd → improve-codebase-architecture（可选）

修Bug：triage → diagnose → tdd（写回归测试）

设计验证：grill-with-docs → prototype → 根据结果决定下一步
```

### 关键原则

- **先规划后执行**：任何非琐碎任务从规划技能开始，避免无头绪探索
- **垂直切片优先**：`tdd`和`to-issues`都要求垂直穿透而非水平铺开
- **不推进无反馈循环**：`diagnose`的核心纪律——没有可复现的pass/fail信号，绝不进入假设阶段
- **公共接口即测试面**：`tdd`和`improve-codebase-architecture`共享这条原则——好的接口产生好的测试
- **领域语言即命名来源**：所有技能输出的命名、术语、模块名称必须从CONTEXT.md中取词，保持一致性

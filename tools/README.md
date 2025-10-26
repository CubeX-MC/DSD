# DSD 工具使用指南

本目录包含使用 DSD 框架的工具和模板。

## 📁 文件说明

- **prompts.md** - 完整的四个 Prompt 模板（A/B/C/D）
- **iteration_template.md** - 迭代记录模板

## 🚀 快速开始

### 步骤 1：准备您的核心目标

在开始使用 Prompt 之前，明确您的服务器目标。例如：

```yaml
CoreGoals:
  1: 高玩家留存率（月留存 > 60%）
  2: 高社区和谐度（玩家满意度 > 7/10）
  3: 低管理负担（每周管理时间 < 5小时）
```

### 步骤 2：描述当前状态

详细描述您的服务器"物质基础"：

```yaml
CurrentState:
  version: "原版生存 1.20.1"
  plugins:
    - GriefPrevention（领地保护）
    - EssentialsX（基础指令）
  player_count: 15
  server_age: "2个月"
  community_structure: "3-4个小团体，1个公共出生点"
```

### 步骤 3：使用 Prompt

1. 将 `prompts.md` 中的 **Prompt A** 复制到您的 LLM（如 ChatGPT、Claude）
2. 填入您的 `{CoreGoals}` 和 `{CurrentState}`
3. 获得输出后，依次使用 Prompt B、C、D

### 步骤 4：记录迭代

使用 `iteration_template.md` 记录每次迭代的结果，便于追溯和学习。

## 许可证

本目录下所有文件采用 GPL-3.0 许可。

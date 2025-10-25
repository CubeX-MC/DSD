# DSD 工具使用指南

本目录包含使用 DSD 框架的工具和模板。

## 📁 文件说明

- **prompts.md** - 完整的四个 Prompt 模板（A/B/C/D）
- **iteration_template.md** - 迭代记录模板
- **data_collection_guide.md** - 数据收集指南（计划中）
- **dsd_agent.py** - 自动化脚本（计划中）

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

## 📊 推荐的 LLM

- **GPT-4 / GPT-4o**：逻辑推理强，适合 Prompt A 和 B
- **Claude 3.5 Sonnet**：擅长结构化输出，适合 Prompt C
- **免费替代**：Gemini 1.5 Pro（需要调整 Prompt 格式）

## 🛠️ 高级用法

### 使用自动化脚本（计划中）

我们正在开发 `dsd_agent.py`，将自动化以下流程：

```bash
# 安装依赖
pip install openai anthropic pyyaml

# 运行迭代
python dsd_agent.py --config my_server.yaml --iteration 0

# 输出：自动生成推论、矛盾、方案的 Markdown 报告
```

配置文件示例 `my_server.yaml`：

```yaml
server:
  name: "我的生存服"
  version: "1.20.1"
  plugins: ["GriefPrevention"]

goals:
  - "高玩家留存率"
  - "高社区和谐度"

llm:
  provider: "openai"  # or "anthropic"
  model: "gpt-4"
  api_key: "YOUR_API_KEY"
```

### 集成 Discord Bot（计划中）

自动从 Discord 聊天中收集玩家反馈，生成 `{AvailableData}` 用于 Prompt D。

## 💡 使用技巧

1. **不要跳过 Prompt D** - 验证环节是 PDCA 循环的关键
2. **保留历史迭代记录** - 可以看到服务器的"进化轨迹"
3. **定期回顾公理** - 确保推论始终基于六大公理
4. **玩家参与决策** - 在实施 Prompt C 的方案前，征求玩家意见

## 🤝 贡献

如果您开发了有用的工具或模板，欢迎提交 PR！

例如：
- 数据收集脚本（从 Plan 插件导出数据）
- Prompt 优化版本
- 其他语言的翻译

## 许可证

本目录下所有文件采用 GPL-3.0 许可。

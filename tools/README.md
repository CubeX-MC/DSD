## Metrics and YAML fields cheat sheet

Use these standardized keys across Prompt A→B→C→D to keep inputs/outputs consistent:

- retention_30d: Percentage of players who return within 30 days.
- churn_7d: Percentage of players who do not return within 7 days.
- concurrent_online_peak: Highest concurrent players during the period.
- avg_concurrent_online: Average concurrent players during the period.
- conflicts_per_week: Number of significant conflict incidents per week.
- grief_reports: Number of griefing reports during the period.
- ban_rate: Percentage of active players banned during the period.
- appeal_rate: Percentage of bans that receive appeals.
- onboarding_completion_rate: Percentage of new players completing onboarding/first milestones.
- k_factor: Viral/referral coefficient derived from invites per active user.
- tps_avg: Average ticks-per-second (server performance) during peak hours.
- tps_p95: 95th percentile TPS drop during peak hours.
- view_distance: Configured server view distance (performance lever/constraint).
- mobcap_utilization: Estimated share of mob cap consumed by shared farms.
- queue_time_p95: 95th percentile queue time or wait time for activities.
- report_to_action_latency: Median time from report to moderator action.
- build_code_violations: Count of violations against collective building codes.
- participation_gini: Inequality of contribution/participation (0–1).

Notes:
- Prefer percentages as decimals (e.g., 0.34 for 34%) unless otherwise stated.
- Time-based fields should include ISO 8601 or clear units (e.g., minutes).
- When adding custom metrics, document them here to keep the schema discoverable.

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

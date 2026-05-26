# AI Agent 方法论合集

> 来自真实生产环境的调试与工程方法论。每一条都是用踩坑换来的。

English | [简体中文](./README.zh.md)

## 这是什么

一组为 AI 编程助手（Claude Code、Cursor、Hermes Agent 等）设计的调试与工程方法论。每条方法论包含：

- **原则**：核心思想
- **检查清单**：可直接执行的步骤
- **反面案例**：真实踩坑经历
- **适用场景**：什么时候用

## 方法论列表

| 方法论 | 核心思想 | 来源 |
|--------|----------|------|
| [约束优先排查](./skills/constraint-first-debugging/) | 先验证不可控层是否支持，再动手改代码 | 微信语音条发送失败 |

## 安装

### Claude Code

直接把 `CLAUDE.md` 放到项目根目录：

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/ryan-flow/ai-agent-methodologies/main/CLAUDE.md
```

### Hermes Agent

```bash
hermes skill install ryan-flow/ai-agent-methodologies
```

### Cursor

复制 `.cursor/rules/methodologies.mdc` 到你的项目 `.cursor/rules/` 目录。

### 手动

`skills/` 目录下的每个方法论都是独立的 Markdown 文件，可以手动复制到任何地方使用。

## 贡献

遇到新的坑？欢迎提交 PR！格式要求：

1. 在 `skills/` 下新建目录
2. 包含 `SKILL.md`（Hermes 格式）和 `METHODOLOGY.md`（通用格式）
3. README 中的方法论列表里加上新条目

## License

MIT

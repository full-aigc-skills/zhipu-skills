---
name: zhipu-text
description: "智谱 AI 文生文模型选型与调用指南，涵盖 GLM-5、GLM-4.7、GLM-4.6、GLM-4.5 系列及免费模型。当用户需要调用智谱文本生成模型时使用此 skill。触发条件：用户提到智谱文生文、GLM 文本模型、智谱大模型、BigModel text generation，或需要文本生成/对话能力时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 文生文模型 (Text Generation)

## 模型总览

| 模型 | Model ID | 参数 | 上下文 |
|------|----------|------|--------|
| GLM-5 | `glm-5` | 744B / 40B active | 128K |
| GLM-4.7 | `glm-4.7` | - | 128K |
| GLM-4.6 | `glm-4.6` | 355B / 32B active | 128K |
| GLM-4.5 系列 | `glm-4.5` 等 5 个变体 | - | 128K |
| GLM-4.7-FlashX | `glm-4.7-flashx` | - | 128K |
| GLM-4.7-Flash | `glm-4.7-flash` | 30B | 200K |

## 选型建议

- **旗舰**: `glm-5` — Agentic Engineering 定位
- **性价比旗舰**: `glm-4.7` — Code Arena 开源第一
- **高速**: `glm-4.7-FlashX`
- **稳定**: `glm-4.6`
- **灵活**: `glm-4.5` 系列 — 5 个变体覆盖不同性能和成本需求
- **免费**: `glm-4.7-flash` — 免费且拥有 200K 上下文

## 共享能力

所有文本模型支持：thinking mode（`thinking.type`: `enabled`/`disabled`）、streaming、Function Calling、上下文缓存、结构化 JSON Schema 输出、MCP 支持。

## API Key 配置

从 `~/.glm/.env` 加载，使用 `ZHIPU_API_KEY`。Key 获取地址：https://open.bigmodel.cn/usercenter/apikeys

## API 调用

```
POST https://open.bigmodel.cn/api/paas/v4/chat/completions
```

Auth: Bearer token，Content-Type: application/json

请求体包含：`model`, `messages`, `stream`, `temperature`, `max_tokens`

Thinking mode: `"thinking": {"type": "enabled"}`

## SDK 示例

```python
from zai import ZhipuAI
client = ZhipuAI(api_key="your-key")
response = client.chat.completions.create(
    model="glm-5",
    messages=[{"role": "user", "content": "你好"}]
)
```

## 推荐场景

Agentic Coding、长链自主代理、办公自动化、角色扮演/剧本生成、专业翻译、结构化数据提取、客服质检。

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

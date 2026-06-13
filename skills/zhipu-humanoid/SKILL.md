---
name: zhipu-humanoid
description: "智谱 AI 角色扮演与拟人模型选型与调用指南。涵盖 CharGLM-4 和 Emohaa。当用户需要调用智谱的角色扮演或心理咨询模型时使用此 skill。触发条件：用户提到智谱角色扮演、CharGLM、Emohaa、虚拟角色、数字人、NPC、心理咨询、情感陪伴、拟人对话、BigModel humanoid，或需要角色一致性/情感对话能力时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 角色/拟人模型 (Humanoid)

## 模型总览

| 模型 | Model ID | 上下文 | 定价 |
|------|----------|--------|------|
| CharGLM-4 | `charglm-4` | 8K | 1 元/百万 token |
| Emohaa | `emohaa` | 8K | 15 元/百万 token |

## 选型建议

- **角色扮演/虚拟人**: `charglm-4` — 角色一致性、多轮记忆
- **心理咨询/情感陪伴**: `emohaa` — 专业倾听、共情能力

## API Key 配置

从 `~/.glm/.env` 加载 `ZHIPU_API_KEY`。Key 获取：https://open.bigmodel.cn/usercenter/apikeys

## CharGLM-4 特性

- 角色一致性维护
- 多轮对话记忆
- 多样化人格创建
- 情感表达
- 流式输出

## CharGLM-4 调用示例

```python
from zai import ZhipuAI
client = ZhipuAI(api_key="your-key")
response = client.chat.completions.create(
    model="charglm-4",
    messages=[
        {"role": "system", "content": "你是小雪，一个温柔体贴的邻家女孩"},
        {"role": "user", "content": "今天心情不太好"}
    ],
    stream=True
)
```

## Emohaa 特性

- 专业倾听能力
- 情绪状态识别
- 共情回应
- Hill 帮助理论指导

## Emohaa 调用示例

```python
response = client.chat.completions.create(
    model="emohaa",
    messages=[{"role": "user", "content": "最近压力很大"}],
    meta={
        "user_info": "用户信息",
        "bot_info": "助手信息",
        "bot_name": "小助手",
        "user_name": "用户"
    }
)
```

## API 端点

```
POST https://open.bigmodel.cn/api/paas/v4/chat/completions
```

## 推荐场景

- CharGLM-4: 情感陪伴、游戏 NPC、数字人直播、虚拟偶像
- Emohaa: 情感支持、心理咨询、压力管理、关系改善

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

---
name: zhipu-image-generation
description: "智谱 AI 图像生成模型选型与调用指南。涵盖 CogView-4、GLM-Image 及免费的 CogView-3-Flash。当用户需要调用智谱的文生图模型时使用此 skill。触发条件：用户提到智谱生图、CogView、GLM-Image、智谱文生图、BigModel image generation，或需要用智谱 API 生成图片时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 图像生成模型 (Image Generation)

## 模型总览

| 模型 | Model ID | 分辨率 | 特性 |
|------|----------|--------|------|
| CogView-4 | `cogview-4` | 最高 4K | 旗舰文生图 |
| GLM-Image | `glm-image` | 最高 2K | 新一代图像生成 |
| CogView-3-Flash | `cogview-3-flash` | 最高 2K | 免费 |

## 选型建议

- **最高质量**: `cogview-4` — 4K 分辨率
- **最新架构**: `glm-image`
- **免费体验**: `cogview-3-flash`

## API Key 配置

从 `~/.glm/.env` 加载 `ZHIPU_API_KEY`。Key 获取：https://open.bigmodel.cn/usercenter/apikeys

## API 调用

```
POST https://open.bigmodel.cn/api/paas/v4/images/generations
```

请求体包含：`model`, `prompt`, `n`, `size`

## SDK 示例

```python
from zai import ZhipuAI
client = ZhipuAI(api_key="your-key")
response = client.images.generations(
    model="cogview-4",
    prompt="一只橘猫坐在窗台上，阳光洒落",
    n=1,
    size="1024x1024"
)
```

## 并发限制

| 用户等级 | 并发数 |
|----------|--------|
| V0 | 5 |
| V1 | 10 |
| V2 | 20 |
| V3 | 50 |

## 推荐场景

电商产品图、社交媒体配图、概念设计草稿、游戏资产、广告创意。

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

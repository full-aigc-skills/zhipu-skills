---
name: zhipu-video-generation
description: "智谱 AI 视频生成模型选型与调用指南。涵盖 CogVideoX-3、Vidu 2、Vidu Q1 及免费的 CogVideoX-Flash。当用户需要调用智谱的视频生成模型时使用此 skill。触发条件：用户提到智谱视频生成、CogVideoX、Vidu、文生视频、图生视频、BigModel video generation，或需要用智谱 API 生成视频时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 视频生成模型 (Video Generation)

## 模型总览

| 模型 | Model ID | 分辨率 | 时长 | 帧率 |
|------|----------|--------|------|------|
| CogVideoX-3 | `cogvideox-3` | 1080P | 5-10s | 24fps |
| Vidu 2 (文生) | `vidu2-image` | 1080P | 4-8s | 24fps |
| Vidu 2 (首尾帧) | `vidu2-start-end` | 1080P | 4-8s | 24fps |
| Vidu 2 (参考) | `vidu2-reference` | 1080P | 4-8s | 24fps |
| Vidu Q1 (文生) | `viduq1-text` | 1080P | 5s | 24fps |
| Vidu Q1 (图生) | `viduq1-image` | 1080P | 5s | 24fps |
| Vidu Q1 (首尾帧) | `viduq1-start-end` | 1080P | 5s | 24fps |
| CogVideoX-Flash | `cogvideox-flash` | 720P | 5s | 16fps |

## 选型建议

- **最高质量**: `cogvideox-3`
- **Vidu 生态**: `vidu2-*` 系列
- **动漫风格**: `viduq1-*` — 支持 general 和 anime 风格
- **免费体验**: `cogvideox-flash`

## API Key 配置

从 `~/.glm/.env` 加载 `ZHIPU_API_KEY`。Key 获取：https://open.bigmodel.cn/usercenter/apikeys

## API 调用

```
POST https://open.bigmodel.cn/api/paas/v4/async/videos/generations
```

异步模式：提交任务 → 轮询查询结果。视频 URL 链接有效期 1 天。

## SDK 示例

```python
from zai import ZhipuAI
client = ZhipuAI(api_key="your-key")
task = client.videos.generations.create(
    model="cogvideox-3",
    prompt="阳光下的海滩，海浪拍打岸边"
)
# 轮询查询结果
result = client.videos.generations.retrieve(task.id)
```

## 并发限制

| 用户等级 | 并发数 |
|----------|--------|
| V0 | 5 |
| V1 | 10 |
| V2 | 15 |
| V3 | 20 |

## 推荐场景

电商营销视频、旅游宣传片、动画短片、影视短剧制作、广告创意、文旅宣传。

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

---
name: zhipu-embedding
description: "智谱 AI 文本向量模型选型与调用指南。涵盖 Embedding-3 和 Embedding-2。当用户需要调用智谱的 Embedding 模型时使用此 skill。触发条件：用户提到智谱向量、Embedding、文本嵌入、语义搜索、向量检索、BigModel embedding，或需要将文本转换为向量时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 向量模型 (Embedding)

## 模型总览

| 模型 | Model ID | 维度 | 上下文 | 最大输入 |
|------|----------|------|--------|----------|
| Embedding-3 | `embedding-3` | 2048/1024/512/256 | 32K | 32K tokens |
| Embedding-2 | `embedding-2` | 2048 | 8K | 8K tokens |

## 选型建议

- **推荐**: `embedding-3` — 更高性能，更灵活维度

### Embedding-3 维度选择

| 维度 | 推荐场景 |
|------|----------|
| 2048 | 高精度语义搜索、RAG |
| 1024 | 通用检索、聚类 |
| 512 | 高效检索、分类 |
| 256 | 大规模向量库、近似搜索 |

## API Key 配置

从 `~/.glm/.env` 加载 `ZHIPU_API_KEY`。Key 获取：https://open.bigmodel.cn/usercenter/apikeys

## API 调用

```
POST https://open.bigmodel.cn/api/paas/v4/embeddings
```

支持单条和批量文本输入。

## SDK 示例

```python
from zai import ZhipuAI
client = ZhipuAI(api_key="your-key")
response = client.embeddings.create(
    model="embedding-3",
    input=["文本内容"],
    dimensions=1024
)
```

## 并发限制

| 用户等级 | 并发数 |
|----------|--------|
| V0 | 50 |
| V1 | 100 |
| V2 | 200 |
| V3 | 500 |

## 推荐场景

语义搜索、RAG 知识库、文本聚类、异常检测、文本分类、相似度计算、推荐系统。

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

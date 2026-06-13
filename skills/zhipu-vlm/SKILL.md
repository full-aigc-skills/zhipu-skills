---
name: zhipu-vlm
description: "智谱 AI 视觉语言模型 (VLM) 选型与调用指南。涵盖 GLM-4.6V、GLM-4.1V-Thinking、GLM-OCR、AutoGLM-Phone 及其免费变体。当用户需要调用智谱的多模态视觉理解模型时使用此 skill，包括图片理解、视频理解、文档 OCR 解析、手机自动化等能力。触发条件：用户提到智谱视觉模型、图片理解、视频分析、VLM、GLM-4.6V、GLM-4.1V、GLM-OCR、AutoGLM、智谱多模态、BigModel vision，或需要图文/视频理解能力时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 视觉语言模型 (VLM)

## 模型总览

| 模型 | Model ID | 参数 | 上下文 | 特性 |
|------|----------|------|--------|------|
| GLM-4.6V | `glm-4.6v` | - | 128K | 图片+视频理解 |
| GLM-4.1V-Thinking | `glm-4.1v-thinking` | - | 128K | 视觉推理、链式思考 |
| GLM-OCR | `glm-ocr` | 0.9B | 8K | 专用 OCR，OmniDocBench 94.62 SOTA |
| AutoGLM-Phone | `autoglm-phone` | - | - | 手机自动化控制 |

## 选型建议

- **通用图片理解**: `glm-4.6v`
- **视频分析**: `glm-4.6v`
- **文档 OCR**: `glm-ocr` — 0.9B 参数，94.62 SOTA
- **视觉推理**: `glm-4.1v-thinking` — 链式思考
- **GUI Agent/前端**: `glm-4.1v-thinking` — 支持视觉定位、前端代码生成
- **手机自动化**: `autoglm-phone`

## API Key 配置

从 `~/.glm/.env` 加载 `ZHIPU_API_KEY`。Key 获取：https://open.bigmodel.cn/usercenter/apikeys

## GLM-OCR 特性

- 0.9B 参数，OmniDocBench 94.62 SOTA
- 支持语言：中文、英文、日文、韩文等
- 输出格式：Markdown、LaTeX、HTML
- 布局解析 API 端点

## AutoGLM-Phone 特性

- Android 设备控制
- 自动化操作执行
- 特定 API 端点

## 推荐场景

图片理解、视频分析、文档问答、GUI Agent、手机自动化

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

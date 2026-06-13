<div align="center">

# zhipu-skills

**智谱 (Zhipu) AIGC 技能 — 文本、图像、视频生成、语音合成、OCR、VLM、Embedding**

[![GitHub](https://img.shields.io/badge/github-full--aigc--skills%2Fzhipu-skills-green.svg)](https://github.com/full-aigc-skills/zhipu-skills)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-兼容-purple.svg)](https://agentskills.io)

[English](./README.md) | 简体中文

</div>

---

## 📖 简介

**zhipu-skills** 是一组 AI 编码智能体技能，属于 [Full AIGC Skills](https://github.com/full-aigc-skills) 生态。包含 **8 个技能**。

## 📦 安装

```bash
npx skills add full-aigc-skills/zhipu-skills
```

## 🎯 技能列表 (8)

| 技能 | 描述 |
|------|------|
| `zhipu-audio` |  "智谱 AI 语音模型选型与调用指南。涵盖文本转语音 (TTS)、声音克隆、语音识别 (ASR)、端到端语音对话、实时音视频对话，包括 GLM-TTS、GLM-TTS-Clone、GLM-ASR-2 |
| `zhipu-embedding` |  "智谱 AI 文本向量模型选型与调用指南。涵盖 Embedding-3 和 Embedding-2。当用户需要调用智谱的 Embedding 模型时使用此 skill。触发条件：用户提到智谱向量、E |
| `zhipu-humanoid` |  "智谱 AI 角色扮演与拟人模型选型与调用指南。涵盖 CharGLM-4 和 Emohaa。当用户需要调用智谱的角色扮演或心理咨询模型时使用此 skill。触发条件：用户提到智谱角色扮演、CharG |
| `zhipu-image-generation` |  "智谱 AI 图像生成模型选型与调用指南。涵盖 CogView-4、GLM-Image 及免费的 CogView-3-Flash。当用户需要调用智谱的文生图模型时使用此 skill。触发条件：用户提 |
| `zhipu-ocr` |  "使用智谱 GLM-4V-Flash 视觉模型识别图片中的文字。支持 JPG/PNG/GIF/BMP/WebP 等常见图片格式，单张识别和批量处理。当用户发送图片并要求识别文字、提取文字或 OCR  |
| `zhipu-text` |  "智谱 AI 文生文模型选型与调用指南，涵盖 GLM-5、GLM-4.7、GLM-4.6、GLM-4.5 系列及免费模型。当用户需要调用智谱文本生成模型时使用此 skill。触发条件：用户提到智谱文 |
| `zhipu-video-generation` |  "智谱 AI 视频生成模型选型与调用指南。涵盖 CogVideoX-3、Vidu 2、Vidu Q1 及免费的 CogVideoX-Flash。当用户需要调用智谱的视频生成模型时使用此 skill。 |
| `zhipu-vlm` |  "智谱 AI 视觉语言模型 (VLM) 选型与调用指南。涵盖 GLM-4.6V、GLM-4.1V-Thinking、GLM-OCR、AutoGLM-Phone 及其免费变体。当用户需要调用智谱的多模 |

## 🤖 支持的智能体

适用于 [Claude Code](https://code.claude.com)、[Codex](https://developers.openai.com/codex)、[Cursor](https://cursor.com)、[OpenCode](https://opencode.ai)、[Gemini CLI](https://geminicli.com)、[GitHub Copilot](https://github.com/features/copilot)、[Windsurf](https://codeium.com/windsurf) 及 [70+ 其他](https://agentskills.io/clients)。

### Claude Code 安装

**方式一：npx skills CLI（推荐）**

```bash
npx skills add full-aigc-skills/zhipu-skills
```

**方式二：手动安装**

```bash
git clone https://github.com/full-aigc-skills/zhipu-skills.git
cp -r zhipu-skills/skills/* .claude/skills/
```

## 📄 License

Apache 2.0

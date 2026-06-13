---
name: zhipu-audio
description: "智谱 AI 语音模型选型与调用指南。涵盖文本转语音 (TTS)、声音克隆、语音识别 (ASR)、端到端语音对话、实时音视频对话，包括 GLM-TTS、GLM-TTS-Clone、GLM-ASR-2512、GLM-4-Voice、GLM-Realtime。当用户需要调用智谱的语音相关模型时使用此 skill。触发条件：用户提到智谱语音、TTS、ASR、语音合成、语音识别、声音克隆、实时对话、GLM-TTS、GLM-Voice、GLM-Realtime、BigModel audio，或需要语音合成/识别/对话能力时。来源: https://github.com/tencentjerry-afk/zhipu-claude-skills"
metadata:
  source: "https://github.com/tencentjerry-afk/zhipu-claude-skills"
  requires:
    env: ["ZHIPU_API_KEY"]
---

# 智谱 AI 语音模型 (Audio)

## 模型总览

| 模型 | Model ID | 类型 | 特性 |
|------|----------|------|------|
| GLM-TTS | `glm-tts` | TTS | 7 种音色，WAV/PCM，24kHz |
| GLM-TTS-Clone | `glm-tts-clone` | 声音克隆 | 3 秒样本即可克隆 |
| GLM-ASR-2512 | `glm-asr-2512` | ASR | CER 0.0717，支持方言 |
| GLM-4-Voice | `glm-4-voice` | 端到端语音 | 8K 上下文，情绪/语调/语速控制 |
| GLM-Realtime | `glm-realtime` | 实时对话 | WebSocket，支持打断/函数调用 |
| GLM-Realtime-Flash | `glm-realtime-flash` | 实时对话 | 0.18 元/分钟 |
| GLM-Realtime-Air | `glm-realtime-air` | 实时对话 | 0.30 元/分钟（含视频） |

## 选型建议

- **标准 TTS**: `glm-tts`
- **个性化语音**: `glm-tts-clone` — 3 秒样本克隆
- **语音转文字**: `glm-asr-2512`
- **语音对话**: `glm-4-voice` — 情绪/语速控制
- **实时交互**: `glm-realtime` — WebSocket，支持打断

## API Key 配置

从 `~/.glm/.env` 加载 `ZHIPU_API_KEY`。Key 获取：https://open.bigmodel.cn/usercenter/apikeys

## GLM-TTS 特性

- 7 种预设音色
- WAV/PCM 输出，24kHz 采样率
- 首帧延迟 ≤400ms

## GLM-TTS-Clone 特性

- 3 秒音频样本即可完成声音克隆
- API: `POST https://open.bigmodel.cn/api/paas/v4/voice/clone`

## GLM-ASR-2512 特性

- 最大 25MB，最长 30s
- CER 0.0717
- 支持中文方言识别

## GLM-4-Voice 特性

- 8K token 上下文，4K 最大输出
- WAV/Base64 mono 16-bit 44100Hz
- 情绪、语调、语速、方言控制

## GLM-Realtime 特性

- WebSocket 协议
- 支持：打断、函数调用、唱歌、屏幕共享
- Flash: 0.18/1.20 元/分钟；Air: 0.30/2.10 元/分钟

## 推荐场景

TTS 语音合成、声音克隆个性化、语音转文字转录、端到端语音助手、实时音视频对话

## 文档参考

- https://docs.bigmodel.cn/
- https://open.bigmodel.cn/usercenter/apikeys

---
name: zhipu-ocr
description: "使用智谱 GLM-4V-Flash 视觉模型识别图片中的文字。支持 JPG/PNG/GIF/BMP/WebP 等常见图片格式，单张识别和批量处理。当用户发送图片并要求识别文字、提取文字或 OCR 时触发。来源: https://github.com/Wcowin/zhipu-OCR-skill (MIT)"
metadata:
  source: "https://github.com/Wcowin/zhipu-OCR-skill"
  license: "MIT"
  requires:
    bins: ["python3"]
    python_packages: ["zhipuai"]
    env: ["ZHIPUAI_API_KEY"]
---

# 智谱 OCR 文字识别

使用 GLM-4V-Flash 视觉模型识别图片中的文字。

## 安装

```bash
git clone https://github.com/Wcowin/zhipu-OCR-skill.git
cd zhipu-OCR-skill
pip install -r requirements.txt
```

## 使用

```bash
python3 scripts/ocr.py <图片路径> [提示词]
```

- `<图片路径>`: 必需，图片文件路径
- `[提示词]`: 可选，默认 "请识别图片中的所有文字，并完整输出"
- `-v`: 显示详细输出

## 配置

设置环境变量 `ZHIPUAI_API_KEY`（从 https://open.bigmodel.cn/usercenter/apikeys 获取）。

## 支持的格式

JPG, PNG, GIF, BMP, WebP 等常见图片格式。

## 使用场景

- 用户发送图片要求识别文字
- 截图文字提取
- 扫描文档 OCR
- 表格内容识别
- 手写文字识别

## 注意

- 需要有效的智谱 AI API Key
- 需要网络连接访问 API

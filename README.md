# Telegram 自动翻译助手 / Telegram Auto Translator Bot

📢 **Telegram 账号**: [@ywjs99999bot](https://t.me/ywjs99999bot)  
💬 **QQ 账号**: 3697099052  

---

## 简介 / Introduction

**Telegram 自动翻译助手**是一款基于 Python 的本地客户端脚本，利用 Telethon + Deep Translator + SQLite 本地缓存，实现对 Telegram 聊天的**收发端自动翻译**，并在 Windows 桌面弹出通知。  

This **Telegram Auto Translator Bot** is a Python‐based local client script that uses Telethon + Deep Translator + SQLite local caching to implement **automatic translation** for incoming and outgoing Telegram messages, with optional Windows desktop notifications.

---

## 功能特性 / Features

1. **接收端自动翻译**  
   - 自动检测对方消息语言（不限中文/英文/日语等）。  
   - 将所有非中文消息翻译为简体中文（zh-CN）。  
   - 翻译结果以 Windows 通知形式弹出（可裁剪超长文本）。  
2. **发送端自动翻译**  
   - 当你在任意 Telegram 客户端发送**中文**消息时，脚本会：  
     1. 毫秒级撤回原文，尽量不让对方看到中文。  
     2. 翻译成英文（en），并重新发送译文。  
   - **发送端不弹窗**，专注于快速替换消息内容。  
3. **多级缓存加速**  
   - **内存 LRU 缓存**（512 条热词）大幅提升热点消息翻译速度。  
   - **SQLite 本地缓存**（translator_cache.db，启用 WAL、索引优化）避免重复调用在线翻译 API。  
   - **异步写入**：专用后台线程批量写入 SQLite，主线程查询不阻塞。  
4. **轻量易用**  
   - 跨平台 Python 脚本，无需服务器部署。  
   - 只需安装 Python 3.10+ 及少量依赖。  
   - 支持 Windows 环境下的桌面通知。

---

## 环境与依赖 / Requirements

- **操作系统**：Windows 10 / 11  
- **Python 版本**：3.10 及以上  
- **第三方库**：  
  ```bash
  pip install telethon deep-translator win10toast

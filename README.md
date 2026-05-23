# edge-speak

> **[English README](./README-EN.md)**

轻量级命令行 TTS 工具，基于 [edge-tts](https://github.com/rany2/edge-tts) 实现，支持对话场景下自动切换男女声。

---

## 特性

- **文本朗读** — 调用微软 Edge 神经语音，音质自然
- **对话模式** — 文本中标 `男:` / `女:`，自动分配不同声音
- **默认英音** — 男声 Ryan，女声 Sonia，均可自定义
- **无缝拼接** — 切换声音时零间隙（使用 ffmpeg concat）

## 依赖

- Python 3.7+
- [edge-tts](https://github.com/rany2/edge-tts) (`pip install edge-tts` 或 `uv tool install edge-tts`)
- `ffmpeg`（对话模式需要）
- `mpv` 或其他音频播放器

## 安装

```bash
git clone https://github.com/smithyyang/edge-speak.git
cd edge-speak
cp speak ~/.local/bin/
chmod +x ~/.local/bin/speak
```

或直接下载脚本：

```bash
curl -o ~/.local/bin/speak https://raw.githubusercontent.com/smithyyang/edge-speak/main/speak
chmod +x ~/.local/bin/speak
```

## 用法

### 基础朗读

```bash
speak 你好，这是一段测试语音。
echo "也可从标准输入传入" | speak
```

### 对话模式（男女声自动切换）

```bash
echo '男: 欢迎光临，请问有什么可以帮您？ 女: 我想订一个房间。 男: 好的，请问住几晚？' | speak
```

## 配置

默认声音：

| 标记 | 声音 |
|------|------|
| `男` | `en-GB-RyanNeural`（英式男声） |
| `女` | `en-GB-SoniaNeural`（英式女声） |

编辑脚本中的 `VOICES` 字典即可自定义。

## 许可

MIT

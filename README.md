# edge-speak

A lightweight CLI text-to-speech tool powered by [edge-tts](https://github.com/rany2/edge-tts) with automatic male/female voice switching for dialogue.

基于 [edge-tts](https://github.com/rany2/edge-tts) 的轻量级命令行 TTS 工具，支持对话场景下自动切换男女声。

---

## Features / 特性

- **Read text aloud** with high-quality Microsoft Edge neural voices / 用微软神经语音朗读文本
- **Dialogue mode** — auto-switch voices by speaker markers (`男:` / `女:`) / 对话模式 —— 按 `男:` / `女:` 标记自动切换声音
- **British English** as default (Ryan / Sonia), fully configurable / 默认英式英语，完全可配置
- Zero audio gap when switching voices (uses ffmpeg concat) / 切换声音零间隙

## Requirements / 依赖

- Python 3.7+
- [edge-tts](https://github.com/rany2/edge-tts) (`pip install edge-tts` or `uv tool install edge-tts`)
- `ffmpeg` (for dialogue mode audio concatenation / 用于对话模式音频拼接)
- `mpv` or any audio player / 或其他音频播放器

## Installation / 安装

```bash
git clone https://github.com/smithyyang/edge-speak.git
cd edge-speak
cp speak ~/.local/bin/
chmod +x ~/.local/bin/speak
```

Or download the script directly / 或直接下载脚本：

```bash
curl -o ~/.local/bin/speak https://raw.githubusercontent.com/smithyyang/edge-speak/main/speak
chmod +x ~/.local/bin/speak
```

## Usage / 用法

### Basic / 基础朗读

```bash
speak Hello, this is a test.
echo "Hello from stdin" | speak
```

### Dialogue mode / 对话模式 (male ↔ female / 男 ↔ 女)

```bash
echo '男: Welcome to our hotel. How may I help you? 女: I would like to book a room, please. 男: Certainly, for how many nights?' | speak
```

## Configuration / 配置

Default voices / 默认声音:

| 标记 | 声音 | Voice |
|------|------|-------|
| `男` | 英式男声 Ryan | `en-GB-RyanNeural` |
| `女` | 英式女声 Sonia | `en-GB-SoniaNeural` |

Edit the `VOICES` dict in the script to customize.
编辑脚本中的 `VOICES` 字典即可自定义声音。

## License / 许可

MIT

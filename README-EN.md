# edge-speak

> [中文](./README.md)

A lightweight CLI text-to-speech tool powered by [edge-tts](https://github.com/rany2/edge-tts) with automatic male/female voice switching for dialogue.

---

## Features

- **Read text aloud** with high-quality Microsoft Edge neural voices
- **Dialogue mode** — auto-switch voices by speaker markers (`男:` / `女:`)
- **British English** as default (Ryan / Sonia), fully configurable
- **Zero audio gap** when switching voices (uses ffmpeg concat)

## Requirements

- Python 3.7+
- [edge-tts](https://github.com/rany2/edge-tts) (`pip install edge-tts` or `uv tool install edge-tts`)
- `ffmpeg` (required for dialogue mode)
- `mpv` or any audio player

## Installation

```bash
git clone https://github.com/smithyyang/edge-speak.git
cd edge-speak
cp speak ~/.local/bin/
chmod +x ~/.local/bin/speak
```

Or download the script directly:

```bash
curl -o ~/.local/bin/speak https://raw.githubusercontent.com/smithyyang/edge-speak/main/speak
chmod +x ~/.local/bin/speak
```

## Usage

### Basic

```bash
speak Hello, this is a test.
echo "Also accepts input from stdin" | speak
```

### Dialogue mode (male ↔ female)

```bash
echo '男: Welcome to our hotel. How may I help you? 女: I would like to book a room, please. 男: Certainly, for how many nights?' | speak
```

## Configuration

Default voices:

| Marker | Voice |
|--------|-------|
| `男` | `en-GB-RyanNeural` (British male) |
| `女` | `en-GB-SoniaNeural` (British female) |

Edit the `VOICES` dict in the script to customize.

## License

MIT

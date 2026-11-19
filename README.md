[README.md](https://github.com/user-attachments/files/35080633/README.md)

# Cybernetic · Terminal MV

《Cybernetic》的字符动效 MV。Python 在 Windows 终端里实时绘制整首歌的画面，并按本地音轨同步。  
A character-art music video for *Cybernetic*. Python renders the full piece live in a Windows terminal, in sync with the local audio track.

**创意指导 / Creative direction — Shanyce**

## 画面 / Visuals

- **开场 / Opening** — 35 个镜头。电路、纵向数据槽、汇聚的搜索信号和折叠菱形轮流出现。水波在歌词回环处再次出现。
- **高潮与片尾 / Climaxes and finale** — 彩色日志、逐渐铺满的 `ERROR`、`HELP ME` 背景中的呼吸人物，以及从信号撕裂过渡到归零的心电图。
- **双语字幕 / Bilingual subtitles** — 英文歌词和中文翻译随音轨显示，播放时可微调时间。

The opening cuts between distinct circuit, data-transfer, and signal-search compositions, with recurring waves. Colored logs, spreading `ERROR` stamps, the breathing portrait in the `HELP ME` scene, and a dissolving ECG carry the later sections. English lyrics and Chinese subtitles both follow the audio clock.

## 播放 / Play

1. 在 Windows 10 或 11 上解压工程，确保 `Play.cmd` 和 `media/` 在同一目录。/ Extract the full project on Windows 10 or 11, keeping `Play.cmd` beside the `media/` folder.
2. 安装 Python 3.9 或更新版本，让新开的命令提示符能运行 `python --version`。/ Install Python 3.9 or newer and confirm that `python --version` works in a fresh Command Prompt. [Python 3.9.13 Windows installer](https://www.python.org/downloads/release/python-3913/) · [Current Windows downloads](https://www.python.org/downloads/windows/)
3. 双击 `Play.cmd`，看到封面后按空格。/ Double-click `Play.cmd`, then press Space on the cover.

离线播放只需 Python 标准库。/ Offline playback uses only the Python standard library.

| 按键 / Key | 功能 / Action |
| --- | --- |
| Space / Enter | 开始、暂停、继续 / Start, pause, resume |
| ← / → | 后退或前进 5 秒 / Seek 5 seconds |
| **K** | 自适应 → 96×28 → 120×38 → 160×48 → 自适应 / Cycle Auto and the three window sizes |
| R | 从头播放 / Restart |
| Q / Esc | 退出 / Quit |
| H | 按键提示 / Shortcut help |
| 1–5 | 跳转章节 / Jump to a chapter |
| `[` / `]` | 字幕提前或延后 0.1 秒 / Advance or delay subtitles by 0.1 seconds |
| `,` / `.` | 上一句或下一句歌词 / Previous or next lyric |
| `+` / `-` | 调整音量 / Adjust volume |

默认使用自适应，拖动窗口时画面实时调整。固定档位以列 × 行为单位。终端限制调整时，画面会按可用空间居中排版。  
The player starts in Auto, which follows the terminal as you resize it. Presets are in columns × rows. If a resize request is unavailable, the player centers the chosen layout and fits it to the available space.

完整说明见 [README.txt](README.txt)。/ See [README.txt](README.txt) for the full user guide.

## 编辑 / Editing

| 文件 / File | 用途 / Purpose |
| --- | --- |
| [Play.cmd](Play.cmd) | Windows 启动入口 / Windows launcher |
| [terminal_opening.py](terminal_opening.py) | 开场镜头顺序 / Opening shot order |
| [opening_geometry.py](opening_geometry.py) | 开场独立构图 / Opening compositions |
| [terminal_film.py](terminal_film.py) | 全片画面合成 / Film composition |
| [media/](media/) | WAV、字幕、角色源图和播放采样 / Audio, subtitles, portrait sources, and playback samples |

修改音频或角色图后可重新生成采样。运行下列命令时，当前目录应包含 `Play.cmd`。  
To regenerate samples after changing the audio or artwork, run these commands from the folder containing `Play.cmd`.

```bat
python -m pip install numpy pillow
python build_terminal_assets.py
```

## 署名与参考 / Credits and references

- **Shanyce** — 创意指导、视觉参考、人物素材选择和节奏调整。/ Creative direction, visual references, artwork selection, and pacing.
- **音乐 / Music** — *Cybernetic* by Yunosuke × Circus-P, featuring Hatsune Miku English. [Official release](https://yunosuke-official.bandcamp.com/album/cybernetic)
- **画面参考 / Visual references** — [Bilibili · BV186pc65E68](https://www.bilibili.com/video/BV186pc65E68/) · [Bilibili · BV1XtHw67En7](https://www.bilibili.com/video/BV1XtHw67En7/)
- **原终端播放器 / Upstream terminal player** — [CoraxEldridge/world.execute-me-ascii · Windows branch](https://github.com/CoraxEldridge/world.execute-me-ascii/tree/windows-support)

音乐、角色图与上游代码的再分发各依其权利方授权。  
Redistribution of the music, character artwork, and upstream code depends on permission from their respective rights holders.

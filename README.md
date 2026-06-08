# Video Frame Extractor

Browser-based video frame extraction tool that runs locally without uploading to any server.

## Features

### Video Frame Extraction
- **Per-segment extraction** — Extract frames by interval or total count across all segments
- **Manual frame capture** — Capture frames with a button or <kbd>C</kbd> key
- **Progress tracking** — Progress bar with stop button to cancel long-running extractions
- **Frame management** — Delete individual frames or remove all at once
- **Download as ZIP** — Organized filenames with segment number, frame number, and timestamp

### Segment-based Extraction
- **Cutting Points mode** — Mark adjacent boundaries to define segments (no gaps)
- **Explicit mode** — Define independent start/end per segment (gaps allowed)
- **Visual timeline** — Colored segment blocks with playhead tracking playback, clickable to seek
- **Export/Import segments** — Save and restore segment configurations as JSON
- **Scene change chart** — Opt-in analysis using per-pixel RGB delta between sampled frames, with zoom & pan for precise boundary marking

### Keyboard Shortcuts
| Key | Action |
|-----|--------|
| <kbd>C</kbd> | Capture current frame |
| <kbd>A</kbd> | Add segment (cutting point / explicit segment) |
| <kbd>S</kbd> | Set start of last segment |
| <kbd>E</kbd> | Set end of last segment |
| <kbd>←</kbd> <kbd>→</kbd> | Seek backward/forward |
| <kbd>Space</kbd> | Play/Pause |

### Filename Format
- With video name: `{video}_seg{N}_frame{N}_{hh.mm.ss.mmm}.jpg`
- Manual captures: `{video}_frame{N}_{time}.jpg`
- Preserves original video filename (strips `/\?%*:|"<>` for cross-platform compatibility, e.g., Windows doesn't allow those even if the source platform does)

## Usage

Visit the website: [https://video-frame-extractor.surge.sh](https://video-frame-extractor.surge.sh)

1. Upload your video file (drag & drop or click to browse)
2. Configure segments using Cutting Points or Explicit mode
3. Extract frames automatically or capture manually
4. Manage your captured frames (delete individual or remove all)
5. Download all frames as a ZIP file

## Technical Details

- Runs entirely in the browser (no server uploads)
- Uses canvas API to take snapshots
- JPEG format for optimized file size (smaller than PNG)
- Scene analysis uses offscreen canvas at 80px width (preserving aspect ratio) for fast pixel-delta computation
- Adaptive sampling rate based on video duration (0.5s / 1s / 2s)
- No external dependencies — pure HTML/CSS/JavaScript

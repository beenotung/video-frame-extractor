# Video Frame Extractor

Browser-based video frame extraction tool that runs locally without uploading to any server.

## Features

- **Video frame extraction** — Extract frames by interval or total count
- **Manual frame capture** — Capture frames with a button or 'C' key
- **Progress tracking** — Progress bar under the extract button
- **Stop extraction** — Stop button to cancel long-running extractions
- **Frame management** — Delete individual frames or remove all at once
- **Download as ZIP** — Download all frames as a ZIP file
- **Newest first display** — Frames shown in reverse order
- **Frame count** — Shows total number of extracted frames
- **Smooth animations** — Quick fade-out when removing frames
- **Keyboard shortcuts** — Left/Right arrows for seeking, Spacebar for play/pause, 'C' to capture frame

## Usage

Visit the website: [https://video-frame-extractor.surge.sh](https://video-frame-extractor.surge.sh)

1. Upload your video file (drag & drop or click to browse)
2. Navigate through the video and capture frames manually, or use the automatic extraction
3. Manage your captured frames (delete individual or remove all)
4. Download all frames as a ZIP file

## Technical Details

- Runs entirely in the browser (no server uploads)
- Uses canvas API to take snapshots
- JPEG format for optimized file size (smaller than PNG)
- Client-side processing (no data uploaded to servers)

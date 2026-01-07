# m3u8-downloader

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/superyngo/m3u8d/blob/main/m3u8_downloader.ipynb)

Download M3U8 streams and convert to MP4 using Google Colab.

## Features

- Single file download with custom filename
- Batch download with filename/URL pairs
- Automatic Google Drive integration
- Uses [llychao/m3u8-downloader](https://github.com/llychao/m3u8-downloader) for fast downloads
- Alternative yt-dlp downloader with aria2c acceleration
- Extract M3U8 links from webpage URLs

## Usage

### 1. Mount Google Drive

Run the first cell to mount your Google Drive. Files will be saved to `drive/MyDrive/m3u8d/`.

### 2. Download Tools

Run the second cell to install:
- m3u8-downloader binary
- yt-dlp with curl-cffi support

### 3. Get M3U8 Links (Optional)

Enter a webpage URL to extract M3U8 links from the page source.

### 4. Path Setting

Set `output_dir` or use default: `drive/MyDrive/m3u8d/`

### 5. Download Options

#### m3u8-downloader (Red/Blue cells)
- **Single File Download** - Enter M3U8 URL and filename
- **Batch Download** - Enter filename/URL pairs

#### yt-dlp (Green/Orange cells)
- **Single File Download (yt-dlp)** - Uses aria2c with 16 connections
- **Batch Download (yt-dlp)** - Same batch format with yt-dlp

### Batch Format

Enter filename and URL pairs in plain text format using `\n` for line breaks:

```
"video1.mp4\nhttps://example.com/stream1.m3u8\nvideo2.mp4\nhttps://example.com/stream2.m3u8"
```

Each pair should be:
- Filename (e.g., `video1.mp4`)
- `\n` (newline separator)
- M3U8 URL
- `\n` (newline separator)
- Next filename...

Failed downloads will be skipped, and the process continues with remaining files.

## Download Records

Successful downloads are recorded to `output_dir/downloaded.txt` in format:
```
[2026-01-07 12:34:56] video.mp4 | https://example.com/stream.m3u8
```

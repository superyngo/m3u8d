# m3u8-downloader

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/superyngo/m3u8d/blob/main/m3u8_downloader.ipynb)

Download M3U8 streams and convert to MP4 using Google Colab.

## Features

- Single file download with custom filename
- Batch download with filename/URL pairs
- Automatic Google Drive integration
- Uses [llychao/m3u8-downloader](https://github.com/llychao/m3u8-downloader) for fast downloads

## Usage

### 1. Mount Google Drive

Run the first cell to mount your Google Drive. Files will be saved to `/content/drive/MyDrive/m3u8d/`.

### 2. Download Tool

Run the second cell to download the m3u8-downloader binary.

## 3. Path Setting

Set output_dir or use defalut: `/drive/MyDrive/m3u8d/`.

### 4. Single File Download

- Enter the M3U8 URL in `M3u8_link`
- Enter the output filename in `filename` (e.g., `video.mp4`)

### 5. Batch Download

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

Succesful download will be recorded to output_dir/downloaded.txt in format:
[2026-01-07 12:34:56] video.mp4 | https://example.com/stream.m3u8



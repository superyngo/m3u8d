# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

m3u8-downloader is a Google Colab-based tool for downloading M3U8 streams and converting them to MP4 files. The entire project is contained in a single Jupyter notebook (`m3u8_downloader.ipynb`) designed to run in Google Colab.

## Architecture

The notebook has two main cells:
1. **Google Drive Mount** - Mounts the user's Google Drive for saving downloaded videos
2. **M3U8 Download** - Takes an M3U8 URL and output path, then uses ffmpeg and the `m3u8downloader` Python package to download and convert the stream

## Dependencies

- ffmpeg (installed via apt in Colab)
- m3u8downloader Python package (installed via pip)

## Key Technical Details

- Uses `downloadm3u8` CLI tool from the m3u8downloader package
- Default output location: `/content/drive/MyDrive/myvideo.mp4`
- Designed exclusively for Google Colab environment (uses Colab-specific drive mounting)

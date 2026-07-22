# NCM to WAV

🌐 **Language:** English | [中文](README.zh-CN.md)

A browser-based batch converter for `.ncm` audio files. The tool reads local NCM files, decrypts the embedded audio stream in the browser, decodes it with the Web Audio API, wraps the result as WAV, and downloads converted files in ZIP batches.

All processing happens locally in the browser. Files are not uploaded to a server.

## 🚀 Live Demo

https://ybjdebao.github.io/NCM-to-WAV/

## ✨ Features

- Drag-and-drop interface for selecting multiple `.ncm` files.
- Batch conversion from NCM to WAV.
- Local browser processing with JavaScript.
- ZIP packaging powered by JSZip.
- Automatic part-based packaging, with up to 40 converted tracks per ZIP file.
- Download queue for smoother consecutive downloads.
- Manual download buttons for generated ZIP parts.
- Progress list with per-file status updates.

## 📦 How to Use

1. Open the live demo.
2. Allow pop-ups/downloads for the site if your browser asks.
3. Drag `.ncm` files into the drop zone, or click the drop zone to choose files.
4. Wait while the files are read, converted, and packaged.
5. Download each generated ZIP part.
6. Extract the ZIP files to access the converted `.wav` files.

## 🛠️ Local Development

This is a static web page. No build tool is required.

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## 📁 Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── static.yml
├── index.html
├── README.md
└── README.zh-CN.md
```

## 🧩 Technical Overview

The converter is built with:

- CryptoJS for AES operations used during NCM parsing.
- Web Audio API for browser-side audio decoding.
- A small WAV writer that serializes decoded PCM audio into a WAV container.
- JSZip for packaging converted files into downloadable ZIP archives.
- Tailwind CSS loaded from a CDN for the interface.

## ⚠️ Limitations

- Browser memory limits apply, especially for large batches or long audio files.
- Conversion success depends on whether the browser can decode the decrypted audio stream.
- Some browsers may block repeated automatic downloads unless pop-ups or downloads are allowed for the site.
- The output is WAV, which is typically much larger than compressed audio formats.

## 📜 Legal Notice

Use this tool only with audio files that you own or are otherwise authorized to convert. Respect copyright, licensing terms, and platform rules for any media you process.

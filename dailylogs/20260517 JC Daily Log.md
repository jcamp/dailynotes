## JC Daily software and notes

**20260516**

### Deskflow - control multiple PC's from your PC

https://github.com/deskflow/deskflow

**Deskflow** is a free and open source keyboard and mouse sharing app. Use the keyboard, mouse, or trackpad of one computer to control nearby computers, and work seamlessly between them. It's like a software KVM (but without the video). TLS encryption is enabled by default. Wayland is supported. Clipboard sharing is supported.

### Glance Windows - FEED reader in your local dashboard - 5 / 5 stars

https://github.com/glanceapp

https://github.com/glanceapp/glance

A lightweight, highly customizable dashboard that displays
your feeds in a beautiful, streamlined interface

See also community widgets: https://github.com/glanceapp/community-widgets

https://github.com/glanceapp/glance/blob/main/docs/configuration.md#configuring-glance

Download and extract the executable from the [latest release](https://github.com/glanceapp/glance/releases/latest) (most likely the file called `glance-windows-amd64.zip` if you're on a 64-bit system) and place it in a folder of your choice. Then, create a new text file called `glance.yml` in the same folder and paste the content from [here](https://raw.githubusercontent.com/glanceapp/glance/refs/heads/main/docs/glance.yml) in it. You should then be able to run the executable and access the dashboard by visiting `http://localhost:8080` in your browser.

### Win11 Debloat

https://github.com/Raphire/Win11Debloat

Win11Debloat is a lightweight, easy to use PowerShell script that allows you to quickly declutter and customize your Windows experience. It can remove pre-installed bloatware apps, disable telemetry, remove intrusive interface elements and much more. No need to painstakingly go through all the settings yourself or remove apps one by one. Win11Debloat makes the process quick and easy!

The script also includes many features that system administrators and power users will enjoy. Such as a powerful command-line interface, support for Windows Audit mode and the option to make changes to other Windows users. Please refer to our [wiki](https://github.com/Raphire/Win11Debloat/wiki/) for more details.

### Feedly Pro (RSS Reader - free and paid for)

https://feedly.com/i/my/me

### Screencap.me - capture screen - PIP and audio via a browser window

https://github.com/mmiscool/screencap.me

This repo contains a no-nonsense browser app for grabbing your screen + microphone, importing existing clips, dropping in title cards, trimming, and exporting one stitched video without touching FFmpeg or a backend.

Why use it

- Start capturing screen + mic instantly; every stop creates a new clip
- Import local video files to mix with recorded clips
- Add title blocks with editable text, font, color, alignment, duration, and optional background images (cover/contain)
- Trim start/end per clip with drag handles or numeric fields; reorder via drag or ↑/↓ controls
- Optional Webcam PiP so you can float your face cam while recording the screen
- Mic offset control (ms) to line up your audio with Webcam PiP if the camera feed lags
- Export the final video fully in-browser (canvas + MediaRecorder) as webm with a live render overlay + preview (and cancel)
- Save/load projects as a single JSON file (clips, title settings, and assets are embedded as base64)
- Zero installs or builds—just open `index.html` on `localhost`

Quick start

1. Run a simple local server in the repo (screen capture needs a secure context):
    `python -m http.server 8000` then open [http://localhost:8000](http://localhost:8000/)

## Video to Gif (convert video part to animated gif all in the browser!)

https://github.com/mmiscool/vid2gif.net

Browser-based video-to-GIF conversion with no external runtime dependencies.

Repo: [https://github.com/mmiscool/vid2gif.net](https://github.com/mmiscool/vid2gif.net)

### What It Does

- Loads a local video file directly in the browser
- Lets you choose start and end time plus frame rate
- Preserves aspect ratio while resizing the GIF output
- Offers scale presets with visible output dimensions
- Generates an animated GIF locally in the page
- Exports a downloadable `.gif` without sending media to a server

### VideoLow (clip and transcode video)

https://github.com/andreasGBL/VideoLow

VideoLow is a lightweight, free tool for Windows based on [ffmpeg](https://github.com/FFmpeg/FFmpeg) that allows you to compress, transcode and trim /clip mp4 videos (and also audio files (mp3 and aac)) easily. This is the perfect tool if you want to create a clip from a video to send to your friends. Avoid large file sizes by selecting a smaller bitrate and speed up the process by utilizing your GPU.

It currently supports h.264 and hevc (h.265) video codecs, as well as mp3 and aac audio codecs. The GUI is made with [QT 5](https://github.com/qt/qt5).

### js2flowchart.js

https://github.com/Bogdan-Lyashenko/js-code-to-svg-flowchart

js2flowchart is a tool for generating beautiful SVG flowcharts™ from JavaScript code.

### VSCode for the Web (web interface)

https://vscode.dev/

https://code.visualstudio.com/docs/setup/vscode-web

Visual Studio Code for the Web provides a free, zero-install Microsoft Visual Studio Code experience running entirely in your browser, allowing you to quickly and safely browse source code repositories and make lightweight code changes. To get started, go to [https://vscode.dev](https://vscode.dev/) in your browser.

VS Code for the Web has many of the features of VS Code Desktop that you love, including search and syntax highlighting while browsing and editing, along with extension support to work on your codebase and make simpler edits. In addition to opening repositories, forks, and pull requests from source control providers like GitHub and Azure Repos, you can also work with code that is stored on your local machine.

VS Code for the Web runs entirely in your web browser, so there are certain limitations compared to the desktop experience, which you can read more about [below](https://code.visualstudio.com/docs/setup/vscode-web#_limitations).

The following video gives a quick overview of Visual Studio Code for the Web.


# Panda3D WebGL Editor & Demos

[![GitHub Pages Build](https://github.com/ShivamKR12/Panda3D-WebGL-Editor/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/ShivamKR12/Panda3D-WebGL-Editor/actions)
[![Build Status](https://img.shields.io/badge/Pages_Build-passing-brightgreen?style=flat&logo=github)](https://github.com/ShivamKR12/Panda3D-WebGL-Editor/actions)
[![Deploy Status](https://img.shields.io/badge/Pages_Deploy-success-blue?style=flat&logo=github)](https://github.com/ShivamKR12/Panda3D-WebGL-Editor/actions)
[![Report Status](https://img.shields.io/badge/Report_Status-online-success?style=flat&logo=github)](https://github.com/ShivamKR12/Panda3D-WebGL-Editor/actions)

A browser-based suite of Panda3D demos and a live Python IDE, powered by WebAssembly and Emscripten. This repository demonstrates the capability of running the **[Panda3D](https://www.panda3d.org/)** game engine directly inside a web browser without requiring any local SDK installation.

## 🌟 Features

This project features a mobile-responsive web launcher (`index.html`) that gives you access to three main WebGL applications:

* **💻 Live Python Editor:** An interactive, split-pane IDE using the Ace Code Editor. It allows you to write Panda3D Python code and instantly render the 3D results in the adjacent WebGL canvas. It includes pre-loaded samples such as:
    * Hello World
    * Asteroids Demo
    * Music Box
    * Emscripten API interactions & asynchronous texture downloading.
* **🐻 Roaming Ralph Demo:** A WebAssembly port of the classic Panda3D 3D character controller demo. Features a responsive split layout with a live console output stream.
* **🎯 Simple FPS Demo:** A compiled first-person shooter prototype demonstrating physics and 3D rendering natively in the browser.

## 🛠️ Tech Stack

* **Engine:** Panda3D (compiled from C++ to WebAssembly)
* **Language Environment:** Python 3.12 (via bundled CPython for Emscripten)
* **Compiler Toolkit:** Emscripten (`emsdk`)
* **Web Technologies:** HTML5 Canvas, WebGL, CSS3 (Roboto Font, FontAwesome)
* **Code Editor:** Ace Editor (Monokai theme)

## 📁 Repository Structure

* `/editor/` - Contains the WebGL canvas, Ace Editor assets, and `editor.html` interface.
* `/roaming-ralph/` - Contains the compiled WebAssembly binaries, data files, and HTML wrapper for the Roaming Ralph demo.
* `/simple_fps/` - Contains the assets and HTML layout for the Simple FPS demo.
* `/emsdk/` - The Emscripten SDK toolkit required to compile Panda3D C++ and Python into WebAssembly.
* `/thirdparty/emscripten-libs/python/` - Pre-compiled static libraries for Python 3.12 used during the build step.
* `index.html` - The main, mobile-responsive launcher page.

## 🚀 Running Locally

Because WebAssembly and asynchronous resource loading (like `.egg`/`.bam` models or `.ogg` sounds) rely on XHR/Fetch APIs, you cannot run these files directly by double-clicking the HTML files (i.e., using the `file://` protocol). You must serve them through a local web server.

If you have Python installed on your system, you can easily host it locally:

1. Clone the repository:
   ```bash
   git clone [https://github.com/ShivamKR12/Panda3D-WebGL-Editor.git](https://github.com/ShivamKR12/Panda3D-WebGL-Editor.git)
   cd Panda3D-WebGL-Editor

```

2. Start a local HTTP server:
```bash
python -m http.server 8000

```


3. Open your browser and navigate to:
`http://localhost:8000/index.html`

## 🔨 Building from Source

*(Note: The repository already contains the pre-compiled `.wasm`, `.js`, and `.data` files so you don't need to build them to run the demos.)*

If you wish to modify the C++ source or the Python bundling, the repository is set up with Emscripten. The Emscripten SDK (`emsdk`) is included directly in the repository to make setting up the build environment straightforward. Python build scripts (`freezify.py`, `build.sh`) are provided within the specific demo directories to package Python code and assets into Emscripten virtual file systems (`.data`).

## 📜 Credits

* A massive thank you to [**rdb**](https://github.com/rdb) for their invaluable help, guidance, and foundational work on the Panda3D WebGL port that made this project possible.
* Powered by the open-source community behind **Panda3D**.
* Compiled using **Emscripten**.
* In-browser code editing provided by **Ace Editor**.

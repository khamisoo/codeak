# Download CodeAK for Windows

This folder is the download page for the desktop app. The installer is the GitHub release file, because GitHub does not accept a file this large as a normal file in the repository.

**[Download CodeAK-Setup.exe](https://github.com/khamisoo/codeak/releases/download/v1.0.0/CodeAK-Setup.exe)**

| | |
| --- | --- |
| File | `CodeAK-Setup.exe` |
| Version | 1.0.0 |
| Architecture | x64 |
| SHA-256 | `9490364ff5b164a6ecf2f50e37b3a03532cfcb023e285bd3a752dad71917eb88` |
| Signed | No |

## Run it

1. Download `CodeAK-Setup.exe`.
2. Compare the SHA-256 if you want to confirm the file.
3. Run the setup file. Windows warns because the file is unsigned. That warning is expected for this release.
4. Open **CodeAK** from the desktop shortcut or the Start menu.

You do not clone this repository. You do not install Node. The installer already contains the app and the agent catalog that was packed into this version.

Setup checks Windows 10 22H2 or Windows 11, 64-bit. It reuses a MongoDB 6, 7, or 8 that already answers on `127.0.0.1:27017`, and an Ollama API that already answers on `http://127.0.0.1:11434`. If either is missing, setup downloads and installs that piece for this computer. A model is not downloaded during setup. Git Bash and Python stay optional.

About 8 GB free is enough when those downloads are required.

## After it opens

The window is the CodeAK dashboard. **Usage guide** in the sidebar explains every module. The same text is in [the usage guide](../docs/usage-guide.md).

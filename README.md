# CodeAK

CodeAK is a Windows desktop app for a local catalog of specialist agents. It runs on your computer. Chat, jobs, and files stay on that computer. There is no account and no sign-in.

Download the installer from [desktop-exe](desktop-exe/README.md). You do not clone a repository, and you do not install Node.

## What you can do

- Browse the agent catalog by division and read what each agent is for.
- Install agents into a tool on your PC, such as Cursor, when Git Bash is available.
- Build a local agent on top of a model you already have in Ollama.
- Chat with that local agent. A file you send belongs to that chat only.
- Save collections, follow a runbook, and read the activity log.
- See this computer’s CPU, memory, GPU, disk, and temperatures, and set budgets for the next local job.

## How it works

CodeAK opens a window on your PC and serves the dashboard at `http://127.0.0.1:3000`. Nothing in the app is an account on the internet.

- **MongoDB** stores projects, chat, jobs, collections, and the activity log. Setup reuses a MongoDB 6, 7, or 8 that already answers on `127.0.0.1:27017`. If none does, setup installs a private database that listens only on this computer.
- **Ollama** runs local models. Setup reuses an Ollama API that already answers on `http://127.0.0.1:11434`. If it is missing, setup installs Ollama. A model is not inside the installer. CodeAK can download one later.
- **Git Bash** and **Python** are optional. Bash is used to install catalog agents into tools. Python is used for weight training.

Redis is not part of CodeAK.

## What a client needs

- Windows 10 22H2 or Windows 11, 64-bit.
- About 8 GB free when setup must download MongoDB or Ollama. Less is enough when both are already running.
- The installer: [CodeAK-Setup.exe](https://github.com/khamisoo/codeak/releases/download/v1.0.0/CodeAK-Setup.exe).

Run `CodeAK-Setup.exe`, then open CodeAK from the shortcut. The full steps, the checksum, and the Windows warning are in [desktop-exe](desktop-exe/README.md).

## How to use it

The module-by-module guide is [docs/usage-guide.md](docs/usage-guide.md). The same guide is inside the app under **Usage guide** in the sidebar.

Start on the Dashboard. Confirm MongoDB and Ollama are connected. Build or open one local agent, then use Chat for that agent. Install catalog agents into a tool only when you want them in that tool.

## This installer is unsigned

`CodeAK-Setup.exe` is version 1.0.0 for 64-bit Windows. It is not code-signed. Windows SmartScreen warns before it runs. That warning is expected for this release.

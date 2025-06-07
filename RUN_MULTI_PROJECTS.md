## 🚀 Running Multiple Services with One Command using `tmux`

This project provides a `Makefile` target called `run-app` that uses [`tmux`](https://github.com/tmux/tmux/wiki) to launch **two interactive terminal panes**, each running a separate service from different directories.

---

### ✅ Prerequisites

Ensure the following are installed on your system:

- [`tmux`](https://github.com/tmux/tmux/wiki)
- [`pnpm`](https://pnpm.io/)
- [`nvm`](https://github.com/nvm-sh/nvm)
- Node.js `v20` installed via `nvm`

#### 🛠 Install `tmux`:

```bash
# macOS
brew install tmux

# Ubuntu/Debian
sudo apt install tmux
```

## 📂 Customize Your Project Paths

Update the Makefile with your actual service folders.

Example structure:

```bash
project-root/
├── service-a/
└── service-b/
```

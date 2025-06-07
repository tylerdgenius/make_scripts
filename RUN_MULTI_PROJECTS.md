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

### 📂 Customize Your Project Paths

Update the Makefile with your actual service folders.

Example structure:

```bash
project-root/
├── service-a/
└── service-b/
```
Replace service-a and service-b below with your actual directories.

### 🧾 Makefile Target

```make
run-app:
	tmux new-session -d -s devsession 'cd service-a && export NVM_DIR="$$HOME/.nvm" && source $$NVM_DIR/nvm.sh && nvm use 20 && pnpm start:dev'
	tmux split-window -v -t devsession 'cd service-b && export NVM_DIR="$$HOME/.nvm" && source $$NVM_DIR/nvm.sh && nvm use 20 && pnpm start:dev'
	tmux select-layout -t devsession tiled
	tmux attach -t devsession
```

### ▶️ Usage

To launch both services in an interactive tmux session:

```bash
make run-app
```

This will:
-- Start a new tmux session named devsession
-- Open a pane for each service
-- Run pnpm start:dev in each
-- Attach you to the session


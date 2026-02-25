# nabu-cli

CLI tools to connect to persistent Claude Code sessions via tmux.

- **`nabu`** — attaches to / creates tmux session `nabu`, resumes Claude Code session
- **`worker`** — attaches to / creates tmux session `worker`, resumes Claude Code session

Both handle nested tmux: if already inside tmux, claude runs directly without creating a new session.

## Setup

```bash
git clone https://github.com/NG-Bullseye/nabu-cli.git
cd nabu-cli
bash setup.sh
```

`setup.sh` asks for:
- Claude Code session ID for `nabu`
- Claude Code session ID for `worker`
- Working directory (where claude runs)

Session IDs stay in a local `config` file (git-ignored).

## Usage

```bash
nabu      # attach to 'nabu' tmux session (or create it) + claude --resume <id>
worker    # attach to 'worker' tmux session (or create it) + claude --resume <id>
```

## Requirements

- `bash`, `tmux`
- `claude` CLI installed

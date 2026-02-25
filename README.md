# nabu-cli

CLI for interacting with [claude-chat-service](https://github.com/NG-Bullseye/claude-chat-service) — a persistent Claude Code session over HTTP.

## Tools

- **`nabu`** — Send messages to Claude, maintains session continuity
- **`worker`** — tmux session manager

## Setup

```bash
git clone https://github.com/NG-Bullseye/nabu-cli.git
cd nabu-cli
bash setup.sh
```

`setup.sh` asks for:
- **Claude Chat Service URL** (e.g. `http://192.168.1.225:8765`)
- **Session ID** (optional — for continuing an existing Claude conversation)

Get the current session ID from a running service:
```bash
curl http://<host>:8765/health
```

Credentials stay in a local `config` file (git-ignored).

## Usage

```bash
nabu "Hallo Claude"
nabu --health       # check service connectivity
nabu --session      # show current session ID
nabu --reset        # clear session (start fresh)
nabu --verbose      # show full JSON response

nabu-worker         # attach/create tmux session
```

## Requirements

- `bash`, `curl`, `python3`
- `tmux` (for `nabu-worker`)
- Running [claude-chat-service](https://github.com/NG-Bullseye/claude-chat-service)

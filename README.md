# nabu-cli

CLI tools for interacting with a Home Assistant Conversation Agent.

## Tools

- **`nabu`** — Send messages to your HA conversation agent from the terminal
- **`worker`** — tmux session manager (persistent terminal session)

## Setup

```bash
git clone https://github.com/YOUR_USERNAME/nabu-cli.git
cd nabu-cli
bash setup.sh
```

`setup.sh` will ask for:
- Home Assistant URL
- Long-lived Access Token
- Conversation Agent ID
- Default language

Credentials are stored in a local `config` file (git-ignored).

## Usage

```bash
nabu "Hallo, was geht?"
nabu "turn on the lights"
nabu --reset        # start new conversation
nabu --show-id      # show current conversation ID
nabu --verbose      # show full API response
nabu --lang en "Hello"

nabu-worker         # attach/create tmux session
```

## Requirements

- `bash`
- `curl`
- `python3`
- `tmux` (for `nabu-worker`)

## Config

Copy `config.example` to `config` and fill in your values manually instead of using `setup.sh`:

```bash
cp config.example config
# edit config with your values
```

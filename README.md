# nabu-cli

CLI for the Home Assistant Conversation Agent — send messages, maintain conversation context, view logs.

## Tools

- **`nabu`** — Talk to the HA conversation agent from the terminal
- **`worker`** — Attach to / create a persistent tmux session named `nabu`

## Setup

```bash
git clone https://github.com/NG-Bullseye/nabu-cli.git
cd nabu-cli
bash setup.sh
```

`setup.sh` asks for:
- Home Assistant URL
- Long-lived Access Token
- Conversation Agent ID
- Default language
- Conversation ID (optional — to continue an existing session)

Get the current conversation ID on the HA host:
```bash
nabu --show-id
```

Credentials stay in a local `config` file (git-ignored).

## Usage

```bash
nabu "Hi was geht?"
nabu "turn on the lights"
nabu --reset              # start new conversation
nabu --show-id            # show current conversation ID
nabu --logs               # tail HA log filtered to conversation lines
nabu --lang en "Hello"
nabu --verbose "test"     # show full API response

worker                    # attach to / create tmux session 'nabu'
```

## Requirements

- `bash`, `curl`, `python3`
- `tmux` (for `worker`)

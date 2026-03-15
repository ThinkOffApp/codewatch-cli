# codewatch-cli

Get IDE notifications on your phone and watch. Reply by voice.

CodeWatch connects your coding agents (Claude Code, Codex, Cursor, VS Code, Windsurf, Aider) to the CodeWatch app on your phone and smartwatch. When your agent finishes a task, hits a blocker, or needs approval, you get a notification. Reply from the couch.

## Install

```bash
npm install -g github:ThinkOffApp/codewatch-cli
```

## Setup

```bash
codewatch connect    # Detects IDEs, installs hooks, saves config
codewatch watch      # Start reply poller (delivers replies to your IDE)
```

## Commands

```
codewatch connect       Detect IDEs and install notification hooks
codewatch watch         Start reply poller (delivers replies to your IDE)
codewatch notify <msg>  Send a test notification to your phone/watch
codewatch status        Show connection status and installed hooks
codewatch disconnect    Remove all CodeWatch hooks
codewatch version       Show version
```

## How it works

1. **Hooks** fire on IDE events (task complete, permission needed) and POST to the relay
2. **Relay** pushes notifications to the CodeWatch app on your phone/watch
3. **You reply** by voice or text from the app
4. **Poller** picks up your reply and injects it into the IDE's tmux session

## Supported IDEs

- Claude Code
- OpenAI Codex
- Cursor
- VS Code
- Windsurf
- Aider

Adding a new IDE: implement `detect_*()` and `install_*_hook()` in `bin/codewatch`.

## Get the app

Phone and watch apps available at [codewatch.app](https://codewatch.app)

## License

AGPL-3.0

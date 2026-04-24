# agent-settings

A central place to store and version-control global settings for coding agents.

## Structure

Each agent gets its own directory. The file name inside mirrors the convention
the agent uses when it looks for a global instructions file:

```
agent-settings/
├── codex/
│   └── AGENTS.md      # symlink / copy to ~/.codex/AGENTS.md
└── claude/
    └── CLAUDE.md      # symlink / copy to ~/CLAUDE.md
```

## How to use

### Codex

Codex reads global instructions from `~/.codex/AGENTS.md`.

```bash
mkdir -p ~/.codex
ln -sf "$(pwd)/codex/AGENTS.md" ~/.codex/AGENTS.md
```

### Claude Code

Claude Code reads project-level instructions from `CLAUDE.md` in your home
directory (or any parent directory of your project).

```bash
ln -sf "$(pwd)/claude/CLAUDE.md" ~/CLAUDE.md
```

## Adding a new agent

1. Create a new directory named after the agent (e.g. `gemini/`).
2. Add the agent's instructions file using the name it expects (e.g. `gemini/GEMINI.md`).
3. Document the symlink / copy step in this README under a new section.

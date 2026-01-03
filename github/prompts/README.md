# GitHub Prompts

## Known issues

### Copilot fails to capture terminal output

GitHub Copilot may fail to capture terminal output, often returning `No output was produced by the command.`

This may be caused by interactive shell tooling (for example **Oh My Posh**) injecting prompt logic and escape sequences.

#### Resolution

Configure a **chat-specific terminal profile** so Copilot runs commands in a clean, non-interactive shell.

#### Example (Windows)

Add the following to your VS Code `settings.json`:

```json
{
    "chat.tools.terminal.terminalProfile.windows": {
        "path": "C:\\Program Files\\Git\\bin\\bash.exe",
        "args": [],
        "env": {
            "COPILOT": "1"
        }
    }
}
```

### References

- GitHub discussion: [Copilot does not detect terminal command has completed or is not getting terminal output #161238](https://github.com/orgs/community/discussions/161238)
- Visual Studio Code: [Chat terminal profiles](https://code.visualstudio.com/updates/v1_105#_chat-terminal-profiles)

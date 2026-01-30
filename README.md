# Claude Code Persona Plugins

A marketplace of output-style plugins for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) that make Claude respond in the voice and mannerisms of fictional characters. Each plugin injects a persona directive at session start via a `SessionStart` hook, changing Claude's delivery style while keeping all technical output 100% accurate.

## Available Personas

| Plugin | Character | Source |
|--------|-----------|--------|
| [tony-soprano-output-style](./plugins/tony-soprano-output-style/) | Tony Soprano | The Sopranos |
| [johnny-silverhand-output-style](./plugins/johnny-silverhand-output-style/) | Johnny Silverhand | Cyberpunk 2077 |
| [dr-venture-output-style](./plugins/dr-venture-output-style/) | Dr. Thaddeus "Rusty" Venture | The Venture Bros |
| [john-mcafee-output-style](./plugins/john-mcafee-output-style/) | John McAfee (fictional caricature) | Original |
| [moe-szyslak-output-style](./plugins/moe-szyslak-output-style/) | Moe Szyslak | The Simpsons |
| [glados-output-style](./plugins/glados-output-style/) | GLaDOS | Portal |
| [solaire-output-style](./plugins/solaire-output-style/) | Solaire of Astora | Dark Souls |
| [ron-swanson-output-style](./plugins/ron-swanson-output-style/) | Ron Swanson | Parks and Recreation |
| [david-attenborough-output-style](./plugins/david-attenborough-output-style/) | David Attenborough | Nature Documentary |
| [gandalf-output-style](./plugins/gandalf-output-style/) | Gandalf | The Lord of the Rings |
| [cave-johnson-output-style](./plugins/cave-johnson-output-style/) | Cave Johnson | Portal |
| [werner-herzog-output-style](./plugins/werner-herzog-output-style/) | Werner Herzog (fictional caricature) | Original |

## Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed and authenticated

## Installation

### Option 1: Install from this marketplace (recommended)

First, register this repository as a plugin marketplace. You only need to do this once.

**If this repo is on GitHub:**

```bash
claude plugin marketplace add owner/repo-name
```

**If you have it cloned locally:**

```bash
claude plugin marketplace add /absolute/path/to/this/repo/plugins
```

Then install any plugin by name:

```bash
claude plugin install tony-soprano-output-style@local
```

The `@local` suffix refers to the marketplace name defined in `plugins/.claude-plugin/marketplace.json`. Replace it with whatever name your marketplace uses.

You can also install from within a Claude Code session using slash commands:

```
/plugin marketplace add /absolute/path/to/this/repo/plugins
/plugin install tony-soprano-output-style@local
```

#### Installation scope

By default, plugins install to your user scope (`~/.claude/settings.json`), making them available across all projects. You can also choose a different scope:

```bash
# Available in all your projects (default)
claude plugin install tony-soprano-output-style@local --scope user

# Shared with your team via version control (.claude/settings.json)
claude plugin install tony-soprano-output-style@local --scope project

# Project-specific, gitignored (.claude/settings.local.json)
claude plugin install tony-soprano-output-style@local --scope local
```

#### Managing installed plugins

```bash
claude plugin disable tony-soprano-output-style@local
claude plugin enable tony-soprano-output-style@local
claude plugin uninstall tony-soprano-output-style@local
```

### Option 2: Load directly for testing

If you just want to try a plugin without installing it, pass the plugin directory at launch:

```bash
claude --plugin-dir ./plugins/tony-soprano-output-style
```

You can load multiple plugins at once:

```bash
claude --plugin-dir ./plugins/glados-output-style --plugin-dir ./plugins/solaire-output-style
```

> **Note:** Only one persona plugin should be active at a time. Loading multiple persona plugins will result in conflicting style directives.

## How It Works

Each plugin uses a [SessionStart hook](https://docs.anthropic.com/en/docs/claude-code/hooks) to inject a persona directive into Claude's context when a session begins. Here's the flow:

1. Claude Code starts a new session
2. The `SessionStart` hook fires and runs the plugin's `hooks-handlers/session-start.sh` script
3. The script outputs a JSON payload with an `additionalContext` field containing the full persona directive
4. Claude receives this directive and adopts the character's voice for the entire session

The persona directive includes rules for voice/tone, signature phrases, metaphors, and character-specific behavior — while explicitly requiring that all technical content remains accurate.

## Plugin Structure

Every plugin in this marketplace follows the same structure:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json              # Plugin metadata (name, version, description, author)
├── hooks/
│   └── hooks.json               # Hook configuration — registers the SessionStart hook
├── hooks-handlers/
│   └── session-start.sh         # Shell script that outputs the persona directive as JSON
└── README.md                    # Plugin documentation
```

### Key files explained

**`.claude-plugin/plugin.json`** — Plugin identity and metadata:

```json
{
  "name": "example-output-style",
  "version": "1.0.0",
  "description": "Output style that makes Claude respond as Example Character",
  "author": {
    "name": "your-name"
  }
}
```

**`hooks/hooks.json`** — Registers a `SessionStart` hook that runs the persona script:

```json
{
  "description": "Example output style hook",
  "hooks": {
    "SessionStart": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "${CLAUDE_PLUGIN_ROOT}/hooks-handlers/session-start.sh"
          }
        ]
      }
    ]
  }
}
```

`${CLAUDE_PLUGIN_ROOT}` is a built-in environment variable that resolves to the absolute path of the plugin directory at runtime.

**`hooks-handlers/session-start.sh`** — Outputs the persona directive as structured JSON. Must exit with code `0` on success:

```bash
#!/usr/bin/env bash
cat <<'EOF'
{
  "hookSpecificOutput": {
    "hookEventName": "SessionStart",
    "additionalContext": "IMPORTANT — OUTPUT STYLE DIRECTIVE: You must adopt the voice of... [full persona rules here]"
  }
}
EOF
exit 0
```

The `additionalContext` string is where the entire persona definition lives — voice rules, signature phrases, metaphors, philosophical style, and the mandate to keep technical accuracy intact.

## Creating Your Own Persona Plugin

1. **Copy an existing plugin** as a starting point:

   ```bash
   cp -r plugins/tony-soprano-output-style plugins/your-character-output-style
   ```

2. **Edit `.claude-plugin/plugin.json`** — Update the `name` and `description`:

   ```json
   {
     "name": "your-character-output-style",
     "version": "1.0.0",
     "description": "Output style that makes Claude respond as Your Character",
     "author": {
       "name": "your-name"
     }
   }
   ```

3. **Edit `hooks/hooks.json`** — Update the description (the hook command stays the same):

   ```json
   {
     "description": "Your Character output style hook",
     "hooks": {
       "SessionStart": [
         {
           "hooks": [
             {
               "type": "command",
               "command": "${CLAUDE_PLUGIN_ROOT}/hooks-handlers/session-start.sh"
             }
           ]
         }
       ]
     }
   }
   ```

4. **Edit `hooks-handlers/session-start.sh`** — Replace the persona directive with your character's rules. The directive should define:

   - **Voice & Tone** — How the character speaks
   - **Signature phrases** — Catchphrases and speech patterns to use
   - **Metaphors & analogies** — The character's frame of reference for technical concepts
   - **Confidence level** — How the character carries themselves
   - **Philosophical style** — How the character reflects on bigger-picture topics
   - **Technical accuracy mandate** — Always include a rule stating code and advice must remain correct
   - **Content guardrails** — Keep output appropriate (no profanity, etc.)

   Make sure the script is executable:

   ```bash
   chmod +x plugins/your-character-output-style/hooks-handlers/session-start.sh
   ```

5. **Register it in the marketplace** (optional) — Add an entry to `plugins/.claude-plugin/marketplace.json`:

   ```json
   {
     "name": "your-character-output-style",
     "source": "./your-character-output-style",
     "description": "Output style that makes Claude respond as Your Character"
   }
   ```

6. **Test it:**

   ```bash
   claude --plugin-dir ./plugins/your-character-output-style
   ```

## Troubleshooting

- **Plugin not loading?** Make sure `session-start.sh` is executable (`chmod +x`).
- **No persona applied?** Verify the JSON output from `session-start.sh` is valid — run the script manually and check for syntax errors: `bash ./plugins/your-plugin/hooks-handlers/session-start.sh | jq .`
- **Permission prompt on first use?** Claude Code will ask you to approve the hook command the first time. Accept it to allow the plugin to run.
- **Want to see hook output?** Run Claude Code in verbose mode to see hook execution details: `claude --verbose`

## References

- [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Hooks documentation](https://docs.anthropic.com/en/docs/claude-code/hooks)
- [Plugin creation guide](https://code.claude.com/docs/en/plugins)
- [Plugin reference](https://code.claude.com/docs/en/plugins-reference)
- [Discover and install plugins](https://code.claude.com/docs/en/discover-plugins)

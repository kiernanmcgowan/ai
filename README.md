# Claude Code Persona Plugins

Output-style plugins for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) that make Claude respond in the voice of fictional characters. Technical output stays 100% accurate — only the delivery changes.

## Available Personas

| Plugin | Character | Source |
|--------|-----------|--------|
| `tony-soprano-output-style` | Tony Soprano | The Sopranos |
| `johnny-silverhand-output-style` | Johnny Silverhand | Cyberpunk 2077 |
| `dr-venture-output-style` | Dr. Thaddeus "Rusty" Venture | The Venture Bros |
| `john-mcafee-output-style` | John McAfee (fictional caricature) | Original |
| `moe-szyslak-output-style` | Moe Szyslak | The Simpsons |
| `glados-output-style` | GLaDOS | Portal |
| `solaire-output-style` | Solaire of Astora | Dark Souls |
| `ron-swanson-output-style` | Ron Swanson | Parks and Recreation |
| `david-attenborough-output-style` | David Attenborough | Nature Documentary |
| `gandalf-output-style` | Gandalf | The Lord of the Rings |
| `cave-johnson-output-style` | Cave Johnson | Portal |
| `werner-herzog-output-style` | Werner Herzog (fictional caricature) | Original |

## Quick Start

**1. Add the marketplace** (one-time setup):

```bash
claude plugin marketplace add kiernanmcgowan/ai
```

**2. Install a persona:**

```bash
claude plugin install tony-soprano-output-style@local
```

Replace `tony-soprano-output-style` with any plugin name from the table above.

**3. Start Claude Code:**

```bash
claude
```

The persona activates automatically. No additional configuration needed.

> **Note:** Only one persona plugin should be active at a time.

## Managing Plugins

```bash
# Disable a persona
claude plugin disable tony-soprano-output-style@local

# Re-enable it
claude plugin enable tony-soprano-output-style@local

# Uninstall it
claude plugin uninstall tony-soprano-output-style@local
```

## Troubleshooting

- **Permission prompt on first use?** Claude Code will ask you to approve the hook command the first time. Accept it to allow the plugin to run.
- **Plugin not loading?** Make sure `session-start.sh` is executable: `chmod +x plugins/<plugin-name>/hooks-handlers/session-start.sh`
- **Want to see hook output?** Run `claude --verbose` to see hook execution details.

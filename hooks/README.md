# hooks/ — Pre- en Post-Hooks

Hooks zijn scripts die automatisch draaien voor of na bepaalde Claude Code acties.

## Hoe werken hooks?

Hooks worden geconfigureerd in `.claude/settings.json`:

```json
{
  "hooks": {
    "preToolUse": [
      {
        "matcher": "Write",
        "command": "bash hooks/pre-write-check.sh"
      }
    ],
    "postToolUse": [
      {
        "matcher": "Write",
        "command": "bash hooks/post-write-notify.sh"
      }
    ]
  }
}
```

## Voorbeelden van hooks

| Hook | Trigger | Gebruik |
|------|---------|---------|
| `pre-write-check.sh` | Voor elk bestand schrijven | Check of pad toegestaan is |
| `post-write-notify.sh` | Na elk bestand schrijven | Toon notificatie |
| `pre-bash-check.sh` | Voor elk bash commando | Blokkeer destructieve commando's |

## Zelf een hook maken

1. Maak een script in deze map (bijv. `hooks/mijn-hook.sh`)
2. Maak het uitvoerbaar: `chmod +x hooks/mijn-hook.sh`
3. Voeg het toe aan `.claude/settings.json`

## Meer informatie

Zie de [Claude Code documentatie over hooks](https://docs.anthropic.com/en/docs/claude-code).

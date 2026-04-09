# commands/ — Custom Slash Commands

Hier kun je custom slash commands plaatsen voor Claude Code.

## Wat zijn commands?

Commands zijn snelkoppelingen die je aanroept met `/` in Claude Code. Bijvoorbeeld: `/status` of `/deploy`.

## Een command maken

Maak een Markdown-bestand in deze map:

```
commands/
├── status.md      → wordt /status
├── deploy.md      → wordt /deploy
└── review.md      → wordt /review
```

### Voorbeeld: `status.md`

```markdown
# /status

Geef een overzicht van:
1. Welke bestanden recent zijn gewijzigd
2. Of er ongecommitte changes zijn (git status)
3. Welke taken er openstaan
```

## Meer informatie

Zie de [Claude Code documentatie](https://docs.anthropic.com/en/docs/claude-code) voor alle mogelijkheden.

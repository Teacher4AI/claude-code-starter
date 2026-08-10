# .claude/commands/ — Eigen slash commands

Commands zijn snelkoppelingen die je aanroept met `/` in Claude Code, bijvoorbeeld
`/status` of `/deploy`.

## Een command maken

Maak een markdown-bestand in deze map. De bestandsnaam wordt het commando:

```
.claude/commands/
├── status.md      → /status
├── deploy.md      → /deploy
└── review.md      → /review
```

### Voorbeeld: `status.md`

```markdown
Geef een overzicht van:
1. Welke bestanden recent zijn gewijzigd
2. Of er ongecommitte wijzigingen zijn (git status)
3. Welke taken er openstaan
```

## Command of skill?

Commands en skills doen inmiddels hetzelfde. Een bestand in `.claude/commands/deploy.md`
en een skill in `.claude/skills/deploy/SKILL.md` geven allebei het commando `/deploy`.

Kies een **skill** als je meer wilt:

- Een eigen map voor bijbehorende bestanden en voorbeelden
- Frontmatter, zodat Claude de skill zelf kan oppakken wanneer hij past
- Een beschrijving die uitlegt wanneer je hem gebruikt

Kies een **command** als het bij een korte, vaste opdracht blijft.

Bestaat er een skill en een command met dezelfde naam, dan wint de skill.

## Meer informatie

Zie de [documentatie over skills en commands](https://code.claude.com/docs/en/skills).

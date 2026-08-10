# .claude/ — Configuratie

Alles wat Claude Code automatisch inleest staat in deze map: je skills, je eigen commands,
je hooks en je projectinstellingen.

| Bestand of map | Doel |
|---|---|
| `settings.json` | Projectinstellingen: permissies, hooks, omgevingsvariabelen |
| `skills/` | Herbruikbare instructies. Mapnaam wordt het commando |
| `commands/` | Eigen slash commands. Werkt naast skills |
| `hooks/` | Scripts die je vanuit `settings.json` aanroept |

## MCP-servers koppelen

MCP (Model Context Protocol) geeft Claude toegang tot externe systemen zoals e-mail,
agenda's, databases en projecttools.

### Toevoegen via de CLI (aanbevolen)

Dit is de kortste route. Claude Code schrijft de configuratie zelf naar het juiste bestand.

```bash
claude mcp add --transport http <naam> <url>
```

Bekijken wat er gekoppeld is:

```bash
claude mcp list
```

Binnen een sessie zie je de status met `/mcp`.

### Waar de configuratie terechtkomt

| Bestand | Bereik |
|---|---|
| `.mcp.json` in je project | Alleen dit project. Deel je mee in Git, handig voor een team |
| `~/.claude.json` | Al je projecten, alleen voor jou |

MCP-configuratie hoort **niet** in `settings.json`. Dat bestand is voor permissies, hooks
en omgevingsvariabelen.

### Welke servers zijn er?

Het aanbod verandert snel, dus wij houden hier geen lijst bij die veroudert. Kijk in de
[MCP-documentatie van Claude Code](https://code.claude.com/docs/en/mcp) voor de actuele
servers en de exacte commando's per stuk.

> **Let op:** bewaar API-sleutels NOOIT in een Git-repository. Gebruik omgevingsvariabelen
> of een `.env`-bestand, dat staat in `.gitignore`.

## Instellingen aanpassen

Binnen een sessie open je de instellingen met `/config`. Handmatig bewerken kan ook:

| Bestand | Bereik |
|---|---|
| `.claude/settings.json` | Dit project, deelbaar via Git |
| `.claude/settings.local.json` | Dit project, alleen voor jou. Staat in `.gitignore` |
| `~/.claude/settings.json` | Al je projecten |

Zie de [documentatie over settings](https://code.claude.com/docs/en/settings) voor alle opties.

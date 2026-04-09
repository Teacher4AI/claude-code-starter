# 🚀 Claude Code Starter

**Kant-en-klare workspace om snel aan de slag te gaan met Claude Code.**

Gemaakt door [Teacher4AI](https://teacher4ai.net) — AI-trainingen uit Rotterdam.

---

## Wat is dit?

Deze repo geeft je een werkende startstructuur voor Claude Code:

- **`CLAUDE.md`** — Template kennisbank die Claude leest bij elke sessie
- **`skills/`** — Herbruikbare instructies met een werkend voorbeeld
- **`commands/`** — Plek voor custom slash commands
- **`hooks/`** — Pre- en post-hooks voor automatisering
- **`.claude/`** — MCP configuratie voorbeelden (Gmail, Notion)
- **`cases/`** — Werkmap voor je eigen projecten
- **`data/`** — Voorbeelddata om mee te experimenteren

## Snel starten

### 1. Clone de repo

```bash
git clone https://github.com/Teacher4AI/claude-code-starter.git
cd claude-code-starter
```

### 2. Open met Claude Code

```bash
claude
```

Claude leest automatisch `CLAUDE.md` en kent je mappenstructuur.

### 3. Pas CLAUDE.md aan

Open `CLAUDE.md` en vul je eigen gegevens in:
- Jouw naam en rol
- Welke tools je gebruikt
- Je werkregels en voorkeuren

### 4. Koppel MCP servers (optioneel)

Zie `.claude/README.md` voor stap-voor-stap instructies om Gmail en Notion te koppelen.

## Mappenstructuur

```
claude-code-starter/
├── CLAUDE.md              ← Jouw kennisbank (pas deze aan!)
├── README.md              ← Dit bestand
├── .gitignore
│
├── .claude/               ← Configuratie
│   ├── README.md          ← MCP setup instructies
│   ├── mcp-config-example.json  ← Voorbeeld (geen echte keys!)
│   └── settings.json      ← Project instellingen
│
├── skills/                ← Herbruikbare instructies
│   └── hello-world/       ← Werkend voorbeeld
│       └── SKILL.md
│
├── commands/              ← Custom slash commands
│   └── README.md
│
├── hooks/                 ← Pre/post automatisering
│   └── README.md
│
├── cases/                 ← Jouw werkbestanden
│   ├── techniek/          ← Technische cases
│   │   └── README.md
│   └── onderwijs/         ← Onderwijs cases
│       └── README.md
│
└── data/                  ← Voorbeelddata
    ├── README.md
    ├── voorbeeld-leerlingen.csv
    └── voorbeeld-rubric.md
```

## Skills gebruiken

Een skill is een gestructureerde instructie die Claude stap-voor-stap volgt. Bekijk het voorbeeld in `skills/hello-world/SKILL.md` en maak je eigen skills door een nieuwe map aan te maken in `skills/`.

**Voorbeeld:**
```
Jij: "Gebruik de hello-world skill"
Claude: *leest skills/hello-world/SKILL.md en voert de stappen uit*
```

## Meer leren?

| Resource | Link |
|----------|------|
| Claude Code documentatie | [docs.anthropic.com](https://docs.anthropic.com/en/docs/claude-code) |
| MCP Protocol | [modelcontextprotocol.io](https://modelcontextprotocol.io) |
| Teacher4AI trainingen | [teacher4ai.net](https://teacher4ai.net) |

### Over Teacher4AI

Teacher4AI verzorgt praktijkgerichte AI-trainingen voor het technisch onderwijs en het MKB. Van basiskennis tot geavanceerd werken met Claude Code — altijd hands-on, altijd toepasbaar.

📍 Rotterdam | 🌐 [teacher4ai.net](https://teacher4ai.net) | 📧 info@teacher4ai.eu

---

*Deze repo is open source en vrij te gebruiken. Gemaakt met ❤️ door Teacher4AI.*

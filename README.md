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

## Wat heb je nodig?

Voordat je begint, zorg dat je het volgende hebt:

| Vereiste | Hoe installeren |
|----------|----------------|
| **Claude Code** | Volg de [installatie-instructies van Anthropic](https://docs.anthropic.com/en/docs/claude-code/getting-started) |
| **Node.js** (v18+) | Download van [nodejs.org](https://nodejs.org/) — kies de LTS versie |
| **Git** | Meestal al geinstalleerd. Test met `git --version` in je terminal |

> **Geen Git?** Geen probleem — je kunt de bestanden ook als ZIP downloaden (zie optie B hieronder).

---

## Snel starten

### Stap 1: Haal de bestanden op naar je computer

Open je **Terminal** (Mac) of **Command Prompt** (Windows) en kies een van deze opties:

**Optie A — Met Git (aanbevolen):**
```bash
git clone https://github.com/Teacher4AI/claude-code-starter.git
```
Dit maakt een map `claude-code-starter` aan op de plek waar je terminal staat (meestal je thuismap).

**Optie B — Als ZIP downloaden (zonder Git):**
1. Ga naar [github.com/Teacher4AI/claude-code-starter](https://github.com/Teacher4AI/claude-code-starter)
2. Klik op de groene knop **"<> Code"**
3. Kies **"Download ZIP"**
4. Pak het ZIP-bestand uit op een plek die je kunt vinden (bijv. je Documenten map)

### Stap 2: Ga naar de map

```bash
cd claude-code-starter
```

> **Tip:** Weet je niet waar de map staat? Op Mac kun je in Finder de map openen, dan in Terminal `cd ` typen (met spatie) en de map vanuit Finder naar het Terminal-venster slepen.

### Stap 3: Start Claude Code

```bash
claude
```

Claude Code opent en leest automatisch `CLAUDE.md` — het weet meteen hoe je workspace eruitziet.

**Test of het werkt:** typ in Claude Code:
```
Gebruik de hello-world skill
```
Claude doorloopt dan de voorbeeldstappen uit `skills/hello-world/SKILL.md`.

### Stap 4: Maak het je eigen

Open `CLAUDE.md` in een teksteditor (of vraag het aan Claude!) en vul in:
- Jouw naam en rol
- Welke tools je wilt gebruiken
- Je eigen regels en voorkeuren

### Stap 5: Koppel externe tools (optioneel)

Wil je dat Claude je email kan lezen of je Notion kan doorzoeken? Zie `.claude/README.md` voor stap-voor-stap instructies om MCP servers zoals Gmail en Notion te koppelen.

> **Let op:** Dit is optioneel. Claude Code werkt prima zonder externe tools — je kunt dit altijd later doen.

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

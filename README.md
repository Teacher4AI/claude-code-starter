# 🚀 Claude Code Starter

**Kant-en-klare workspace om snel aan de slag te gaan met Claude Code.**

Gemaakt door [Teacher4AI](https://teacher4ai.net), AI-trainingen uit Rotterdam.

---

## Wat is dit?

Deze repo geeft je een werkende startstructuur voor Claude Code:

- **`CLAUDE.md`** — Template kennisbank die Claude leest bij elke sessie
- **`.claude/skills/`** — Herbruikbare instructies, met twee werkende voorbeelden
- **`.claude/commands/`** — Plek voor eigen slash commands
- **`.claude/hooks/`** — Scripts die automatisch draaien voor of na een actie
- **`.claude/`** — Projectinstellingen en MCP-uitleg
- **`cases/`** — Werkmap voor je eigen projecten
- **`data/`** — Voorbeelddata per spoor, klaar om echt iets mee te doen

## Wat heb je nodig?

| Vereiste | Hoe |
|----------|-----|
| **Claude Code** | Zie stap 1 hieronder |
| **Een Claude-abonnement** | Pro, Max, Team of Enterprise. Het gratis Claude.ai-plan geeft geen toegang tot Claude Code |
| **Git** | Meestal al geinstalleerd. Test met `git --version` in je terminal |

> **Geen Git?** Geen probleem, je kunt de bestanden ook als ZIP downloaden. Zie optie B bij stap 2.

---

## Snel starten

### Stap 1: Installeer Claude Code

Open je **Terminal** (Mac) of **PowerShell** (Windows) en plak het commando dat bij je systeem hoort.

**macOS, Linux of WSL:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows PowerShell:**
```powershell
irm https://claude.ai/install.ps1 | iex
```

**Liever Homebrew?**
```bash
brew install --cask claude-code
```

Controleer daarna of het gelukt is:
```bash
claude --version
```

> **Liever geen terminal?** Er is ook een desktop-app. Die werkt prima, maar deze starterskit
> gaat uit van de terminal, want daar hoort het clonen van deze repo bij.

Volledige installatie-instructies en alternatieve routes staan in de
[Claude Code documentatie](https://code.claude.com/docs/en/setup).

### Stap 2: Haal deze workspace op

**Optie A, met Git (aanbevolen):**
```bash
git clone https://github.com/Teacher4AI/claude-code-starter.git
```
Dit maakt een map `claude-code-starter` aan op de plek waar je terminal staat, meestal je thuismap.

**Optie B, als ZIP (zonder Git):**
1. Ga naar [github.com/Teacher4AI/claude-code-starter](https://github.com/Teacher4AI/claude-code-starter)
2. Klik op de groene knop **"<> Code"**
3. Kies **"Download ZIP"**
4. Pak het bestand uit op een plek die je terugvindt, bijvoorbeeld je map Documenten

### Stap 3: Ga naar de map

```bash
cd claude-code-starter
```

> **Tip:** weet je niet waar de map staat? Op Mac open je hem in Finder, typ je in Terminal
> `cd ` (met een spatie) en sleep je de map naar het Terminal-venster.

### Stap 4: Start Claude Code

```bash
claude
```

De eerste keer vraagt Claude Code je om in te loggen via je browser. Daarna opent een
sessie in je terminal en leest Claude automatisch `CLAUDE.md`, zodat het meteen weet hoe
je workspace eruitziet.

**Test of het werkt:** typ in Claude Code:
```
/hello-world
```

Claude doorloopt dan de stappen uit `.claude/skills/hello-world/SKILL.md`. Zie je het
commando niet in de lijst als je `/` typt? Dan staat de skill niet op de goede plek of
mist de frontmatter bovenaan het bestand.

### Stap 5: Maak het je eigen

Open `CLAUDE.md` in een teksteditor, of vraag het aan Claude, en vul in:

- Jouw naam en rol
- Welke tools je wilt gebruiken
- Je eigen regels en voorkeuren

### Stap 6: Doe iets echts

Een begroeting is leuk, maar je wilt zien wat het je oplevert. In `data/` staat
voorbeeldmateriaal per spoor.

**Techniek.** Er staat een stilstandsregistratie van een productiebedrijf klaar: drie
lijnen, een vol jaar, ongeveer 1350 meldingen, met alle rommel die er in het echt ook in
zit. Typ in Claude Code:

```
/stilstandsrapport
```

Claude leest het bestand, groepeert de oorzaken die in tien schrijfwijzen zijn ingevoerd,
rekent een Pareto-analyse uit, maakt de grafiek en schrijft een rapport in
`cases/techniek/stilstandsanalyse/`. Wissel daarna het voorbeeldbestand om voor je eigen
export en draai hem opnieuw.

**Onderwijs.** In `data/onderwijs/` staan leerlinggegevens en een rubric om mee te oefenen.

### Stap 7: Koppel externe tools (optioneel)

Wil je dat Claude je e-mail kan lezen of je Notion kan doorzoeken? Zie
[`.claude/README.md`](.claude/README.md) voor het koppelen van MCP-servers.

> **Let op:** dit is optioneel. Claude Code werkt prima zonder externe tools.

## Mappenstructuur

```
claude-code-starter/
├── CLAUDE.md              ← Jouw kennisbank (pas deze aan!)
├── README.md              ← Dit bestand
├── .gitignore
│
├── .claude/               ← Alles wat Claude Code automatisch inleest
│   ├── README.md          ← MCP koppelen
│   ├── settings.json      ← Projectinstellingen en hooks
│   ├── skills/            ← Herbruikbare instructies
│   │   ├── hello-world/SKILL.md        ← Werkend voorbeeld
│   │   └── stilstandsrapport/SKILL.md  ← Data-analyse met grafiek en rapport
│   ├── commands/          ← Eigen slash commands
│   │   └── README.md
│   └── hooks/             ← Scripts voor pre/post automatisering
│       └── README.md
│
├── cases/                 ← Jouw werkbestanden
│   ├── feedbackronde/     ← Uitgewerkte oefencase: AI-feedback op een map met antwoorden
│   ├── meldingsflow/      ← Uitgewerkte oefencase: van melding tot ticket
│   ├── techniek/
│   │   ├── README.md
│   │   └── stilstandsanalyse/  ← Resultaten van de stilstandsrapport-skill
│   └── onderwijs/
│       └── README.md
│
└── data/                  ← Voorbeelddata per spoor
    ├── README.md
    ├── techniek/
    │   └── voorbeeld-stilstand.csv   ← ~1350 stilstandsmeldingen
    └── onderwijs/
        ├── voorbeeld-leerlingen.csv
        └── voorbeeld-rubric.md
```

**Waarom staan `cases/meldingsflow/` en `cases/feedbackronde/` niet onder techniek of
onderwijs?** Het zijn geen lege werkmappen maar uitgewerkte oefencases, met eigen skill,
instellingen en testbestanden. De feedbackronde hoort bij de minicursus AI-feedback
automatiseren. De meldingsflow is voor beide sporen geschreven (de README vertaalt melding →
ingeleverd werk en behandelaar → docent), dus hij past in geen van de twee. Je start Claude
Code **in die map**, niet in de hoofdmap.

**Waarom staat alles onder `.claude/`?** Claude Code leest skills, commands en instellingen
alleen daar. Een map `skills/` in de hoofdmap wordt niet gevonden.

## Skills gebruiken

Een skill is een gestructureerde instructie die Claude stap-voor-stap volgt. De mapnaam
wordt het commando dat je typt.

```
Jij:    /hello-world
Claude: leest .claude/skills/hello-world/SKILL.md en voert de stappen uit
```

Claude kan een skill ook zelf oppakken als hij past bij wat je vraagt. Daarvoor leest hij
de `description` uit de frontmatter.

### Zelf een skill maken

Maak een map onder `.claude/skills/` met een `SKILL.md` erin. De frontmatter bovenaan is
verplicht, zonder die regels wordt het bestand niet als skill herkend.

```markdown
---
name: mijn-skill
description: Wat de skill doet en wanneer je hem gebruikt. Claude leest dit om te bepalen wanneer hij de skill oppakt.
---

# Skill: Mijn skill

## Doel
...

## Stappen
1. Eerste stap
2. Tweede stap
```

Claude Code merkt nieuwe skills op tijdens je sessie. Heb je de map `.claude/skills/` net
aangemaakt terwijl Claude al draaide? Start hem dan één keer opnieuw.

## Meer leren?

| Resource | Link |
|----------|------|
| Claude Code documentatie | [code.claude.com/docs](https://code.claude.com/docs) |
| Skills | [code.claude.com/docs/en/skills](https://code.claude.com/docs/en/skills) |
| MCP koppelen | [code.claude.com/docs/en/mcp](https://code.claude.com/docs/en/mcp) |
| Teacher4AI trainingen | [teacher4ai.net](https://teacher4ai.net) |

### Over Teacher4AI

Teacher4AI verzorgt praktijkgerichte AI-trainingen voor het technisch onderwijs en het MKB.
Van basiskennis tot geavanceerd werken met Claude Code, altijd hands-on en toepasbaar.

📍 Rotterdam | 🌐 [teacher4ai.net](https://teacher4ai.net) | 📧 info@teacher4ai.eu

---

*Deze repo is open source en vrij te gebruiken. Gemaakt met ❤️ door Teacher4AI.*

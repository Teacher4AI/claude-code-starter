# Mijn AI Workspace — CLAUDE.md

> Dit bestand is de "kennisbank" die Claude Code leest bij elke opdracht.
> Pas het aan naar jouw situatie: jouw naam, jouw tools, jouw projecten.

---

## Over jou

| Instelling | Waarde |
|------------|--------|
| **Naam** | [Jouw naam] |
| **Organisatie** | [Jouw organisatie] |
| **Rol** | [Jouw rol, bijv. "Docent techniek" of "Projectleider"] |
| **Taal** | Nederlands (tenzij anders aangegeven) |
| **Tijdzone** | Europe/Amsterdam |

---

## Wat doet dit bestand?

Claude Code leest `CLAUDE.md` automatisch bij elke sessie. Hierin beschrijf je:

1. **Wie je bent** — zodat Claude de juiste toon en context gebruikt
2. **Welke tools je hebt** — MCP servers (Gmail, Notion, etc.)
3. **Hoe je werkt** — regels, voorkeuren, workflow
4. **Waar je bestanden staan** — mappenstructuur

> **Tip:** Hoe specifieker je dit invult, hoe beter Claude je helpt.
> Begin simpel en bouw het uit naarmate je meer ontdekt.

---

## Mijn tools (MCP servers)

Hieronder beschrijf je welke MCP servers je hebt gekoppeld. Claude weet dan wanneer welke tool te gebruiken.

| Tool | Waarvoor | Status |
|------|----------|--------|
| Gmail | Email lezen en opstellen | `[ ]` Nog koppelen / `[x]` Actief |
| Notion | Notities en databases | `[ ]` Nog koppelen / `[x]` Actief |
| *Voeg toe* | *Beschrijving* | |

> Zie `.claude/` map voor MCP configuratie voorbeelden.

---

## Mappenstructuur

```
mijn-project/
├── CLAUDE.md          ← Dit bestand (jouw kennisbank)
├── .claude/           ← Claude Code configuratie + MCP setup
├── skills/            ← Herbruikbare instructies voor Claude
├── commands/          ← Custom slash commands
├── hooks/             ← Automatische acties (pre/post)
├── cases/             ← Werkbestanden per project of case
│   ├── techniek/      ← Cases voor technisch werk
│   └── onderwijs/     ← Cases voor onderwijswerk
└── data/              ← Voorbeelddata en templates
```

---

## Skills

Skills zijn gestructureerde instructies die Claude kan volgen. Denk aan een recept: stap-voor-stap, altijd hetzelfde resultaat.

```
skills/
├── hello-world/       ← Voorbeeld-skill (bekijk deze eerst!)
│   └── SKILL.md
└── jouw-skill/        ← Maak je eigen skills
    └── SKILL.md
```

### Een skill maken

Maak een map in `skills/` met een `SKILL.md` bestand:

```markdown
# Skill: [Naam]

## Doel
Wat doet deze skill?

## Wanneer gebruiken
Bij welke vraag of opdracht?

## Stappen
1. Eerste stap
2. Tweede stap
3. ...

## Output
Wat lever je op?
```

---

## Mijn regels

Voeg hier je persoonlijke voorkeuren toe:

- Schrijf altijd in het Nederlands
- Gebruik `€` voor bedragen, niet `$`
- Bestandsnamen: kleine-letters-met-streepjes.extensie
- *[Voeg je eigen regels toe]*

---

## Projecten

Beschrijf hier je lopende projecten zodat Claude context heeft:

### Project: [Naam]
- **Doel:** ...
- **Status:** ...
- **Bestanden:** `cases/techniek/` of `cases/onderwijs/`

---

> **Volgende stap:** Koppel je eerste MCP server!
> Zie `.claude/README.md` voor instructies.

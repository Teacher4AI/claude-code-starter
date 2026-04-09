# Skill: Hello World

## Doel

Dit is een voorbeeld-skill om te laten zien hoe skills werken. Claude volgt deze stappen wanneer je vraagt: "Gebruik de hello-world skill."

## Wanneer gebruiken

- Als eerste kennismaking met skills
- Om te testen of Claude je `skills/` map leest
- Als template voor je eigen skills

## Stappen

### Stap 1: Begroeting

Begroet de gebruiker met:
- Naam (uit CLAUDE.md, als ingevuld)
- Huidige datum en tijd
- Een korte samenvatting van de workspace

### Stap 2: Workspace check

Controleer de mappenstructuur:
1. Bestaat `CLAUDE.md`? → Lees en toon de naam en rol
2. Hoeveel skills staan er in `skills/`?
3. Zijn er bestanden in `cases/`?
4. Welke MCP servers zijn geconfigureerd?

### Stap 3: Quick demo

Demonstreer een kleine taak:
1. Maak een bestand `cases/hello.md` aan met de tekst:
   ```markdown
   # Mijn eerste Claude Code bestand

   Aangemaakt op: [datum]
   Door skill: hello-world

   Dit bestand is automatisch aangemaakt door de hello-world skill.
   Je kunt het veilig verwijderen.
   ```
2. Toon het resultaat aan de gebruiker

### Stap 4: Volgende stappen

Geef de gebruiker tips:
- "Pas `CLAUDE.md` aan met jouw gegevens"
- "Koppel een MCP server (zie `.claude/README.md`)"
- "Maak je eigen skill in `skills/jouw-skill/SKILL.md`"

## Output

- Begroeting met workspace-overzicht
- Bestand `cases/hello.md` aangemaakt
- Tips voor volgende stappen

## Voorbeeld interactie

```
Gebruiker: "Gebruik de hello-world skill"

Claude: "👋 Hallo [naam]! Het is [datum].

📁 Je workspace:
- CLAUDE.md: ✅ gevonden
- Skills: 1 (hello-world)
- Cases: leeg (nog geen projecten)
- MCP servers: nog niet geconfigureerd

Ik heb cases/hello.md aangemaakt als demo.

💡 Volgende stappen:
1. Vul CLAUDE.md aan met je gegevens
2. Koppel Gmail of Notion (zie .claude/README.md)
3. Maak je eerste eigen skill!"
```

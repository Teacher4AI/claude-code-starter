# .claude/hooks/ — Pre- en post-hooks

Hooks zijn scripts die automatisch draaien voor of na een actie van Claude. Handig om een
controle af te dwingen die je niet elke keer wilt herhalen.

## Hoe je een hook aanzet

De scripts staan in deze map, de configuratie staat in `.claude/settings.json`:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Write",
        "hooks": [
          {
            "type": "command",
            "command": "${CLAUDE_PROJECT_DIR}/.claude/hooks/pre-write-check.sh"
          }
        ]
      }
    ]
  }
}
```

Let op drie dingen die vaak misgaan:

- De naam van de gebeurtenis schrijf je met hoofdletters: `PreToolUse`, niet `preToolUse`
- Het commando staat in een geneste `hooks`-array, niet direct naast `matcher`
- `"type": "command"` is verplicht

`${CLAUDE_PROJECT_DIR}` verwijst naar de hoofdmap van je project, zodat de hook ook werkt
als je Claude Code vanuit een submap start.

## Waar je hooks voor gebruikt

| Gebeurtenis | Wanneer | Voorbeeld |
|---|---|---|
| `PreToolUse` | Vlak voor een actie | Blokkeer schrijven buiten je projectmap |
| `PostToolUse` | Vlak na een actie | Draai automatisch een linter of formatter |
| `SessionStart` | Bij het starten | Toon welke taken openstaan |

## Zelf een hook maken

1. Maak een script in deze map, bijvoorbeeld `pre-write-check.sh`
2. Maak het uitvoerbaar: `chmod +x .claude/hooks/pre-write-check.sh`
3. Zet het in `.claude/settings.json` volgens het schema hierboven
4. Test het, een hook die stilletjes faalt merk je anders pas veel later

De hook krijgt informatie binnen via stdin als JSON en kan met een exit-code aangeven of
de actie door mag gaan.

## Meer informatie

Alle gebeurtenissen, velden en exit-codes staan in de
[documentatie over hooks](https://code.claude.com/docs/en/hooks).

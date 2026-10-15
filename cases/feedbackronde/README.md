# cases/feedbackronde: AI-feedback op een map met antwoorden

Dit is de oefencase bij de minicursus **AI-feedback automatiseren** op de Teacher4AI Academy.
Een agent in deze map beoordeelt een map met studentantwoorden op één open opdracht, met jouw
rubric en jouw lesstof, en schrijft per antwoord feedback weg. Jij kijkt daarna een steekproef
na. Alles werkt met bestanden: er is geen leeromgeving en geen mailbox voor nodig.

## Zo start je

Deze case is een eigen projectmap: start Claude Code **in deze map**, niet in de hoofdmap van
de starterskit.

```bash
cd claude-code-starter/cases/feedbackronde
claude
```

De eerste keer vraagt Claude Code of je de bestanden in deze map vertrouwt. Antwoord ja: pas
dan gelden de regels in `.claude/settings.json` volledig. Typ daarna:

```
/feedbackronde
```

De skill leest de opdracht, de rubric en de lesstof, beoordeelt de zes antwoorden, vraagt
toestemming om in `feedback/` te schrijven en toont een overzicht met een steekproef.

> Heb je de starterskit al eerder binnengehaald? Haal dan eerst de nieuwste versie op:
> `git pull` in de map `claude-code-starter`, of download de ZIP opnieuw.

## Wat er in de map staat

| Bestand of map | Wat het is |
|---|---|
| `opdracht.md` | De open vraag en het leerdoel (de feed up) |
| `rubric.md` | Drie criteria met elementen, weging en veelgemaakte fouten |
| `lesstof/` | Drie chunks uit één hoofdstuk, elk met leerdoel, praktijkvoorbeeld en misvatting |
| `antwoorden/` | Zes voorbeeldantwoorden: een sterk antwoord, een algemeen antwoord, een te kort antwoord, een antwoord dat de lesstof herhaalt, een antwoord met een verstopte instructie aan de beoordelaar, en een antwoord met een gat in de registratie |
| `feedback/` | Leeg bij aanvang; de skill schrijft hier per antwoord een bestand en één `overzicht.md` |
| `.claude/skills/feedbackronde/SKILL.md` | De skill: de vaste stappen van inlezen tot steekproef |
| `.claude/settings.json` | De permissies: lezen mag, schrijven in `feedback/` komt eerst bij jou langs, antwoorden en lesstof wijzigen en het internet op kan niet |

## Met je eigen materiaal

Vervang de inhoud van `opdracht.md`, `rubric.md`, `lesstof/` en `antwoorden/` door je eigen
vak. Houd de vorm aan: een chunk met leerdoel en misvatting, een rubric met elementen die je
in een antwoord kunt aanwijzen. Gebruik alleen geanonimiseerde antwoorden (student-01,
student-02, ...): namen en studentnummers horen niet in deze map.

## Wat de skill niet doet

Geen cijfers, geen eindoordeel en niets versturen. De docent kijkt de steekproef na en
beslist. Wijkt het oordeel van de skill af van het jouwe, pas dan de rubric of de chunks aan
en draai de ronde opnieuw: dat is precies waar de verbetering zit.

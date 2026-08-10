# Stilstandsanalyse

Werkmap voor de stilstandsrapport-skill. Hier komen de resultaten te staan.

## Wat hier verschijnt

| Bestand | Wanneer |
|---------|---------|
| `oorzaakgroepen.md` | Na de eerste run. Hoe de vrije-tekstoorzaken zijn gegroepeerd |
| `pareto-[periode].png` | De grafiek |
| `rapport-[periode].md` | Het rapport met tabel, grafiek en verantwoording |

De map is bij het clonen leeg. Dat hoort zo, je vult hem met je eigen runs.

## Starten

```
/stilstandsrapport
```

Claude pakt dan `data/techniek/voorbeeld-stilstand.csv`. Wil je je eigen export gebruiken,
zet die dan in `data/techniek/` en noem het bestand in je opdracht.

## Daarna

Pas `.claude/skills/stilstandsrapport/SKILL.md` aan naar wat jouw organisatie wil zien. Andere
maten, andere indeling, een extra uitsplitsing. De skill is van jou zodra je hem verandert.

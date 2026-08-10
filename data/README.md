# data/ — Voorbeelddata

Voorbeeldbestanden om mee te experimenteren, gesplitst per spoor. Net als `cases/`.

| Map | Voor wie | Inhoud |
|-----|----------|--------|
| [`techniek/`](techniek/) | Technici, engineers, werkvoorbereiders | Stilstandsregistratie van een productielijn (~1350 regels) |
| [`onderwijs/`](onderwijs/) | Docenten, opleiders | Leerlinggegevens en een beoordelingsrubric |

Elke map heeft een eigen README met de kolommen en de bedoeling.

## Eigen data toevoegen

Plaats hier je eigen datasets. Let op:

- **Geen persoonsgegevens** van echte leerlingen of medewerkers
- **Geen vertrouwelijke bedrijfsdata**
- Gebruik fictieve of geanonimiseerde data
- Voeg bestanden toe aan `.gitignore` als ze niet op GitHub mogen

## Tips voor Claude

Je kunt Claude vragen:

- "Analyseer `data/techniek/voorbeeld-stilstand.csv` en vertel me wat opvalt"
- "Gebruik de weekrapport-stilstand skill"
- "Genereer vergelijkbare testdata voor mijn eigen lijn"

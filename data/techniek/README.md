# data/techniek/ — Voorbeelddata techniek

## `voorbeeld-stilstand.csv`

Een stilstandsregistratie van een fictief productiebedrijf: drie lijnen, twaalf machines,
drie ploegen, een vol jaar aan meldingen. Ongeveer 1350 regels.

Dit is het soort bestand dat je zelf uit een MES, een onderhoudspakket of een gedeelde
Excel haalt. Rommelig, want zo komt het in het echt ook binnen.

| Kolom | Inhoud |
|-------|--------|
| `datum` | Datum van de melding (JJJJ-MM-DD) |
| `tijd` | Starttijd van de stilstand |
| `lijn` | L1 Assemblage, L2 Verpakking of L3 Extrusie |
| `machine` | De machine die stilstond |
| `oorzaak` | **Vrije tekst**, ingevuld door de ploeg. Schrijfwijzen lopen door elkaar |
| `duur_min` | Duur in minuten |
| `ploeg` | A (06-14), B (14-22), C (22-06) |
| `monteur` | Code van de technische dienst, soms leeg |
| `opmerking` | Vrije notitie, vaak leeg |

### Wat er expres niet klopt

De data is met opzet niet schoongepoetst. Je komt tegen:

- **Dezelfde oorzaak in meerdere schrijfwijzen.** "sensor storing", "Sensor storing",
  "sensorstoring" en "sensor defect" zijn hetzelfde probleem. Je moet ze eerst groeperen,
  anders klopt je analyse niet.
- **Lege velden.** Een handvol regels heeft geen duur, een paar hebben geen oorzaak.
  Weglaten of meenemen is jouw keuze, maar maak hem bewust en schrijf op wat je koos.
- **Een paar registraties van 0 minuten.** Invoerfouten. Die bestaan.

### De vraag onder de data

Er zit een verschil tussen de storing die je het **vaakst** ziet en de storing die je de
**meeste tijd** kost. Dat verschil is precies waarom je deze analyse doet: waar je aandacht
naartoe gaat is niet vanzelf waar de winst zit.

> Alle namen, machines en cijfers zijn verzonnen. Er zit geen echte bedrijfsdata in.

## Je eigen data gebruiken

Zet je eigen export in deze map en verwijs ernaar in je opdracht. Let op:

- Geen persoonsgegevens van medewerkers
- Geen vertrouwelijke bedrijfsdata in een publieke repo
- Twijfel je? Zet het bestand in `.gitignore`

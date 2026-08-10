# Skill: Stilstandsrapport

## Doel

Van een ruwe stilstandsregistratie naar een rapport met een Pareto-analyse en een grafiek.
Eén opdracht, elke keer hetzelfde resultaat.

Dit is het verschil tussen een chatvenster en een agent: Claude leest het bestand zelf,
schrijft de analyse, **draait die ook echt**, en zet het resultaat op je schijf.

## Wanneer gebruiken

- Je hebt een export met stilstanden, storingen of meldingen
- Je wilt weten waar je verloren tijd echt zit
- Je wilt dat rapport periodiek herhalen zonder het opnieuw uit te leggen

## Wat je nodig hebt

Een CSV met minimaal een datum, een oorzaak en een duur. De kolommen mogen anders heten
dan hieronder. Zonder opgegeven bestand gebruik je `data/techniek/voorbeeld-stilstand.csv`.

## Stappen

### Stap 1: Lees en verken

Lees het bestand. Rapporteer eerst kort terug, voordat je gaat rekenen:

- Hoeveel regels, welke periode
- Welke kolommen, welke lijnen of machines
- Hoeveel lege of onmogelijke waarden (lege duur, duur 0, lege oorzaak)

### Stap 2: Groepeer de oorzaken

De kolom `oorzaak` is vrije tekst. Dezelfde storing staat er in meerdere schrijfwijzen in
("sensor storing", "Sensor storing", "sensorstoring", "sensor defect").

Groepeer die tot logische categorieën. **Toon de groepering aan de gebruiker voordat je
verdergaat** en vraag of het klopt. Jij kent de data, de gebruiker kent de fabriek.

Leg je keuzes vast in `cases/techniek/stilstandsanalyse/oorzaakgroepen.md`, zodat de
volgende keer dezelfde indeling gebruikt wordt.

### Stap 3: Beslis over de rommel

Lege duur, duur 0, lege oorzaak: laat zien hoeveel het er zijn en stel voor wat je ermee
doet. Neem de keuze op in het rapport, zodat de lezer weet waar de cijfers op rusten.

Verzin nooit een waarde om een gat te vullen.

### Stap 4: Reken

Bereken per oorzaakgroep:

| Maat | Waarom |
|------|--------|
| Aantal meldingen | Hoe vaak zit je ermee |
| Totale duur in minuten en uren | Wat het je echt kost |
| Gemiddelde duur | Kort en vaak, of zeldzaam en lang |
| Aandeel in de totale stilstand (%) | Hoe zwaar het weegt |
| Cumulatief aandeel (%) | Waar de 80-procentgrens ligt |

Sorteer op totale duur, niet op aantal. Splits daarnaast uit per lijn en per ploeg.

### Stap 5: Maak de grafiek

Maak een Pareto-diagram: staven met de minuten per oorzaakgroep (aflopend) en een lijn met
het cumulatieve percentage over de tweede as. Schrijf het weg als PNG in
`cases/techniek/stilstandsanalyse/`.

Kies zelf het gereedschap dat op deze machine werkt. Python met matplotlib is de meest
voor de hand liggende route. Ontbreekt de bibliotheek, vraag dan of je hem mag installeren.
Bedenk geen ASCII-vervanging, de gebruiker vroeg om een grafiek.

Controleer daarna dat het bestand er echt staat en dat het te openen is.

### Stap 6: Schrijf het rapport

Schrijf `cases/techniek/stilstandsanalyse/rapport-[periode].md` met:

1. **Kop** — periode, aantal meldingen, totale stilstand in uren
2. **De kern in drie zinnen** — waar de tijd blijft, wat opvalt, wat je zou aanpakken
3. **De grafiek** — ingesloten met een relatief pad
4. **Tabel** — alle oorzaakgroepen met de maten uit stap 4
5. **Per lijn en per ploeg** — waar de verschillen zitten
6. **Verantwoording** — hoe je hebt gegroepeerd en wat je met de lege velden deed

Schrijf zakelijk en kort. Dit rapport gaat naar iemand die het in twee minuten leest.

### Stap 7: Kijk verder dan de grootste staaf

Sluit af met wat je opvalt en niet met een samenvatting van de tabel. Kijk in elk geval naar:

- Verschilt de volgorde op **aantal** van de volgorde op **minuten**? Wat betekent dat?
- Zit er een ploeg of een lijn die eruit springt?
- Is er een oorzaak die door het jaar heen toeneemt?

Trek geen conclusies die de data niet draagt. Noem het een signaal, niet een oorzaak.

## Zo roep je hem aan

```
Gebruik de stilstandsrapport skill
Gebruik de stilstandsrapport skill op mijn eigen export in data/techniek/
Gebruik de stilstandsrapport skill, alleen kwartaal 2
```

## Deze skill aanpassen

Dit is een tekstbestand. Verander de stappen, de maten of de opbouw van het rapport en de
volgende run volgt jouw versie. Dat is het hele idee van een skill.

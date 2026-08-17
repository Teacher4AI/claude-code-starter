# cases/meldingsflow: van melding tot ticket

Dit is de oefencase bij de praktijkmodule **AI-koppelingen en automatisering** (hoofdstuk 5
tot en met 7, de Claude Code-route). Een storingsmelding komt binnen, er komt een diagnose
uit, er gaat een ticket de map in en er staat een bericht voor de behandelaar klaar. Alles
werkt met bestanden: een melding is een tekstbestand in `meldingen/`, een ticket is een
markdown-bestand in `tickets/`. Je hebt er geen mailbox en geen database voor nodig. Die
twee zijn de optionele tweede stap, verderop.

Werk je in het onderwijs? Lees dan "ingeleverd werk" voor "melding", "feedback" voor
"diagnose" en "docent" voor "behandelaar". De keten is precies dezelfde. Daarom staat deze
case náást `cases/techniek/` en `cases/onderwijs/` en niet in één van de twee: hij is voor
beide sporen geschreven, met die vertaaltabel als brug.

## Zo start je

Deze case is een eigen projectmap: je start Claude Code **in deze map**, niet in de
hoofdmap van de starterskit. Alleen dan vindt Claude Code de skill, de instellingen en de
mappen `meldingen/` en `tickets/` op de plek waar de module ze noemt.

```bash
cd claude-code-starter/cases/meldingsflow
claude
```

De eerste keer vraagt Claude Code of je de bestanden in deze map vertrouwt. Antwoord ja:
zonder dat gelden de regels in `.claude/settings.json` maar half en vraagt hij alsnog
toestemming voor elk bestand dat hij in `meldingen/` leest.

Typ daarna in Claude Code:

```
/meldingsflow meldingen/melding-01.txt
```

De skill leest de melding, stelt de diagnose, vraagt toestemming om
`tickets/ticket-M-4410.md` te schrijven en toont het concept-bericht. Draai hem daarna nog
een keer op dezelfde melding: er hoort geen tweede ticket bij te komen.

> Heb je de starterskit al eerder binnengehaald? Haal dan eerst de nieuwste versie op:
> `git pull` in de map `claude-code-starter`, of download de ZIP opnieuw. Deze case is
> later toegevoegd.

## Wat er in de map staat

| Bestand of map | Wat het is |
|---|---|
| `README.md` | Dit bestand |
| `meldingen/melding-01.txt` | Normale melding met meldingsnummer M-4410 en een duidelijke urgentie-aanwijzing |
| `meldingen/melding-02.txt` | Vage melding ("het doet raar"), zonder meldingsnummer en zonder onderdeel |
| `meldingen/melding-03.txt` | Melding met een verstopte instructie erin (prompt-injectie), voor hoofdstuk 6 |
| `meldingen/melding-04.txt` | Melding met nummer M-4411, zonder enige aanwijzing over urgentie, voor de controleur in hoofdstuk 6 |
| `tickets/` | Leeg bij aanvang; de skill schrijft hier één `ticket-<nummer>.md` per melding |
| `.claude/skills/meldingsflow/SKILL.md` | Het skelet van de skill uit hoofdstuk 5, oefening 2: de vier schakels staan erin, de condities en foutafhandeling schrijf je zelf bij |
| `.claude/settings.json` | De permissieregels uit hoofdstuk 6: lezen in `meldingen/` mag zonder vragen, schrijven in `tickets/` komt eerst bij jou langs, versturen kan niet |
| `.mcp.json.example` | Voorbeeld voor de optionele koppelingen (notitie-database en mail), zonder sleutels |
| `runs.jsonl` | Ontstaat bij je eerste run: één logregel per run. Hoofdstuk 7 gebruikt hem |

Wat je zelf toevoegt in de loop van de module: `.claude/agents/meldingsagent.md` en
`.claude/agents/ticketcontroleur.md` (hoofdstuk 6).

## Wat elk hoofdstuk hier doet

- **Hoofdstuk 5**: je vult het skelet in `.claude/skills/meldingsflow/SKILL.md` aan met
  condities en foutafhandeling en draait hem op de vier meldingen.
- **Hoofdstuk 6**: je maakt een agent met een smalle gereedschapskist, gebruikt de regels in
  `.claude/settings.json`, valt hem aan met `melding-03.txt` en laat een tweede agent het
  ticket van `melding-04.txt` beoordelen.
- **Hoofdstuk 7**: je laat de skill een logregel schrijven naar `runs.jsonl` en start hem
  buiten de sessie met `claude -p "/meldingsflow meldingen/melding-01.txt"`.

## Optionele tweede stap: de koppelingen

Wil je de keten met echte systemen draaien, dan voeg je twee koppelingen toe. Doe dit in
deze map, dan komen ze in `.mcp.json` hier terecht en reizen ze mee met de case.

**De notitie-database (Notion), voor tickets als record naast het bestand:**

```bash
claude mcp add -s project --transport http tickets https://mcp.notion.com/mcp
```

Start daarna een sessie en log in met `/mcp`; er staat geen sleutel in het bestand.

**De mailkoppeling (Gmail), om de melding uit je mailbox te halen:**

```bash
claude mcp add -s project mail -- npx -y @gongrzhe/server-gmail-autoauth-mcp
```

Deze koppeling werkt met inloggen bij Google (OAuth) en een configuratiebestand buiten deze
map. De installatiestappen staan in de handleiding van het pakket zelf; volg die en verzin
ze niet zelf. Zit je op Microsoft 365, sla de mailkoppeling dan over: de meldingen staan als
bestand klaar en de keten werkt volledig zonder.

Controleer daarna met `claude mcp list` of beide koppelingen antwoorden, en kijk met `/mcp`
in je sessie hoe de handelingen precies heten. De naam van de verstuur-handeling zet je in
`.claude/settings.json` bij `deny`. Bij de Gmail-koppeling hierboven heet hij
`mcp__mail__send_email` (dat staat er al); gebruik je een andere koppeling, kijk dan met
`/mcp` hoe hij daar heet.

## Let op

- De testmeldingen zijn verzonnen en bevatten geen persoonsgegevens. Vervang je ze door
  echte meldingen, zet deze map dan niet in een gedeelde repository zonder de meldingen en
  tickets eruit te halen.
- Er staat nooit een sleutel in `.mcp.json` of in deze map. Beide koppelingen loggen in via
  de browser.

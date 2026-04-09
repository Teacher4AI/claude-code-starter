# .claude/ — Configuratie

Deze map bevat configuratiebestanden voor Claude Code.

## MCP Servers koppelen

MCP (Model Context Protocol) servers geven Claude toegang tot externe tools zoals Gmail en Notion.

### Stap 1: Settings openen

In Claude Code, type:
```
/settings
```

Of bewerk het bestand `~/.claude/settings.json` handmatig.

### Stap 2: MCP server toevoegen

Kopieer de voorbeeldconfiguratie uit `mcp-config-example.json` en pas de waarden aan.

### Gmail koppelen

1. Ga naar [Google Cloud Console](https://console.cloud.google.com/)
2. Maak een project aan en activeer de Gmail API
3. Maak OAuth2 credentials aan (type: Desktop App)
4. Download het `credentials.json` bestand
5. Installeer de Gmail MCP server:
   ```bash
   npx @anthropic/create-mcp -t gmail
   ```
6. Volg de instructies om te authenticeren

### Notion koppelen

1. Ga naar [Notion Integrations](https://www.notion.so/my-integrations)
2. Maak een nieuwe integratie aan
3. Kopieer de API token
4. Deel de gewenste pagina's/databases met je integratie
5. Voeg de token toe aan je MCP configuratie

> **Let op:** Bewaar API keys NOOIT in een Git repository!
> Gebruik environment variables of een `.env` bestand (staat in `.gitignore`).

## Bestanden in deze map

| Bestand | Doel |
|---------|------|
| `README.md` | Deze uitleg |
| `mcp-config-example.json` | Voorbeeld MCP configuratie (zonder echte keys) |
| `settings.json` | Claude Code project-instellingen (optioneel) |

# news

Neuigkeiten für den [Mett Launcher](https://github.com/Mett-Gaming/mett-launcher). Der Launcher liest `news.json` von
`https://raw.githubusercontent.com/Mett-Gaming/news/main/` und zeigt die Einträge auf der Seite **NEUIGKEITEN** sowie –
wenn `game` gesetzt ist – in der Aktivitätsspalte des Spiels. Offline zeigt er den letzten Stand.

## Neue Meldung

Eintrag oben in `items` ergänzen und pushen. Reihenfolge ist egal, der Launcher sortiert nach Datum.

```json
{
  "id": "kasse0-v0.20.0",
  "date": "2026-11-23T18:00:00+01:00",
  "title": "KASSE 0 v0.20.0: …",
  "game": "kasse0",
  "kind": "patchnotes",
  "excerpt": "Ein Satz für die Übersicht.",
  "body": "- Punkt 1\n- Punkt 2",
  "image": "images/kasse0-v0.20.0.png",
  "url": "https://github.com/Mett-Gaming/kasse0/releases/tag/v0.20.0"
}
```

| Feld | Pflicht | Bedeutung |
|---|---|---|
| `id` | ja | Eindeutig. Für Patchnotes `<spiel-id>-<tag>` – dann ersetzt die Meldung im Launcher den rohen Release-Eintrag. |
| `date` | ja | ISO-8601 mit Zeitzone. |
| `title` | ja | Überschrift. |
| `game` | nein | Spiel-ID aus dem [Katalog](https://github.com/Mett-Gaming/launcher-catalog); leer = allgemeine Meldung. |
| `kind` | nein | `patchnotes`, `news` oder `event` (Standard `news`). |
| `excerpt` | nein | Kurztext für die Übersicht. |
| `body` | nein | Langtext als einfaches Markdown (Aufzählungen). |
| `image` | nein | Bild relativ zu diesem Repo (`images/…`) oder `https://`-URL. |
| `url` | nein | Link für „Mehr auf GitHub“. |

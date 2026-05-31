# bamobus 🚏

Eine kleine Web-App, die deine Bus-/Bahn-Haltestellen **live** verfolgt und – wie eine
Abfahrtstafel an der Straße – die **nächsten 5 Verbindungen** mit Countdown in Minuten
und Echtzeit-Verspätungen anzeigt. Fokus: **Baden-Württemberg** (funktioniert aber deutschlandweit).

## Features

- 🔎 **Suche** nach Haltestelle **oder Adresse** mit Vorschlägen beim Tippen
- 📍 **In der Nähe** – findet per GPS die nächsten Haltestellen
- 🏠 **Adresse → nächste Haltestelle** – Adresse eingeben, nächstgelegene Stationen wählen
- 💾 **Speichern** mehrerer Haltestellen (lokal im Browser, keine Anmeldung)
- 🚆 **Abfahrtstafel** mit Linienfarben, Ziel, Gleis/Steig
- ⏱️ **Countdown in Minuten** + Uhrzeit, sekundengenau live
- 🔴 **Echtzeit-Verspätungen** (`+X min` / „pünktlich" / „Fällt aus")
- 🔄 **Auto-Refresh** alle 30 s

## Nutzung

Es ist eine einzige statische Datei – kein Server, kein API-Key nötig.

1. `index.html` im Browser öffnen (Doppelklick) **oder** lokal hosten:
   ```bash
   python -m http.server 8000
   # dann http://localhost:8000 öffnen
   ```
2. Haltestelle/Adresse suchen oder **📍 Nähe** tippen, Station speichern – fertig.

> Hinweis: Der GPS-Button benötigt `https://` oder `localhost` (Browser-Vorgabe für Standortzugriff).

## Daten

Öffentliche, kostenlose Routing-API **[Transitous](https://transitous.org)** (MOTIS),
gespeist aus den offiziellen DELFI-/bwegt-Fahrplandaten inkl. Echtzeit.

## Deployment (GitHub Pages)

Repo → **Settings → Pages → Branch: `main` / root**. Danach läuft die App unter
`https://8bamo.github.io/bamobus/` – inklusive GPS, weil HTTPS.

---

Erstellt mit [Claude Code](https://claude.com/claude-code).

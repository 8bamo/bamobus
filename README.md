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
- ★ **Linien-Favoriten** + Umschalter „Nur Favoriten"
- 🔀 **Filter** nach Bus / S-Bahn / U-Bahn / Regio
- 📺 **Paginator**: bei mehr als 5 Abfahrten blättert die Tafel alle 5 s automatisch weiter
- ⛶ **Vollbild-/Kiosk-Modus** für Tablet & Monitor (mit Display-Wachhaltung per Wake-Lock)
- 🔄 **Auto-Refresh** alle 30 s · Start-Haltestelle: **Stuttgart Hauptbahnhof**

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

## Deployment

### Vercel (empfohlen)

Das Repo enthält `vercel.json` (statische Auslieferung, Security-Header, `geolocation`
erlaubt). Zwei Wege:

**A) Dashboard (am einfachsten)**
1. [vercel.com/new](https://vercel.com/new) → GitHub-Repo `8bamo/bamobus` importieren
2. Framework: **Other**, Build Command leer, Output Directory leer (Root)
3. **Deploy** → läuft unter `https://bamobus.vercel.app` (o. ä.), HTTPS inklusive → GPS funktioniert

**B) CLI**
```bash
npm i -g vercel
vercel          # Preview-Deploy
vercel --prod   # Produktiv-Deploy
```

### GitHub Pages (Alternative)

Repo → **Settings → Pages → Branch `main` / root**. Läuft dann unter
`https://8bamo.github.io/bamobus/` – ebenfalls mit HTTPS und GPS.

---

Erstellt mit [Claude Code](https://claude.com/claude-code).

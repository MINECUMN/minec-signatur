# MINEC E-Mail-Signatur

Universelle HTML-E-Mail-Signatur für **Michael Netzig / MINEC UG** mit eingebetteten Social-Media-Icons und Firmenlogo.

## Enthaltene Dateien

| Datei | Zweck |
|---|---|
| `signatur_gmail_kopieren.html` | **Zum Einrichten** — weißer Hintergrund, direkt aus Chrome kopieren |
| `signatur_universal.html` | Vorschau auf MINEC-Cream-Hintergrund |
| `signatur.html` | Originalversion mit SVG-Icons (nur moderne Clients) |

## Signatur einrichten

### Gmail (Google Workspace)
1. `signatur_gmail_kopieren.html` in **Chrome** öffnen
2. `Cmd+A` → `Cmd+C`
3. Gmail → Einstellungen → Signaturen → Neu → Einfügen (`Cmd+V`)
4. Als Standard festlegen → Speichern

### Apple Mail
Mail → Einstellungen → Signaturen → `+` → HTML-Ansicht (`Cmd+Shift+H`) → Inhalt einfügen

### Outlook (Mac/Web)
Datei → Optionen → E-Mail → Signaturen → Neu → HTML einfügen

## Enthaltene Social-Media-Links

| Icon | Ziel |
|---|---|
| WhatsApp | `https://wa.me/4953746740089` |
| LinkedIn | `https://www.linkedin.com/in/netzig/` |
| Facebook | `https://www.facebook.com/MINEC.tech.` |
| Instagram | `https://www.instagram.com/minec_ug/` |
| Newsletter | n8n-Webhook (Anmeldeformular) |

## Technische Details

- Icons: Base64-kodierte PNG (60×60 px, dargestellt als 30×30 px, 2× Retina)
- Logo: Transparent, passt sich dem E-Mail-Hintergrund an
- Layout: `<table>`-basiert für maximale E-Mail-Client-Kompatibilität
- Kein externer Bildhost erforderlich — alles inline eingebettet

## Anpassen

URLs oder Kontaktdaten ändern: In `signatur_gmail_kopieren.html` und `signatur_universal.html` die entsprechenden `href`-Attribute und Textstellen bearbeiten, danach neu in den E-Mail-Client einpflegen.

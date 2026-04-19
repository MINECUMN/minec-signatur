# Technische Dokumentation — MINEC E-Mail-Signatur

## Übersicht

Die E-Mail-Signatur ist als selbst-enthaltene HTML-Datei aufgebaut. Alle Bilder (Logo und Social-Media-Icons) sind als Base64-kodierte PNG-Daten direkt in den HTML-Code eingebettet — kein externer Server oder CDN wird benötigt.

---

## Dateistruktur

```
Signatur/
├── README.md                      # Kurzanleitung
├── DOKUMENTATION.md               # Diese Datei
├── dokumentation.html             # Visuelle Dokumentation (MINEC Design)
├── signatur_gmail_kopieren.html   # Kopiervorlage (weißer Hintergrund)
├── signatur_universal.html        # Vorschau (Cream-Hintergrund)
└── signatur.html                  # Originalversion mit SVG-Icons
```

---

## Aufbau der Signatur

### HTML-Struktur

Die Signatur ist vollständig `<table>`-basiert, da E-Mail-Clients wie Outlook kein CSS-Flexbox oder Grid unterstützen. Alle Styles sind als Inline-Styles direkt am Element definiert.

```
<table>                          ← Äußere Tabelle (max-width: 420px)
  <tr> Grußformel </tr>
  <tr> Name + Logo </tr>
  <tr> Adresse & Kontakt </tr>
  <tr> Trennlinie </tr>
  <tr>
    <table>                      ← Innere Tabelle für Icons
      <tr>
        <td> WhatsApp-Icon </td>
        <td> LinkedIn-Icon </td>
        <td> Facebook-Icon </td>
        <td> Instagram-Icon </td>
        <td> Newsletter-Icon </td>
      </tr>
    </table>
  </tr>
</table>
```

### Typografie

| Element | Größe | Gewicht | Farbe |
|---|---|---|---|
| Grußformel | 13px | Regular | `#22262c` |
| Name | 15px | 700 (Bold) | `#193e47` |
| Adresse | 12px | Regular | `#707070` |
| Links | 12px | Regular | `#155d6b` |

### Farbpalette

| Variable | Hex | Verwendung |
|---|---|---|
| Navy | `#193e47` | Name |
| Teal | `#155d6b` | Links, Newsletter-Icon |
| Gray Dark | `#707070` | Adresstext |
| Gray Light | `#dcd9d7` | Trennlinie |

---

## Logo

### Quelle
Original-SVG: `Gründungsunterlagen/Logo/MINEC Logo.svg`
Format: Vektorgrafik, ViewBox `357.2 × 149.86`, Farbe `#0096b2`

### Konvertierung
1. SVG → PNG via macOS `qlmanage -t -s 300`
2. Weißer Hintergrund entfernt (Pixel mit R,G,B > 230 → transparent)
3. Zuschnitt auf Inhalt (Bounding Box)
4. Skalierung auf 220 × 98 px (2× für Retina)
5. Darstellung im HTML: `width="110" height="49"`
6. Einbettung als `data:image/png;base64,...`

### Transparenz
Das Logo-PNG hat einen transparenten Hintergrund und passt sich automatisch der Hintergrundfarbe des E-Mail-Clients an.

---

## Social-Media-Icons

Alle Icons sind als 60 × 60 px PNG generiert (2× Retina), dargestellt als 30 × 30 px.
Generiert mit Python/Pillow — abgerundete Quadrate (`border-radius: 6px`) mit Markenfarbe.

| Icon | Hintergrundfarbe | Stil |
|---|---|---|
| WhatsApp | `#25D366` | Chat-Blase + Linse |
| LinkedIn | `#0077B5` | „in"-Text (Helvetica Bold) |
| Facebook | `#1877F2` | „f"-Text (Helvetica) |
| Instagram | Gradient (Gelb → Pink → Lila) | Kamera-Outline + Dot |
| Newsletter | `#155d6b` (MINEC Teal) | Briefumschlag |

---

## E-Mail-Client-Kompatibilität

| Client | Kompatibel | Hinweis |
|---|---|---|
| Gmail (Web) | ✅ | Bilder werden auf Google-Server kopiert |
| Google Workspace | ✅ | |
| Apple Mail | ✅ | |
| Outlook 2016+ (Mac) | ✅ | |
| Outlook 365 (Web) | ✅ | |
| Outlook 2007/2010 (Win) | ⚠️ | SVG nicht unterstützt; PNG-Version funktioniert |
| Thunderbird | ✅ | |

---

## Signatur aktualisieren

### URL ändern (z. B. neues Instagram-Handle)
In `signatur_gmail_kopieren.html` und `signatur_universal.html` den entsprechenden `href`-Wert im `<a>`-Tag des jeweiligen Icons suchen und ersetzen. Danach Signatur im E-Mail-Client neu einrichten.

### Logo austauschen
1. Neues SVG in `qlmanage` konvertieren
2. Weißen Hintergrund entfernen (Python/Pillow)
3. Als Base64 kodieren
4. `src`-Attribut des Logo-`<img>`-Tags ersetzen

### Icon neu generieren
Das Python-Skript zur Icon-Generierung ist in der Session-History verfügbar. Icons werden mit Pillow (`pip install pillow`) generiert.

---

## Kontakt

**MINEC UG** | Michael Netzig | Gartenweg 9, 38551 Ribbesbüttel
+49 5374 6740088 | info@minec.tech | https://minec.tech

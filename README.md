# scroll-prototype

Scroll-Prototyp für den ZEIT-Abo-Rückblick — „Ihre erste Woche mit Z+“.

**→ [Prototyp öffnen](https://afriendlikeyou.github.io/scroll-prototype/)** (sobald GitHub Pages aktiviert ist)

## Aufbau

Nach Figma `550:28224`:

Einstieg → vier Datenvisualisierungen mit je einer Empfehlung → „Das war der Anfang“ → beliebte Artikel → dynamische Ausspielfläche → Abschluss.

## Zwei Varianten

Im Prüfstand umschaltbar:

- **Szenen** — jede Visualisierung nimmt eine volle Bildhöhe ein, die Animation startet beim Eintritt in die Sichtzone und läuft beim Zurückscrollen erneut
- **Karten, gestapelt** — die Visualisierungen liegen auf Karten, die per `position: sticky` einrasten. Sobald die nächste Karte sie überdeckt, sinken sie zurück: Skalierung bis 0,945, leichte Verschiebung und ein Schleier in Seitenfarbe

## Prüfstand

Links neben dem Gerät, mobil oberhalb:

| Regler | Wirkung |
|---|---|
| Lesezeit | rechnet gegen die Dezilgrenzen der Vergleichsgruppe und leitet Perzentil, Dezil und Tonstufe ab |
| Vergleichsgruppe | Tag 2 bis 7 — bei Tag 2 greift die Warnung „zu wenige Menschen“ |
| Tageszeit | fünf Abschnitte, Balkenbreite entspricht der Stundenzahl |
| Themenfeld | 40 Felder, steuert Wolke und Empfehlungen |
| Ausspielfläche | Wochenmarkt, Spiele, App — zeigt, was noch nicht entdeckt wurde |
| Blöcke | die unteren Abschnitte einzeln ein- und ausblenden |
| Quellenzeilen | Belegtexte, die nur intern gedacht sind |
| Darstellung | hell, dunkel oder Systemeinstellung |

## Tonstufen

Statt einer harten 50-Prozent-Schwelle vier Stufen — je dünner die Datenlage, desto zurückhaltender die Aussage. **Kein Modul wird ausgeblendet**, nur der Text ändert sich.

| Stufe | Dezil | Kommunikation |
|---|---|---|
| A | 8–10 | Rangaussage mit Zahl und Band |
| B | 5–7 | Vergleich ohne Zahl |
| C | 2–4 | nur der eigene Wert, kein Rang |
| D | 1 | Aussicht statt Rückblick |

Bei weniger als 100 Menschen in der Vergleichsgruppe wird die Rangaussage ausgesetzt.

## Daten

Testdaten. Verteilungen, Dezilgrenzen je Kohorte und die Empfehlungszuordnung liegen als Konstanten im Skript. Keine personenbezogenen Daten.

## Technik

Eine eigenständige HTML-Datei ohne Abhängigkeiten. Einzige externe Ressource ist Google Fonts — Archivo steht als Stellvertreter für Tablet Gothic. `prefers-reduced-motion` und `prefers-color-scheme` werden berücksichtigt, mobil unter 700 px läuft der Prototyp im Vollbild ohne Geräterahmen.

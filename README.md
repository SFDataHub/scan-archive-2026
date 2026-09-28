# scan-archive-2026

Jahresarchiv fuer SFTools-Rohdaten aus dem Jahr 2026.

## Struktur

```text
YYYY-MM/
  <server>/
    YYYY-MM-DD_HHmmssSSSZ.json.gz
manifest.json
```

Jede `.json.gz`-Datei enthaelt ein minifiziertes JSON-Objekt mit den Top-Level-Feldern `players` und `groups`. Die Datensaetze bleiben im bestehenden SFTools-Schema und werden aus der Quelle unveraendert uebernommen.

## Manifest

`manifest.json` verwendet `schemaVersion` 1 und beschreibt jede gespeicherte Scan-Datei mit stabiler ID, Server, numerischem Timestamp, relativem POSIX-Pfad, Formatkennung, Kompression, SHA-256, Datei- und Rohgroesse sowie Spieler- und Gildenanzahl. Die Eintraege sind deterministisch nach Timestamp und Server sortiert.

## Add-only-Regel

Dieses Archiv ist add-only. Bestehende Scan-Dateien duerfen nicht veraendert, normalisiert, zusammengefuehrt oder geloescht werden. Neue Scans werden als neue Dateien ergaenzt und anschliessend im Manifest referenziert.

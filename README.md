# Irondude 2026 – GitHub Pages Paket

## Veröffentlichung
1. Alle Dateien und Ordner aus diesem Verzeichnis in das GitHub-Repository hochladen.
2. In GitHub unter **Settings → Pages** als Quelle **Deploy from a branch** wählen.
3. Branch **main** und Ordner **/(root)** auswählen.
4. Die veröffentlichte GitHub-Pages-Adresse einmal in Safari öffnen.
5. Auf dem iPhone über **Teilen → Zum Home-Bildschirm** als Web-App installieren.

## Enthaltene Funktionen
- 4 feste Spieler: Jan, Max, Sören und David
- Punkte: 1. Platz = 10, 2. Platz = 7, 3. Platz = 5, 4. Platz = 3
- dynamische Startreihenfolge nach dem vorherigen Spiel
- Start mit genau einem Spiel; anschließend beliebig erweiterbar oder einzeln löschbar
- automatische lokale Speicherung nach jeder Änderung
- Import/Export des gesamten Spielstands als JSON-Datei
- Offline-Nutzung nach dem ersten Laden
- dynamische Gesamtwertung und Fortschrittsanzeige
- Gesamtwertung wird vor dem aktuell ausgewählten Spiel angezeigt
- Spielanzahl passt sich beim Hinzufügen und Löschen automatisch an

## Aktualisieren
Bei einer neuen Version alle Dateien ersetzen und committen. Der Service Worker nutzt einen Network-First-Ansatz für die Hauptseite und aktualisiert den Offline-Cache automatisch.

## Version 9.0
- Startet bei neuen Spielständen mit genau einem Spiel.
- Migriert alte, ungenutzte 10-Spiel-Vorlagen automatisch auf die tatsächlich verwendete Spielanzahl.
- Kompaktere Bezeichnungen: GESAMT, SPIEL und „Weiteres Spiel“.
- Das zusätzliche Emblem unter dem Banner wurde entfernt.

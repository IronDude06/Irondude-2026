# Irondude 2026 – GitHub Pages + privater Online-Spielstand

Diese Version nutzt GitHub Pages für die App und ein privates Repository `irondude-2026-data` für den gemeinsamen Spielstand. Es gibt keinen zusätzlichen Server und keinen weiteren Drittanbieter.

## Wichtiges Speicherverhalten

- Jede Eingabe wird weiterhin **sofort lokal auf dem jeweiligen iPhone** gespeichert.
- **Online wird ausschließlich gespeichert, wenn ausdrücklich auf `Speichern` gedrückt wird.**
- Es gibt **keine automatische Online-Speicherung** nach Änderungen und auch keine automatische Online-Speicherung, wenn die Internetverbindung zurückkehrt.
- Solange lokale Änderungen noch nicht online gespeichert wurden, zeigt die Statuszeile entsprechend `Lokale Änderungen · Speichern drücken` bzw. `Änderungen lokal gespeichert · Speichern drücken`.
- Andere Geräte prüfen weiterhin regelmäßig, ob ein neuer **manuell gespeicherter** Online-Stand vorliegt. Eigene noch nicht gespeicherte lokale Änderungen werden dabei nicht überschrieben.
- Der frühere Import-Button wurde vollständig entfernt.

## Einmalige Einrichtung

1. Die Dateien dieses Pakets in das bestehende GitHub-Pages-Repository hochladen und die alten Dateien ersetzen.
2. Das private Repository `irondude-2026-data` muss bestehen.
3. Der Fine-grained Personal Access Token benötigt für dieses Repository `Contents: Read and write`.
4. Beim ersten Start auf jedem iPhone den gemeinsamen Online-Code einmal unter `ONLINE VERBINDEN` eingeben.

## Bedienung

1. Spielname oder Platzierungen eintragen. Die Änderungen liegen sofort lokal auf dem Gerät.
2. Wenn der Stand für alle Freunde bereitstehen soll, oben auf **Speichern** drücken.
3. Nach erfolgreichem Upload erscheint `Online gespeichert · HH:MM Uhr`.
4. Ohne Internet bleiben lokale Eingaben erhalten. Sobald wieder Internet vorhanden ist, muss zum Hochladen weiterhin manuell **Speichern** gedrückt werden.

## Gemeinsamer Stand auf mehreren Geräten

Ein Gerät mit unveränderten lokalen Daten lädt beim Start und anschließend regelmäßig einen neueren Online-Stand. Hat ein Gerät eigene noch nicht manuell gespeicherte Änderungen, werden diese nicht automatisch durch den Online-Stand überschrieben.

Da nur eine `scoreboard.json` verwendet wird, sollte idealerweise nur ein Gerät zur selben Zeit Änderungen vornehmen und anschließend **Speichern** drücken. Der zuletzt erfolgreich manuell gespeicherte Stand ist der gemeinsame Online-Stand.

## Datenschutz

Der Spielstand liegt im privaten Repository `irondude-2026-data`. Das GitHub-Pages-Frontend selbst bleibt bei GitHub Free öffentlich erreichbar. Der Online-Code darf nicht direkt in `index.html` eingetragen oder in das öffentliche Repository committed werden.

## Version 10.1

- Import-Funktion entfernt
- Online-Speicherung ausschließlich manuell über `Speichern`
- lokale Speicherung weiterhin automatisch
- keine automatische Synchronisierung lokaler Änderungen bei Netzwerk-Rückkehr
- automatische Abfrage neuer, bereits manuell gespeicherter Online-Stände bleibt bestehen

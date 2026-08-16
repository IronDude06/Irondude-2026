# Irondude 2026 – GitHub Pages + privater Online-Spielstand

Diese Version erweitert den bisherigen Stand um ein vollständiges Jokersystem und einen Statistikbereich. GitHub Pages liefert die App aus, der gemeinsame Spielstand liegt weiterhin im privaten Repository `irondude-2026-data`.

## Jokerregeln

Jeder Spieler besitzt jeden der drei Joker genau einmal für das gesamte Turnier:

- **Team**: Der Spieler wählt einen Mitspieler. Belegen beide in beliebiger Reihenfolge Platz 1 und 2, erhalten beide jeweils **+3 Punkte**. Mehrere Teamjoker können im selben Spiel eingesetzt werden.
- **Verdopplung**: Die eigenen Punkte aus der Platzierung werden in diesem Spiel verdoppelt. Ein möglicher Team-Bonus wird anschließend zusätzlich addiert.
- **Streichen**: Für den Spieler werden in diesem Spiel **0 Punkte** gewertet, unabhängig von der Platzierung. In den Statistiken wird trotzdem angezeigt, wie viele normale Platzierungspunkte er ohne Streichen erhalten hätte.

Ein Joker, der bei einem Spieler bereits in einem Spiel ausgewählt wurde, wird für diesen Spieler in späteren Spielen nicht mehr angeboten. Wird das betreffende Spiel gelöscht oder der Joker dort wieder entfernt, steht er wieder zur Verfügung.

## Neue Oberfläche

- Neuer Bereich **JOKER** oberhalb von **GESAMT** mit den drei Jokerarten.
- In **GESAMT** werden pro Spieler die drei Joker angezeigt: farbig = verfügbar, grau = bereits genutzt.
- Die bisherige Platzierungsstatistik wurde aus **GESAMT** entfernt.
- Im Bereich **SPIEL** stehen die vier Spieler untereinander. Neben dem Foto befinden sich Platzierung, Joker-Auswahl und die daraus resultierenden Punkte.
- Beim Teamjoker erscheint zusätzlich die Auswahl des Teampartners.
- Unter **Weiteres Spiel** befindet sich **STATISTIKEN** mit:
  1. Platzierungen je Spieler,
  2. kumuliertem Punkteverlauf als Liniendiagramm,
  3. den mit Jokern erzielten Punkten bzw. den beim Streichen nicht gewerteten möglichen Punkten.

## Speicherung

- Jede Änderung wird automatisch **lokal** auf dem jeweiligen Gerät gespeichert.
- **Online wird ausschließlich gespeichert, wenn auf `Speichern` gedrückt wird.**
- Andere Geräte können einen neueren, manuell gespeicherten Online-Stand laden, solange auf dem Gerät keine eigenen ungespeicherten Änderungen vorhanden sind.
- Joker, Teampartner, Spielnamen und alle Ergebnisse werden gemeinsam in `scoreboard.json` gespeichert.

## GitHub-Einrichtung

Die bestehende Einrichtung bleibt unverändert:

1. Dieses Paket in das GitHub-Pages-Repository hochladen und die bisherigen Dateien ersetzen.
2. Das private Repository `irondude-2026-data` muss vorhanden sein.
3. Der verwendete Fine-grained Personal Access Token benötigt `Contents: Read and write` für dieses Repository.
4. Den gemeinsamen Online-Code auf jedem iPhone beim ersten Start einmal eingeben.

## Version 11.0

- Jokersystem Team / Verdopplung / Streichen
- Joker-Verfügbarkeit je Spieler über das gesamte Turnier
- Team-Partnerauswahl und automatische Bonusberechnung
- Gesamtwertung mit Jokerstatus statt Platzierungsübersicht
- Spieler im aktuellen Spiel vertikal angeordnet
- Statistikbereich mit Platzierungen, Punkteverlauf und Joker-Punkten
- Datenmigration für bestehende Spielstände ohne Jokerdaten
- Offline-Cache `irondude-2026-v20`


## Version 11.1
- Joker-Punkte als kompakte Spaltenansicht mit Joker-Symbolen
- Spielerfarben konsistent in Spiel, Gesamtwertung und Statistiken
- Joker-Regel: Verdopplung betrifft nur die eigenen Platzierungspunkte; Team-Bonus +3 wird separat addiert
- Spielverlauf fuer jedes abgeschlossene Spiel im Statistikbereich

## Version 11.2
- Hauptbereiche JOKER, GESAMT, SPIEL und STATISTIKEN auf- und zuklappbar
- Unterbereiche Platzierungen, Punkteverlauf, Joker-Punkte und Spielverlauf separat klappbar
- Kompakte Joker-Auswahl: -, Team, 2x, 0; Teampartner startet mit -
- Einheitliche Profilbildgröße in allen Ansichten
- Joker-Symbole einheitlich im Irondude-Rot; verbrauchte Joker in GESAMT grau
- Punkteverlauf-Legende ohne Spielernamen
- Platzierungsstatistik: Platz 1/2 links, Platz 3/4 rechts
- Spielverlauf nutzt die mobile Breite effizienter
- Offline-Cache `irondude-2026-v22`

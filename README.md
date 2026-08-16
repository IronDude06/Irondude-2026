# Irondude 2026 – GitHub Pages + privater Online-Spielstand

Diese Version speichert den gemeinsamen Spielstand automatisch online in einem **privaten GitHub-Repository**. Die App selbst bleibt eine statische GitHub-Pages-PWA; es gibt keinen zusätzlichen Server und keinen weiteren Drittanbieter.

## Architektur

- **App-Repository**: dein bisheriges GitHub-Pages-Repository (öffentlich, damit GitHub Pages mit GitHub Free funktioniert)
- **Daten-Repository**: `irondude-2026-data` (privat)
- **Online-Datei**: `scoreboard.json` – wird von der App automatisch erstellt und aktualisiert
- **Online-Code**: ein Fine-grained Personal Access Token mit Zugriff ausschließlich auf das private Daten-Repository

Der Online-Code ist **nicht** im HTML hinterlegt. Er wird auf jedem iPhone einmal eingegeben und nur im lokalen Browser-/Web-App-Speicher dieses Geräts abgelegt.

## 1. App aktualisieren

1. Alle Dateien dieses Pakets in dein bisheriges GitHub-Pages-Repository hochladen und die alten Dateien ersetzen.
2. `Commit changes` ausführen.
3. GitHub Pages wie bisher aus `main` / `root` veröffentlichen.

## 2. Privates Daten-Repository anlegen

1. Auf GitHub **New repository** wählen.
2. Repository exakt `irondude-2026-data` nennen.
3. Sichtbarkeit **Private** wählen.
4. **Add a README file** aktivieren, damit der Branch `main` direkt angelegt wird.
5. Repository erstellen.

Du musst dort keine `scoreboard.json` anlegen. Die App erstellt die Datei beim ersten erfolgreichen Verbinden automatisch.

## 3. Online-Code erstellen

In GitHub:

1. Profilbild → **Settings**.
2. **Developer settings**.
3. **Personal access tokens** → **Fine-grained tokens**.
4. **Generate new token**.
5. Als Repository-Zugriff **Only select repositories** wählen und ausschließlich `irondude-2026-data` auswählen.
6. Unter **Repository permissions** nur **Contents: Read and write** vergeben. Metadaten-Lesezugriff wird von GitHub automatisch bereitgestellt.
7. Ein sinnvolles Ablaufdatum wählen, z. B. nach eurer Reise.
8. Token erstellen und direkt kopieren. GitHub zeigt ihn später nicht erneut vollständig an.

Dieser Token ist euer gemeinsamer **Online-Code**.

## 4. Auf deinem iPhone verbinden

1. Die aktualisierte GitHub-Pages-Adresse in Safari öffnen.
2. Beim ersten Start erscheint **ONLINE VERBINDEN**.
3. Den Online-Code einfügen und **Verbinden** wählen.
4. Wenn auf deinem iPhone bereits ein lokaler Spielstand vorhanden ist, fragt die App einmalig, ob dieser zum gemeinsamen Online-Stand werden soll.
5. Danach wird der Code auf diesem Gerät gespeichert.

## 5. Freunde verbinden

1. Deine Freunde öffnen dieselbe GitHub-Pages-Adresse bzw. die bereits installierte Home-Screen-App.
2. Du sendest ihnen den Online-Code separat, z. B. per AirDrop/iMessage.
3. Jeder fügt den Code beim ersten Start einmal ein.
4. Anschließend lädt die App automatisch den gemeinsamen Spielstand.

Ein GitHub-Konto ist auf den iPhones deiner Freunde dafür nicht erforderlich; der Online-Code authentifiziert die App gegenüber dem privaten Daten-Repository.

## Verhalten beim Spielen

- Jede Änderung wird sofort lokal gespeichert.
- Nach kurzer Verzögerung wird sie automatisch zu GitHub synchronisiert.
- **Speichern** erzwingt eine sofortige Online-Synchronisierung.
- Alle 20 Sekunden prüft die App, ob auf einem anderen Gerät ein neuer Stand gespeichert wurde.
- Ohne Internet bleibt die App nutzbar und speichert lokal. Sobald wieder eine Verbindung besteht, wird erneut synchronisiert.
- Die Zeile unter den Buttons zeigt z. B. `Online gespeichert`, `Offline · lokal gespeichert` oder einen Verbindungsfehler.
- Durch Antippen dieser Statuszeile kann der Online-Code verwaltet oder entfernt werden.
- **Import** für vorhandene JSON-Sicherungen bleibt erhalten; ein importierter Stand wird anschließend online synchronisiert.

## Hinweis bei gleichzeitiger Bearbeitung

Die Lösung ist bewusst schlank und verwendet eine einzelne `scoreboard.json`. Am zuverlässigsten ist sie, wenn immer nur ein Gerät zur selben Zeit aktiv Eingaben vornimmt. Die anderen Geräte können den Stand ansehen und werden automatisch aktualisiert. Bei nahezu gleichzeitigen Schreibvorgängen gilt praktisch der zuletzt erfolgreich gespeicherte Stand.

## Datenschutz / Öffentlichkeit

Der eigentliche Spielstand liegt ausschließlich im privaten Repository `irondude-2026-data` und ist ohne Online-Code nicht abrufbar. Das GitHub-Pages-Frontend selbst ist bei der kostenlosen GitHub-Pages-Nutzung weiterhin öffentlich erreichbar. Ohne Online-Code kann es jedoch den privaten gemeinsamen Spielstand nicht laden.

Den GitHub-Token **nicht** direkt in `index.html` eintragen oder in ein öffentliches Repository committen.

## Version 10.0

- automatisches Online-Speichern über die GitHub Contents API
- privates Daten-Repository ohne weiteren Anbieter
- einmalige Eingabe eines gemeinsamen Online-Codes je Gerät
- automatisches Laden neuer Spielstände anderer Geräte
- Offline-Fallback mit späterer Synchronisierung
- `Speichern` löst sofortige Cloud-Synchronisierung aus
- bestehender JSON-Import bleibt erhalten

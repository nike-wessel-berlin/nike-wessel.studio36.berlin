# AGENTS.md

Website von Nike Wessel: [nike-wessel.studio36.berlin](https://nike-wessel.studio36.berlin/)

Nike ist keine Entwicklerin. Antworte auf Deutsch, kurz und ohne Fachjargon. Führe alle Befehle selbst aus.

Sie braucht nur zwei Dinge:

## 1. Vorschau ("Vorschau", "zeig mal", "lokal anschauen")

Es läuft immer nur **ein** Vorschau-Server, fest auf http://localhost:5173.

1. Prüfen, ob schon einer läuft: `lsof -nP -iTCP:5173 -sTCP:LISTEN`
   - Läuft einer: nicht neu starten. Änderungen erscheinen dort automatisch.
   - Läuft keiner: falls `node_modules` fehlt, `npm install`. Dann `npm run dev` im Hintergrund starten.
2. Ihr den Link geben: http://localhost:5173

Meldet `npm run dev`, dass Port 5173 belegt ist, läuft bereits ein Server. Den einfach weiterverwenden, keinen zweiten auf einem anderen Port starten.

## 2. Live stellen ("deploy", "veröffentlichen", "live stellen")

Ohne Rückfragen komplett durchführen:

1. `gh auth status` – Account muss **nike-wessel-berlin** sein. Sonst abbrechen und ihr sagen: `gh auth login` ausführen.
2. `git pull --rebase origin main`
3. `npm run build` – bei Fehlern erst beheben, nie mit kaputtem Build deployen.
4. Alles committen mit kurzer deutscher Nachricht, was sich geändert hat.
5. `git push origin main`
6. `npm run deploy` – erst das stellt die Seite live (Branch `gh-pages`).
7. Melden: was live ist, Link zur Seite, sichtbar in 1–2 Minuten.

Keine Änderungen vorhanden? Einfach sagen, nichts deployen.

## Nicht machen

- Kein `git push --force`, keine neuen Branches, nichts direkt an `gh-pages` ändern.

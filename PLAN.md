# Plan -- Feinschliff Quintenzirkel

Ausgangspunkt: funktionierender Prototyp in `index.html`. Diese Datei
beschreibt die naechsten Schritte fuer den Feinschliff in Claude Code.
Reihenfolge ist ein Vorschlag, keine zwingende Abfolge.

## 1. Projektstruktur

Aktuell ist alles in einer `index.html`. Das ist gut zum Deployen, aber
fuer die Weiterentwicklung unhandlich.

- Code in Module trennen (Geometrie, Akkord-Logik, Renderer, UI/State).
- Leichtes Setup erwaegen (z. B. Vite), das sich weiterhin statisch fuer
  GitHub Pages bauen laesst. Der Deploy-Weg ueber Pages muss erhalten bleiben.
- Build-Output weiterhin als statische Dateien, kein Backend.

## 2. Gitarrengriffe -- echte Datenbasis

Wichtigste inhaltliche Verbesserung.

- Die kuratierten Voicings durch eine echte Quelle ersetzen, z. B. die
  Chord-Datenbank `@tombatossals/chords-db`, oder eine Voicing-Engine.
- Alternative Griffe pro Akkord ermoeglichen (durchblaettern).
- Korrektheit gegen die Theorie pruefen -- die Rollenfaerbung (Grundton /
  Terz / Quinte) muss zu den tatsaechlich gegriffenen Toenen passen.

## 3. Vierklaenge optional zuschaltbar

- maj7, m7 und m7b5 als optionale Erweiterung der drei Ringe
  (Dur -> maj7, Moll -> m7, vermindert -> m7b5 / halbvermindert).
- Per Schalter zuschaltbar, Dreiklaenge bleiben Standard.

## 4. Schablone per Drag drehen

- Die Modi-Schablone zusaetzlich per Maus/Touch drehbar machen, nicht
  nur per Pfeiltasten. Beim Loslassen auf das naechste Segment einrasten.
- Pfeiltasten als Bedienoption erhalten.


## 5. Feinschliff UI

- Verhalten auf Mobilgeraeten / kleinen Viewports pruefen.
- Optional: gewaehlte Tonart / Modus als Zustand in der URL ablegen,
  damit Ansichten teilbar sind.

## Offene Frage fuer spaeter

- Erste und zweite Umkehrung gibt es schon beim Klavier. Soll es etwas
  Vergleichbares auch fuer die Gitarre geben (verschiedene Lagen)?

## Nicht vergessen

- Musiktheorie bleibt das Fundament -- vor Logikaenderungen Korrektheit
  pruefen.
- Der Deploy ueber GitHub Pages muss in jedem Schritt funktionsfaehig
  bleiben.

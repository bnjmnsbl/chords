# Interaktiver Quintenzirkel

## Was das ist

Eine interaktive Lern-Webseite rund um den Quintenzirkel, gedacht als
Werkzeug fuer das Verstaendnis von Tonarten, diatonischen Dreiklaengen und
Kirchentonarten. Standalone, ohne Backend, deploybar ueber GitHub Pages.

## Aktueller Stand

Funktionierender Prototyp in einer einzigen Datei: `index.html`.
Reines HTML/CSS/JS, keine externen Abhaengigkeiten, kein Build-Schritt.
Diese Datei ist die Quelle der Wahrheit fuer alle bisher umgesetzte Logik.

## Konzept und Aufbau

Drei konzentrische Ringe, je 12 Segmente, im Quintenabstand angeordnet:

- **Innerer Ring** -- Durtonarten (I): C, G, D, A, E, H, Fis, Des, As, Es, B, F
- **Mittlerer Ring** -- parallele Molltonarten (vi): Am, Em, Hm, ...
- **Aeusserer Ring** -- verminderte Dreiklaenge der 7. Stufe (vii-vermindert): H-vermindert, ...

Jedes "Tortenstueck" zeigt damit die drei diatonischen Grunddreiklaenge
einer Durtonart (Dur / Moll / vermindert).

### Modi-Schablone

Ein ein- und ausblendbarer Layer, der die sieben Kirchentonarten markiert.
Er deckt drei benachbarte Segmente ab und ist bewusst NICHT symmetrisch:

- innerer Ring: Lyd -- Ion -- Mix
- mittlerer Ring: Dor -- Aeo -- Phr
- aeusserer Ring: Loc (nur das mittlere Segment)

Die Schablone laesst sich in 30-Grad-Schritten um den Mittelpunkt drehen.
Steht Ion ueber C, zeigt sie die sieben Modi von C-Dur. Dreht man sie ein
Segment im Uhrzeigersinn, landet Ion auf G usw. Sie ist halbtransparent,
sodass die Akkordnamen darunter lesbar bleiben.

## Funktionen (bereits umgesetzt)

- Klick auf ein Segment zeigt das Griffbild des Akkords.
- Umschalten zwischen Gitarren- und Klaviergriffen.
- Gitarre: kuratierte Standard-Voicings (offene Akkorde wo moeglich, sonst Barre).
- Klavier: Dreiklang in Grundstellung sowie 1. und 2. Umkehrung.
- Grundton / Terz / Quinte sind farblich unterschieden (mit Legende).
- Modi-Schablone ein-/ausblendbar und per Pfeiltasten drehbar.
- Eigenes Dark-/Light-Mode-Schema ueber `prefers-color-scheme`.

## Wichtige Designentscheidungen

- Die Schablone dreht sich um den Kreismittelpunkt, ein Klick = ein Segment.
- Die Gitarrengriffe sind ein fest hinterlegtes, kuratiertes Set --
  KEIN Algorithmus. Das ist die wichtigste bekannte Einschraenkung.
- Bekannter, bereits behobener Bug: Beim Ableiten des Grundtons aus dem
  Akkordnamen muss `dim` vor `m` entfernt werden, sonst wird das "m" aus
  "dim" mit abgeschnitten.

## Musiktheorie -- bitte sorgfaeltig

Die Theorie muss korrekt bleiben. Vor Aenderungen an der Akkord- oder
Modus-Logik die Stimmigkeit pruefen. Bei Unsicherheit lieber nachfragen
als raten.

## Zielgruppe

Ein fortgeschrittener Gitarrist, der seine Musiktheorie vertiefen will.
Das Werkzeug soll didaktisch klar sein, nicht ueberladen.

## Naechste Schritte

Siehe `PLAN.md`.

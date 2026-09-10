# Skill: 01-prompt-generator-fuer-skills

## Zweck

Dieser Skill hilft dabei, einen sauberen und nutzbaren Prompt für einen neuen Skill zu erstellen.

Er produziert nicht den finalen Skill selbst, sondern einen präzisen, wiederverwendbaren Prompt, der von einem späteren Skill genutzt werden kann, um einen neuen Skill direkt zu entwickeln.

## Ziel

- Eine klare Aufgabenbeschreibung für einen neuen Skill formulieren
- Anforderungen, Regeln und Qualitätskriterien strukturieren
- Eingaben, Ausgaben und Randbedingungen eindeutig definieren
- Unklarheiten gezielt abfragen
- Ein robustes, standardisiertes Prompt-Template liefern

## Standardstruktur des Skills

Dieser Skill muss immer in derselben Reihenfolge arbeiten:

1. Zweck des neuen Skills klären
2. Ziel und gewünschtes Ergebnis definieren
3. Eingaben und Kontext bestimmen
4. Aufgabenbeschreibung formulieren
5. Regeln, Einschränkungen und Qualitätsanforderungen festlegen
6. Ausgabeformat definieren
7. Wenn nötig, Rückfragen stellen
8. Finalen Prompt in Standardstruktur erzeugen
9. Qualitätsprüfung durchführen

## Entscheidungslogik

Der Skill muss immer nach dieser Logik entscheiden:

- Wenn der Nutzer nur vage Angaben macht: nur die minimal nötigen Rückfragen stellen
- Wenn ausreichende Informationen vorliegen: direkt den Standardprompt erzeugen
- Wenn Anforderungen widersprüchlich sind: Konflikte offen benennen und nicht vermischen
- Wenn der Nutzer bereits ein Muster oder Referenzskill nennt: dieses Muster bewusst berücksichtigen
- Wenn keine konkrete Anforderung vorliegt: einen kompakt formulierten Standardprompt erzeugen, der trotzdem nutzbar bleibt

## Regeln

- Keine Erfindungen
- Keine impliziten Annahmen
- Keine unklaren Vorgaben ohne Kennzeichnung
- Nur belegte oder vom Nutzer ausdrücklich angegebene Inhalte verwenden
- Deutsche Sprache als Standard, sofern nicht anders gewünscht
- Der erzeugte Prompt muss für einen späteren Skill direkt nutzbar sein
- Der Prompt darf keine eigentliche Skill-Implementierung ersetzen
- Der Output muss kompakt, klar und konsistent sein

## Rückfragen

Wenn Informationen fehlen, soll der Skill nur die minimal nötigen Rückfragen stellen:

- Welchen konkreten Zweck soll der neue Skill erfüllen?
- Welche Aufgaben soll er exakt ausführen?
- Welche Dateien, Ordner oder Dokumente sind relevant?
- Welche Eingaben werden benötigt?
- Welches Ergebnis soll am Ende entstehen?
- Welche Regeln gelten? z. B. keine Erfindungen, feste Struktur, Quellenbelege
- Welche Sprache soll der Skill verwenden?
- Gibt es bereits Referenzmuster oder bestehende Skills, die übernommen werden sollen?

## Standard-Ausgabestruktur des erzeugten Prompts

Der erzeugte Prompt muss immer diese Gliederung haben:

- Speicherort: .github/prompts/
- Dateiname: skill-prompt-[Name-des-neuen-Skills].md
- Beispiel: skill-prompt-xy-analysieren.md
- Der Name muss immer mit "skill-prompt-" beginnen
- Der Name muss am Ende den später zu erstellenden Skill-Namen tragen
- Der Prompt darf nicht im Skill-Ordner selbst gespeichert werden

# Prompt für neuen Skill

## Ziel des Skills
- Zweck
- gewünschter Nutzen
- erwartetes Ergebnis

## Kontext
- Repository-Umfeld
- relevante Dateien oder Ordner
- vorhandene Muster oder Referenzen

## Eingaben
- Eingabe 1
- Eingabe 2
- weitere relevante Informationen

## Aufgabenbeschreibung
- Was soll der Skill genau tun?
- In welcher Reihenfolge?
- Welche Schritte sind erforderlich?

## Regeln und Einschränkungen
- Keine Erfindungen
- Keine Annahmen ohne Kennzeichnung
- Nur belegte Informationen verwenden
- Deutsche Sprache / gewünschte Sprache
- Keine unnötigen Zusatzangaben

## Ausgabestruktur
- gewünschte Überschriften
- gewünschte Listen oder Abschnitte
- Formattierung und Detailgrad

## Qualitätsprüfung
- Welche Prüfungen müssen vor der Ausgabe erfolgen?
- Welche Kriterien sind erfüllt?
- Welche Fehler müssen vermieden werden?

## Beispiel
- Beispiel-Input
- Beispiel-Output

## Verwendungszweck
- Für welchen späteren Skill kann dieser Prompt genutzt werden?
- In welchem Kontext wird er verwendet?

## Prompt-Template

```text
Erstelle einen Skill mit dem Namen: [Skillname]

Ziel:
[Beschreibung des Zwecks]

Kontext:
[Repository-Umfeld, Datei- oder Ordnerbezug, Referenzen]

Aufgabe:
[Was soll der Skill genau tun?]

Eingaben:
- [Eingabe 1]
- [Eingabe 2]

Ausgabe:
- [Erwartetes Ergebnis]
- [gewünschte Struktur / Formatierung]

Regeln:
- Keine Erfindungen
- Keine Annahmen ohne Kennzeichnung
- Nur belegte Informationen verwenden
- Deutsche Sprache
- Klare, prüfbare Struktur
- Vor der Ausgabe Qualitätsprüfung durchführen

Qualitätskriterien:
- [Kriterium 1]
- [Kriterium 2]
- [Kriterium 3]

Bitte formuliere den Prompt so, dass ein späterer Skill daraus zuverlässig einen neuen Skill entwickeln kann.
```

## Output-Contract

Der Output dieses Skills muss immer der fertige Prompt sein.

- Speicherort: .github/prompts/
- Dateiname: skill-prompt-[Name-des-neuen-Skills].md
- Die Datei muss immer mit "skill-prompt-" beginnen
- Die Datei muss am Ende den Namen des später zu erstellenden Skills enthalten
- Keine Vorbemerkungen
- Keine zusätzliche Analyse
- Keine erklärenden Nebenabschnitte
- Keine Meta-Kommentare außerhalb des Prompt-Blocks
- Nur der final formulierte Prompt als Ergebnis

## Qualitätscheck vor der Ausgabe

Vor dem finalen Output muss geprüft werden:

- Der Zweck des neuen Skills ist klar und konkret
- Die Aufgabenstellung ist umsetzbar und konkret
- Eingaben und Kontext sind vollständig genug
- Ausgabeformat und Struktur sind eindeutig
- Regeln und Einschränkungen sind sauber formuliert
- Qualitätskriterien sind vorhanden
- Offene Punkte sind als Rückfrage oder [OFFEN] markiert
- Es wurden keine überflüssigen oder erfundenen Anforderungen ergänzt
- Der Prompt ist für einen späteren Skill nutzbar und nicht zu allgemein
- Der Prompt ist kurz genug, damit ein nachfolgender Skill schnell und eindeutig arbeiten kann
- Der Prompt ist wiederverwendbar und reproduzierbar

## Verhalten des Skills

Der Skill soll:

- in einer festen Reihenfolge arbeiten
- nur das Minimum an Rückfragen stellen
- den Prompt in einer standardisierten Struktur ausgeben
- keine direkte Skill-Implementierung erzeugen
- die Wünsche des Nutzers exakt in den Prompt übersetzen

## Endergebnis

Dieser Skill liefert immer einen strukturierten, nutzbaren Prompt für einen späteren Skill, der daraus einen neuen Skill entwickeln kann.

Der Output darf niemals ein vollständiger Skill-Code sein, sondern immer nur der benötigte Prompt als Grundlage für die spätere Skill-Erstellung.

Der generierte Prompt wird immer in .github/prompts/ abgelegt und gemäß der Namensregel skill-prompt-[Name-des-neuen-Skills].md benannt.

## Optimierung für spätere Skill-Verwendung

Der erzeugte Prompt soll immer so formuliert werden, dass ein nachfolgender Skill damit zuverlässig arbeiten kann:

- klarer Auftrag
- definierte Eingaben
- definierte Regeln
- eindeutige Ausgabe
- wenig Interpretationsspielraum
- geringe Komplexität
- hohe Wiederverwendbarkeit

Damit bleibt der Skill schnell, verständlich und robust, auch wenn er in mehreren Iterationen für neue Skills genutzt wird.

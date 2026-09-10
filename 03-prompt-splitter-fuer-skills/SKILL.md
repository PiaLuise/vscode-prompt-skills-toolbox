# Skill: 03-prompt-splitter-fuer-skills

## Zweck

Dieser Skill scannt vorhandene Prompt-Inhalte aus mehreren Quellordnern, analysiert und gruppiert sie fachlich und teilt sie in einzelne, hochwertige Skill-Prompts auf. Die resultierenden Skill-Prompts werden gemäß den Anforderungen des Skills 01-prompt-generator-fuer-skills erzeugt.

## Ziel

- Vorhandene Prompt-Inhalte aus mehreren Quellordnern systematisch einlesen
- Inhalte nach Thema, Zweck, Aufgaben, Ein-/Ausgaben und Prozesslogik analysieren
- Gemeinsamkeiten, Überschneidungen und thematische Abgrenzungen identifizieren
- Inhalte in logisch abgegrenzte Gruppen aufteilen
- Für jede Gruppe einen eigenständigen, hochwertigen Skill-Prompt erzeugen
- Alle erzeugten Skill-Prompts konsistent nach Struktur, Qualität und Namenslogik des Skills 01-prompt-generator-fuer-skills gestalten

## Kontext

Der Skill arbeitet mit mehreren Prompt-Quellen, die thematisch zusammenhängen, aber in unterschiedlichen Ordnern und Varianten vorliegen. Relevante Quellordner:
- [OFFEN]

Als verbindliche Referenz für Struktur, Qualität und Namenslogik der zu erzeugenden Skill-Prompts dient der Skill 01-prompt-generator-fuer-skills.

Als verbindliche fachliche Referenz dafür, können Dateien aus dem Ordner "input" genutzt werden - soweit angegeben.

## Standardstruktur / Verarbeitungsschritte

1. Ordnerinhalte der Quellordner identifizieren und prüfen.
2. Alle Prompt-Dateien in den angegebenen Ordnern einlesen und auflisten.
3. `input/Umsetzungsliste_Skills.md` einlesen und je Phase die dort definierten Ziel-Skills (Name, Definition, Skill-Art) erfassen.
4. Inhalte der Quell-Prompts analysieren und systematisch klassifizieren: Hauptziel, Aufgabenstellung, Ein- und Ausgaben, Regeln und Einschränkungen, erwartete Struktur, Wiederverwendbarkeit, fachliche Zusammenhänge.
5. Gemeinsamkeiten, Überschneidungen und thematische Abgrenzungen identifizieren.
6. Analysierte Inhalte in logisch zusammengehörende Gruppen aufteilen, sodass jede Gruppe ein eigenes, klar abgegrenztes Ziel hat.
7. Jede gebildete Gruppe einem konkreten Eintrag aus `Umsetzungsliste_Skills.md` zuordnen, indem Zweck der Gruppe und Definition des Listeneintrags fachlich abgeglichen werden. Eine Gruppe ohne passenden Eintrag wird als [OFFEN] gekennzeichnet, nicht künstlich einem Eintrag zugeordnet.
8. Für jeden zugeordneten Listeneintrag prüfen, ob unter `.github/skills` bereits ein passender Ordner nach dem Muster `phase-[Phasennummer]-[laufende Nummer]-[skill-name-slug]` existiert.
9. Für jede resultierende Gruppe einen separaten Prompt für den zugeordneten Ziel-Skill formulieren, wobei der Skill-Name exakt dem Namensmuster des zugehörigen (bestehenden oder noch zu erstellenden) Skill-Ordners entspricht.
10. Den Skill 01-prompt-generator-fuer-skills dabei als Standard-Referenz verwenden (gleiche Struktur, Qualitätsanforderungen, Regeln, Output-Normalisierung, Namens- und Speicherlogik).
11. Die erzeugten Einzel-Prompts im Ordner .github/prompts speichern.
12. Jede erzeugte Datei muss mit "skill-prompt-" beginnen und am Ende den Namen des zugeordneten Ziel-Skills tragen: skill-prompt-[phase-Phasennummer-laufendeNummer-skill-name-slug].md.
13. Wenn für den zugeordneten Ziel-Skill unter `.github/skills` noch **kein** Ordner bzw. keine `SKILL.md` existiert, im Anschluss an die Erstellung der Skill-Prompt-Datei den Skill 02-skill-generator-aus-skill-prompt nutzen, um aus dieser Skill-Prompt-Datei den fehlenden Skill-Ordner samt `SKILL.md` anzulegen.
14. Wenn der Ziel-Skill-Ordner bereits existiert (auch mit leerer `SKILL.md`), dies in der Ergebnisliste vermerken, ohne den bestehenden Ordner ungefragt zu überschreiben.
15. Qualitätsprüfung durchführen.
16. Ergebnisliste mit den erzeugten Skill-Prompts, ihren Zielen, der zugeordneten Zeile aus `Umsetzungsliste_Skills.md` und dem Status des Ziel-Skill-Ordners (bereits vorhanden / neu angelegt / noch [OFFEN]) erstellen.

## Entscheidungslogik

- Wenn ein Ordner leer ist: dies dokumentieren, keine fiktiven Inhalte erzeugen.
- Wenn Inhalte in mehreren Ordnern wiederholt vorkommen: gemeinsame Themencluster bilden.
- Wenn keine klare fachliche Trennung möglich ist: nur die nächstliegende, saubere Gliederung bilden und als [OFFEN] kennzeichnen.
- Wenn ein Prompt zu allgemein ist: in mehrere, klar abgegrenzte Skill-Prompts aufteilen.
- Wenn ein Prompt zu klein oder nicht eigenständig nutzbar ist: mit einem passenden Nachbarthema zusammenführen.
- Wenn eine gebildete Gruppe keinem Eintrag aus `Umsetzungsliste_Skills.md` eindeutig zugeordnet werden kann: keinen Skill-Namen erfinden, sondern die Zuordnung als [OFFEN] kennzeichnen.
- Wenn für einen zugeordneten Ziel-Skill bereits ein Ordner mit `SKILL.md` unter `.github/skills` existiert: die Skill-Prompt-Datei trotzdem wie gewohnt erzeugen bzw. aktualisieren, aber keinen neuen Skill-Ordner anlegen und keinen bestehenden Ordner ungefragt überschreiben.
- Wenn für einen zugeordneten Ziel-Skill noch kein Ordner existiert: nach Erstellung der Skill-Prompt-Datei den Skill 02-skill-generator-aus-skill-prompt einsetzen, um den fehlenden Skill-Ordner mit `SKILL.md` anzulegen.
- Wenn zu einer Phase in `Umsetzungsliste_Skills.md` "Noch keine Einträge vorhanden" steht (z. B. aktuell Phase 06–10): für diese Phase keine Skill-Prompts erzeugen, da keine Zieldefinition vorliegt.

## Regeln

- Keine Erfindungen
- Keine Annahmen ohne Kennzeichnung
- Keine unklaren oder breiten Aussagen, wenn die Quelle das nicht belegt
- Keine künstlich erzeugten Skillnamen ohne fachliche Grundlage
- Skill-Namen und die Zuordnung von Prompt-Gruppen zu Skills dürfen ausschließlich aus `input/Umsetzungsliste_Skills.md` abgeleitet werden, nicht frei erfunden werden
- Nur tatsächlich aus den analysierten Prompts abgeleitete Inhalte verwenden
- Widersprüche müssen sichtbar bleiben und nicht eigenständig gelöst werden
- Die vorhandenen Ordnerinhalte müssen fachlich sauber aufgeteilt werden, nicht nur nach Dateinamen
- Die Ausgabe muss standardisiert und reproduzierbar sein
- Jede resultierende Prompt-Datei muss dieselbe Struktur wie der Skill 01-prompt-generator-fuer-skills haben
- Die Speicherung erfolgt immer in .github/prompts
- Der Dateiname muss immer mit "skill-prompt-" beginnen und den Namen des zugeordneten Ziel-Skills gemäß Namensmuster `phase-[Phasennummer]-[laufende Nummer]-[skill-name-slug]` am Ende tragen
- Bestehende Skill-Ordner und `SKILL.md`-Dateien unter `.github/skills` dürfen nicht ungefragt überschrieben werden
- Fehlt für einen zugeordneten Ziel-Skill der Ordner bzw. die `SKILL.md` unter `.github/skills`, muss zwingend der Skill 02-skill-generator-aus-skill-prompt genutzt werden, um ihn anzulegen

## Eingaben

- Inhalte aus den genannten Quellordnern mit Prompt-Dateien
- `input/Umsetzungsliste_Skills.md` als Referenz für Name, Definition und Phase der Ziel-Skills
- Bestehende Skill-Ordner unter `.github/skills` (inkl. bereits angelegter, aber ggf. leerer `phase-*`-Ordner) zur Prüfung, ob ein Ziel-Skill bereits existiert
- Gesamtzielsetzung: Aufteilung in einzelne, saubere Skill-Prompts mit korrekter Zuordnung zu den Ziel-Skills
- Vorgaben des Skills 01-prompt-generator-fuer-skills
- Vorgaben des Skills 02-skill-generator-aus-skill-prompt für den Fall fehlender Ziel-Skill-Ordner
- Gewünschte Ausgabequalität und Standardstruktur

## Ausgabestruktur / Output-Contract

Jeder erzeugte Skill-Prompt folgt exakt dieser Gliederung:
- Ziel des Skills
- Kontext
- Eingaben
- Aufgabenbeschreibung
- Regeln und Einschränkungen
- Ausgabestruktur
- Qualitätsprüfung
- Beispiel
- Verwendungszweck
- Prompt-Template
- Output-Contract
- Qualitätsprüfung vor der Ausgabe
- Verhalten des Skills
- Endergebnis

Speicherort: .github/prompts/
Dateiname: skill-prompt-[phase-Phasennummer-laufendeNummer-skill-name-slug].md, entsprechend dem zugeordneten Eintrag aus `Umsetzungsliste_Skills.md`

Zusätzlich kann eine kurze Ergebnisübersicht erstellt werden, die zeigt: welche Prompt-Dateien erkannt wurden, welche Gruppen gebildet wurden, welche resultierenden Skill-Prompts entstanden sind, welchem Eintrag aus `Umsetzungsliste_Skills.md` sie zugeordnet wurden, wo sie gespeichert wurden und ob der zugehörige Ziel-Skill-Ordner bereits bestand oder mithilfe von 02-skill-generator-aus-skill-prompt neu angelegt wurde.

## Qualitätsprüfung

- Jeder resultierende Skill-Prompt ist klar und eindeutig von anderen abgegrenzt
- Keine Überlappung ohne fachliche Begründung
- Keine verschachtelten oder unklaren Aufgabenbereiche
- Jeder Prompt ist für einen eigenen Skill nutzbar
- Struktur konsistent und identisch zum Standard des Skills 01-prompt-generator-fuer-skills
- Prompt-Dateien sind sauber benannt und korrekt gespeichert
- Aufteilung entspricht fachlichen Themen, nicht bloß Dateinamen
- Jede Zuordnung zu einem Ziel-Skill ist durch einen konkreten Eintrag in `Umsetzungsliste_Skills.md` belegt
- Für jeden zugeordneten Ziel-Skill wurde geprüft, ob der Skill-Ordner mit `SKILL.md` unter `.github/skills` bereits existiert; fehlende Ordner wurden über 02-skill-generator-aus-skill-prompt angelegt
- Resultierende Prompts sind kurz genug für zuverlässige spätere Nutzung

## Verhalten des Skills

Der Skill soll:
- Ordnerinhalte identifizieren und prüfen
- Prompt-Dateien einlesen und analysieren
- `input/Umsetzungsliste_Skills.md` als verbindlichen Katalog der Ziel-Skills einlesen
- Inhalte nach Thema, Zweck und Aufgaben logisch gliedern
- mögliche Überschneidungen und Abhängigkeiten erkennen
- Einzelthemen in eigenständige Skill-Prompts übersetzen und jede Gruppe einem konkreten Eintrag aus `Umsetzungsliste_Skills.md` zuordnen
- den Skill 01-prompt-generator-fuer-skills als Pflicht-Referenz für Struktur und Qualität verwenden
- jede final erzeugte Datei nach der Namensregel skill-prompt-[phase-Phasennummer-laufendeNummer-skill-name-slug].md benennen und in .github/prompts speichern
- prüfen, ob der zugeordnete Ziel-Skill-Ordner mit `SKILL.md` bereits unter `.github/skills` existiert
- bei fehlendem Ziel-Skill-Ordner den Skill 02-skill-generator-aus-skill-prompt einsetzen, um diesen aus der erzeugten Skill-Prompt-Datei anzulegen
- eine Qualitätsprüfung durchführen
- eine Ergebnisliste mit den erzeugten Skill-Prompts, ihren Zielen und dem Status ihres Ziel-Skill-Ordners erstellen

## Endergebnis

Dieser Skill liefert immer eine Menge finaler Skill-Prompt-Dateien im Ordner .github/prompts, die jeweils einen vollständig formulierten, eigenständig nutzbaren Prompt für einen einzelnen Ziel-Skill aus `input/Umsetzungsliste_Skills.md` enthalten – strukturell identisch zum Standard des Skills 01-prompt-generator-fuer-skills. Für Ziel-Skills, deren Ordner unter `.github/skills` noch nicht existiert, wird zusätzlich mithilfe des Skills 02-skill-generator-aus-skill-prompt der fehlende Skill-Ordner samt `SKILL.md` angelegt.

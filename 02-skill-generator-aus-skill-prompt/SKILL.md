Erstelle einen Skill mit dem Namen: skill-generator-aus-skill-prompt

Ziel:
Dieser Skill soll aus einem vorhandenen Skill-Prompt (einer Datei im Ordner .github/prompts, deren Name mit "skill-prompt-" beginnt) einen vollständigen, direkt einsatzfähigen neuen Skill erzeugen. Der Skill liest den passenden Skill-Prompt ein, leitet daraus eine vollständige Skill-Definition ab und legt diese als neuen Skill-Ordner im Verzeichnis .github/skills ab. Der neue Skill wird dabei ausschließlich auf Basis des Inhalts des gewählten Skill-Prompts erzeugt, nicht auf Basis eigener Annahmen.

Kontext:
Im Repository existiert der Skill 01-prompt-generator-fuer-skills, der Skill-Prompts nach einer festen Struktur erzeugt und im Ordner .github/prompts ablegt. Diese Dateien folgen immer dem Namensmuster:
- skill-prompt-[Name-des-neuen-Skills].md

Beispiele:
- skill-prompt-splitter-fuer-prompts.md
- skill-prompt-xy-analysieren.md

Der vorliegende Skill setzt genau an dieser Stelle an: Er nimmt einen oder mehrere dieser bereits erzeugten Skill-Prompts als Eingabe und wandelt sie in fertige, nutzbare Skills um. Als Referenz für Aufbau und Qualität bestehender, bereits erzeugter Skills dienen die vorhandenen Ordner in .github/skills, z. B. 01-prompt-generator-fuer-skills/SKILL.md sowie die phase-*-Skills.

Aufgabe:
Der Skill soll die folgenden Aufgaben ausführen:

1. Den Ordner .github/prompts nach Dateien durchsuchen, deren Name mit "skill-prompt-" beginnt.
2. Existiert mehr als eine passende Datei, muss immer beim Nutzer nachgefragt werden, welcher Skill-Prompt verwendet werden soll – auch wenn der Nutzer bereits einen Hinweis gegeben hat. Erst nach eindeutiger Bestätigung durch den Nutzer wird fortgefahren.
3. Den Inhalt der gewählten Skill-Prompt-Datei vollständig einlesen und auswerten (Ziel, Kontext, Aufgabe, Eingaben, Ausgabe, Regeln, Ausgabestruktur, Qualitätskriterien, Verarbeitungsschritte, Fehler- und Grenzfälle).
4. Den Skill-Namen aus dem Dateinamen ableiten, indem das Präfix "skill-prompt-" und die Dateiendung ".md" entfernt werden.
5. Prüfen, ob unter .github/skills bereits ein Ordner mit diesem Namen bzw. eine SKILL.md darin existiert. Ist das der Fall, muss vor jeder weiteren Aktion beim Nutzer nachgefragt werden, ob der bestehende Skill überschrieben werden darf. Ohne ausdrückliche Bestätigung des Nutzers darf nichts überschrieben werden und der Vorgang wird abgebrochen.
6. Auf Basis des eingelesenen Skill-Prompts eine vollständige Skill-Definition formulieren, die derselben Struktur und demselben Detailgrad folgt wie bestehende SKILL.md-Dateien im Repository (z. B. 01-prompt-generator-fuer-skills/SKILL.md).
7. Im Ordner .github/skills einen neuen Unterordner mit dem abgeleiteten Skill-Namen anlegen (bzw. bei bestätigter Überschreibung den bestehenden Ordner verwenden).
8. In diesem Unterordner eine Datei mit dem festen Namen "SKILL.md" erstellen bzw. bei bestätigter Überschreibung ersetzen.
9. In dieser Datei die vollständige Skill-Definition aus Schritt 6 hinterlegen, sodass der Skill-Prompt vollständig in einen konkreten, nutzbaren Skill überführt wurde.
10. Keine Inhalte ergänzen, die nicht im Skill-Prompt enthalten oder daraus unmittelbar ableitbar sind.
11. Nach der Erstellung eine kurze Ergebnisübersicht liefern (verwendeter Skill-Prompt, erzeugter Skill-Ordner, erzeugte Datei).

Eingaben:
- Der Ordner .github/prompts mit allen Dateien, die mit "skill-prompt-" beginnen
- Optional: eine konkrete Angabe des Nutzers, welcher Skill-Prompt verwendet werden soll
- Die bestehenden SKILL.md-Dateien in .github/skills als Struktur- und Qualitätsreferenz

Ausgabe:
- Ein neuer Ordner unter .github/skills mit dem aus dem Skill-Prompt abgeleiteten Namen
- Darin eine Datei SKILL.md mit der vollständigen, aus dem Skill-Prompt abgeleiteten Skill-Definition
- Eine kurze Ergebnisübersicht: verwendeter Skill-Prompt, Name und Pfad des neuen Skill-Ordners, Pfad der erzeugten SKILL.md

Regeln:
- Keine Erfindungen
- Keine Annahmen ohne Kennzeichnung als [ANNAHME]
- Fehlende oder unklare Angaben im Skill-Prompt als [OFFEN] kennzeichnen
- Nur Inhalte verwenden, die im gewählten Skill-Prompt tatsächlich enthalten sind
- Es darf immer nur ein Skill-Prompt je Durchlauf in einen Skill überführt werden, sofern der Nutzer nichts anderes angibt
- Existieren mehrere passende skill-prompt-*.md Dateien, muss immer beim Nutzer nachgefragt werden, welche verwendet werden soll (keine automatische Auswahl, auch nicht bei vermeintlich eindeutigem Bezug)
- Der neue Skill-Ordner wird immer unter .github/skills angelegt
- Die Skill-Datei heißt immer exakt "SKILL.md"
- Der Ordnername des neuen Skills entspricht dem Namen aus dem Dateinamen des Skill-Prompts (ohne Präfix "skill-prompt-" und ohne Dateiendung)
- Bestehende Skill-Ordner oder SKILL.md-Dateien dürfen niemals ohne vorherige ausdrückliche Rückfrage und Bestätigung des Nutzers überschrieben werden; ohne Bestätigung wird der Vorgang abgebrochen
- Deutsche Sprache als Standard, sofern der Skill-Prompt nichts anderes vorgibt
- Der erzeugte Skill muss eigenständig nutzbar sein, ohne dass der ursprüngliche Skill-Prompt noch vorliegen muss

Ausgabestruktur der erzeugten SKILL.md:
- # Skill: [Name des neuen Skills]
- ## Zweck
- ## Ziel
- ## Standardstruktur / Verarbeitungsschritte
- ## Entscheidungslogik (falls im Skill-Prompt enthalten)
- ## Regeln
- ## Rückfragen (falls im Skill-Prompt enthalten)
- ## Ausgabestruktur / Output-Contract
- ## Qualitätsprüfung
- ## Verhalten des Skills
- ## Endergebnis

Qualitätsprüfung:
- Der gewählte Skill-Prompt wurde vollständig ausgewertet
- Alle wesentlichen Abschnitte des Skill-Prompts (Ziel, Aufgabe, Regeln, Ausgabe, Qualitätskriterien) sind in der SKILL.md wiederzufinden
- Der Ordnername und der Dateiname entsprechen exakt der Namenskonvention
- Es wurden keine Inhalte erfunden oder ergänzt, die nicht aus dem Skill-Prompt stammen
- Die Struktur der SKILL.md entspricht bestehenden SKILL.md-Dateien im Repository
- Bestehende Skills wurden nicht ungewollt überschrieben

Beispiel:
- Beispiel-Input: Skill-Prompt-Datei .github/prompts/skill-prompt-splitter-fuer-prompts.md
- Beispiel-Output: Ordner .github/skills/splitter-fuer-prompts/ mit der Datei SKILL.md, deren Inhalt die aus dem Skill-Prompt abgeleitete vollständige Skill-Definition ist

Verwendungszweck:
Dieser Skill wird immer dann eingesetzt, wenn ein bereits erzeugter Skill-Prompt aus .github/prompts in einen tatsächlich nutzbaren, im Repository abgelegten Skill überführt werden soll. Er bildet damit den letzten Schritt der Skill-Erstellungskette nach den Skills 01-prompt-generator-fuer-skills und skill-prompt-splitter-fuer-prompts.

Output-Contract:
- Speicherort des neuen Skills: .github/skills/[Name-des-neuen-Skills]/
- Dateiname der Skill-Datei: SKILL.md
- Keine Vorbemerkungen oder Meta-Kommentare in der SKILL.md selbst
- Nur die finale Skill-Definition als Inhalt der SKILL.md
- Zusätzlich außerhalb der Datei: kurze Ergebnisübersicht über den erzeugten Skill

Qualitätsprüfung vor der Ausgabe:
- Wurde der korrekte Skill-Prompt identifiziert?
- Ist der abgeleitete Skill-Name korrekt und eindeutig?
- Enthält die SKILL.md alle wesentlichen Inhalte des Skill-Prompts?
- Wurden keine Inhalte erfunden oder ausgelassen?
- Wurde ein bestehender Skill-Ordner versehentlich überschrieben?
- Ist die Struktur konsistent zu bestehenden SKILL.md-Dateien?

Verhalten des Skills:
Der Skill soll:
- immer zuerst prüfen, welche skill-prompt-*.md Dateien in .github/prompts vorliegen
- bei mehreren passenden Dateien immer nachfragen, welcher Skill-Prompt verwendet werden soll, bevor irgendeine weitere Aktion erfolgt
- vor dem Anlegen prüfen, ob bereits ein gleichnamiger Skill-Ordner bzw. eine SKILL.md existiert, und in diesem Fall immer erst nachfragen, ob überschrieben werden darf
- den Inhalt des gewählten Skill-Prompts vollständig und unverändert in seiner Aussage übernehmen
- daraus eine strukturierte, eigenständige Skill-Definition erzeugen
- den neuen Skill korrekt benannt und an der richtigen Stelle ablegen
- keine eigene fachliche Interpretation über den Skill-Prompt hinaus vornehmen

Endergebnis:
Dieser Skill liefert immer einen vollständigen, direkt nutzbaren neuen Skill-Ordner unter .github/skills mit einer darin enthaltenen SKILL.md, deren Inhalt die vollständige, aus dem jeweiligen Skill-Prompt abgeleitete Skill-Definition ist.

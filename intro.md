# TODO

- Beispielhafter Aufbau eines Thesaurus
- Was ist SKOS -> Übung dazu?
- Wie lassen sich Thesauri etc in Dokumentationssysteme einbinden
- RDF-Einführung
- Linked Data

- Mapping-Tabelle mithilfe von SKOS anlegen
- Wie sieht das konkret in den verschiedenen Softwares aus?
- Unterscheidung zwischen den Thes., Ontol, Taxon etc.

- Vertiefung Nutzung Wikidata

- Erstellung eines eigenen Vokabulars: Grundsätzliche Überlegungen, praktische Umsetzung

# Einführung in kontrollierte Vokabulare

Kontrollierte Vokabulare stellen eine kuratierte Sammlung standardisierter Begriffe und Konzepte dar.
Sie reduzieren damit die potenzielle Vielzahl natürlichsprachlicher Beschreibung einer Resource (eines Dings).
Diese Standardisierung dient der besseren Auffindbarkeit von Objekten (Retrieval) und erleichtert die automatische oder halbautomatische Analyse von Datensammlungen.


Es gibt verschiedene Arten kontrollierter Vokabulare oder Wissensorganisationssysteme (*KOS*, von engl. Knowledge Organisation Systems)), die zunächst begrifflich differenziert werden sollen {cite}`kellerDigitalisierungPhilosophischenZettelkastens2014`).

## Glossar, Schlagwortliste

Unter Schlagwörtern versteht man Begriffe, die eine Eigenschaft eines Objekts beschreiben.
Werden Schlagwörter standardisiert, liegt bereits eine basale, aber doch sehr wichtige Form eines kontrollierten Vokabulars vor.
Eine potenzielle Vielzahl von Begriffen wird auf eine bestimmte Menge begrenzt.
Hierdurch entsteht (womöglich auf Kosten der Präzision) Einheitlichkeit, die wiederum die Auffindbarkeit und Nachnutzbarkeit erhöht.

Schlagwörter in Glossaren können mit – idealerweie 'opaken' – Identifikatoren versehen und somit eindeutig adressierbar gemacht werden.
Es können zu den Schlagwörtern alternative Bezeichnungen, Übersetzungen und Hinweise hinzugefügt werden.

Ein Beispiel für ein Glossar ist die GND.


## Taxonomie

Eine Taxonomie ist eine streng hierarchische Klassifikation.
Eine Wissensdomäne wird dabei in disjunkte Klassen aufgeteilt und jeder Resource wird dabei genau ein bestimmter Platz zugewiesen.

So lassnen sich z.B. Plastiken nach ihrem Material in Holz- und Marmorskulpturen unterscheiden und dann weiter nach Sujet etc.
Auf diese Weise entsteht eine sich immer weiter ausdifferenzierende Kaskade an Klassen von Objekten, die bestimmte Eigenschaften gemein haben.

Die einzige in einer Taxonomie abbildbare Relation ist die der Über- bzw. Unterordnung (z.B. ist die Malerei eine Unterart der Bildenden Künste)

## Thesaurus

Ein Thesaurus verzeichnet Begriffe in Relation zu anderen Begriffen.
Mögliche Relationen sind:

- Ober- und Unterbegriff
- Ähnlichkeit/Gegensätzlichkeit (Synomom/Antonym)
- Teil-Ganzes (Meronymie)
- Äquivokation (Homonymie/Polysemie)

Ein Thesaurus kann äquivalente Begriffe oder Begriffe in verschiedenen Sprachen zusammenfassen.
Bevorzugte Begriffe können als solche hervorgehhoben werden.

## Ontologien

Eine Ontologie bildet die Komplexität eines Wissensbereichs möglichst umfassend ab.
Sie bietet also im Vergleich zum Thesaurus die Möglichkeit, Relationen zwischen Objekten beliebig kompex zu modellieren.
8
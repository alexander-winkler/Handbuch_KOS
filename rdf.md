# Kurzeinfürung RDF

## Allgemeines 

RDF (Resource Description Framework) ist ein sehr allgemeiner Standard zur Beschreibung beliebiger Ressourcen und ist einer der wesentlichen Bausteine des Semantic Web.

Im RDF werden Aussagen in Form von sog. Tripeln gemacht, d.h. Reihen von Subjekt, Prädikat und Objekt.

Bsp.:

Van Gogh -> ist Urheber von -> Gemälde Sternennacht .
(Subjekt)   (Prädikat)         (Objekt)             .

Subjekt und Prädikat müssen mit einem IRI idenfiziert werden, das Objekt kann entweder durch einen IRI oder einen Literal realisiert sein.

## Turtle-Format

Eine relativ bequem lesbare und weit verbreitete Darstellungsform ("Serialisierung") von RDF ist das sog. Turtle-Format.
Im Turtle-Format steht je ein Triple in einer Zeile.
Ein Triple wird durch einen Punkt beendet.

Z.B.:

```
<http://vocab.getty.edu/ulan/500115588> <http://www.w3.org/2000/01/rdf-schema#label> "Gogh, Vincent van" .
```

Die Ressource mit der IRI `http://vocab.getty.edu/ulan/500115588` hat als Label (das steckt hinter dem Prädikat `http://www.w3.org/2000/01/rdf-schema#label`) das Litteral "Gogh, Vincent van". 

### Sprach-Tags

Ein Litteral kann mit einem Sprach-Tag versehen werden.
Hier wird das ISO 639-Kürzel mit dem "@"-Zeichen an den String angefügt.

```
<http://vocab.getty.edu/ulan/500115588> <http://www.w3.org/2000/01/rdf-schema#label> "Gogh, Vincent van"@en .
```

### Angabe der Datentypen

Um die Maschinenlesbarkeit eines Litteral-Objekts zu steigern oder Missverständnisse zu vermeiden, kann der Datentyp eines Litteral angegeben werden.
Dies geschieht mit einem "Doppeldach" (`^^`) hinter den String sowie einer Formatbeschreibung.
Auch diese ist standardisiert.

Um also anzugeben, dass eine bestimmt Resource zu einem bestimmten Zeitpunkt modifiziert wurde, lässt sich schreiben:

```
<http://vocab.getty.edu/ulan/500115588> <http://purl.org/dc/terms/modified> "2003-01-02T11:14:40"^^<http://www.w3.org/2001/XMLSchema#dateTime>
```

### Kurzschreibweisen

Turtle bietet einige Kurzschreibweisen an:

Werden mehrere Aussagen zum selben Subjekt getroffen, gibt es die Möglichkeit, die Statements per Semikolon (;) zu trennen und auf die wiederholte Nennung des Subjekts zu verzichten.

Schematisch:

Statt:

S P1 O1 .
S P2 O2 .


S P1 O1 ;
  P1 O2 .

Einem Subjekt können über ein Prädikat mehrere Objekte zuwiesen werden.
Diese weden durch Komma getrennt.

S P O1, O2, O3, O4 .

Eine häufig anzutreffende, recht technische Kurzschreibweise zum Schluss:
In RDF-Tripeln wird oft der `type` einer Resource spezifiziert.
Hierfür kann `<http://www.w3.org/1999/02/22-rdf-syntax-ns#type>` verwendet werden.
Es wurde jedoch für diesen häufigen Fall festgelegt, dass statt `<http://www.w3.org/1999/02/22-rdf-syntax-ns#type>` schlicht `a` verwendet werden kann.

```
<http://vocab.getty.edu/ulan/500115588> a <http://www.w3.org/2004/02/skos/core#Concept> .
```

ist also identisch mit 

```
<http://vocab.getty.edu/ulan/500115588> <http://www.w3.org/1999/02/22-rdf-syntax-ns#type> <http://www.w3.org/2004/02/skos/core#Concept> .
```

### Namensräume

Jede Resource wird über den IRI eindeutig identifiziert.
Um diese Eindeutigkeit zu garantieren, reicht es nicht aus, einen einfachen String (z.B. `time`, `concept`, `creator`), da diese Strings mitunter in verschiedenen Vokabularen verwendet und somit nicht mehr unterscheidbar wären.
Man behilft sich also durch die Hinzufügung eines desambiguierenden Namensraums, der *per definitionem* die Form einer URL hat und im Idealfall auch zu einer entsprechenden Online-Resource mit weiteren Informationen führt.
Der Vorteil dieses Verfahrens liegt darin, dass diejenige Instanz, die den String definiert, im besten Falle auch Kontrolle über die verwendete URL hat.
Hierdurch ist in der Praxis gesichert, dass jede IRI eindeutig ist.

Die Beispiele oben stammen aus dem ULAN von Getty.
Die Einzelnen Resourcen sind mit IRIs bezeichnet.
Hierdurch wird die Darstellung sehr verbos und unübersichtlich.

Es besteht (auch) im Turle-Format die Möglichkeit, für Namespaces Abkürzungen zu definieren.
Unter Verwendung von Namespaces kann das letzte Beispiel oben auch folgendermaßen dargestellt werden:

```
@prefix ulan : http://vocab.getty.edu/ulan/
@prefix rdf : http://www.w3.org/1999/02/22-rdf-syntax-ns#
@prefix skos: http://www.w3.org/2004/02/skos/core#


ulan:500115588 rdf:type skos:Concept .
```
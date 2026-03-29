# Automatisierte Standortsuche für Freiflächen-PV

## Warum die Suche nach PV-Flächen so wichtig und doch so schwierig ist


<div style='text-align: justify;'>
  Nicht jede sonnige Fläche ist automatisch ein guter PV-Standort. Zwischen Schutzgebieten, Hochwassergefahr, Bodengüte und Infrastrukturanbindung wird schnell deutlich, dass die Standortsuche eine komplexe planerische Abwägung erfordert. Umso sinnvoller wäre es, wenn nicht jede Kommune dafür eigene methodische Ansätze entwickeln müsste. Gegen-wärtig ist dies jedoch häufig noch der Fall. Ziel unseres Projekts ist es deshalb, diese frag-mentierte Vorgehensweise zu überwinden und eine übertragbare und automatisierte Metho-dik für die Planung von PV-Freiflächenanlagen (PV-FFA) zu entwickeln.
</div>

<div style='text-align: justify;'>
Denn der Ausbau der Photovoltaik ist ein zentraler Baustein der Energiewende in Deutsch-land. Ende 2025 waren bundesweit rund 117 GW PV-Leistung installiert; im Jahr 2025 wur-den ca. 74 TWh Strom und damit etwa 17 % der inländischen Stromproduktion durch Photo-voltaik erzeugt (BNETZA 2026a, 2026b). Gleichzeitig sieht das EEG bis 2030 ein Ausbau-ziel von 215 GW vor, sodass in den kommenden Jahren ein weiterer deutlicher Ausbau not-wendig ist (UBA 2023). 
</div>

<div style='text-align: justify;'>
Zugleich werden PV-Module zunehmend effizienter und günstiger. Während im Jahr 2006 noch 4 ha pro MW installierter Leistung benötigt wurden, lag dieser Wert 2024 bereits bei unter 1 ha/MW (UBA 2025). Damit wird es auch für die Kommunen zunehmend attraktiver, Bauflächen für PV-FFA zu schaffen.
</div>

<div style='text-align: justify;'>
Mit dem Ausbau steigt jedoch auch die Bedeutung einer gezielten räumlichen Steuerung. Ende 2024 waren in Deutschland bereits etwa 45.000 ha mit PV-FFA belegt, davon rund 15.200 ha auf Ackerflächen. Trotz eines Flächenanteils am Bundesgebiet von nur etwa 0,1 % zeigt sich, dass der Ausbau nicht konfliktfrei ist, da landwirtschaftliche Nutzung, Energie-produktion, Naturschutz und planerische Vorgaben miteinander konkurrieren (UBA 2025).
Entsprechend wächst der Bedarf an einem Tool, mit dem Kommunen durch die Eingabe ih-res Gemeindenamens und gegebenenfalls ergänzt um eigene Anforderungen geeignete land-wirtschaftliche Flächen für Freiflächen-PV identifizieren können. Eine GIS-gestützte Analy-se eignet sich hierfür besonders, da sie datenbasiert, reproduzierbar und entsprechend trans-parent bei Planungs- und Entscheidungsprozessen unterstützen kann.
</div>

> **Ziel des Projekts:** Entwicklung eines GIS-basierten Workflows, mit dem geeignete landwirtschaftliche Schläge für Freiflächen-Photovoltaikanlagen automatisiert identifiziert werden können. Dafür werden relevante räumliche Kriterien zusammengeführt und so ausgewertet, dass potenziell geeignete Flächen nachvollziehbar ausgegeben werden.
> **Untersuchungsgebiet:** Viele rechtliche Vorgaben zur Errichtung von PV-FFA sind föderal strukturiert und damit in weiten Teilen Ländersache. Das Projekt wird daher exemplarisch für das Land Niedersach-sen durchgeführt.

## Method

### Vom Geodatensatz zur Eignungsbewertung

<div style='text-align: justify;'>
 Am Anfang stellt sich die Frage, wie sich aus vielen einzelnen Geodaten am Ende eine nachvollziehbare PV-Eignungsbewertung für landwirtschaftliche Flächen ableiten lässt. Denn erst im Zusammenspiel verschiedener Informationen wird sichtbar, welche Flächen grundsätzlich infrage kommen und welche aufgrund bestimmter Rahmenbedingungen ausgeschlossen oder schlechter bewertet werden sollten. Um diese Einflussfaktoren systematisch zusammenzuführen, haben wir mit einer <strong>Multikriterienanalyse (MCDA)</strong> gearbeitet.Zur Bewertung wurden zwei Arten von Kriterien abgeleitet.
</div>

<div style='text-align: justify;'>
 Um diese unterschiedlichen Einflussfaktoren systematisch zusammenzuführen, haben wir mit einer  gearbeitet. Dieser Ansatz eignet sich besonders dann, wenn mehrere räumliche Kriterien gleichzeitig berücksichtigt und zu einer gemeinsamen Bewertung zusammengeführt werden sollen.
</div>

<div style='text-align: justify;'>
  Dafür wurden unterschiedliche räumliche Datensätze zusammengeführt, darunter landwirtschaftliche Schläge, Schutzgebiete, Hochwasserflächen, Siedlungsnähe, Verkehrsinfrastruktur und Bodengüte. Diese Informationen wurden so aufbereitet, dass sie räumlich vergleichbar und gemeinsam auswertbar sind.
</div>

#### 1. Harte Ausschlusskriterien

<div style='text-align: justify;'>
Zunächst kommen harte Ausschlusskriterien zum Einsatz: Sie filtern alle Flächen heraus, die für Freiflächen-PV rechtlich, ökologisch oder praktisch nicht infrage kommen. Diese sind in der Abbildung aufgezählt. Unter Schutzgebiete fallen jegliche naturschutzrechtlichen Fläche wie bspw. Naturschutzgebiete, Vogelschutzgebiete und Natura 2000-Gebiete. Da die Pachtung bzw. der Erwerb eines Schlags mit einem bürokratischen Aufwand verbunden ist, werden außerdem nur landwirtschaftliche Schläge mit mindestens einem Hektar Fläche berücksichtigt.
</div>

![Das ist das erste Bild](https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Bild2.jpg "Das ist ein Bild")
*Abbildung 1: Rasterbasierte Eignungsbewertung der Flächen. (schematische Darstellung)*

---

Übrig bleiben die landwirtschaftlichen Flächen, die grundsätzlich bebaut werden könnten.



#### 2. Weiche Bewertungskriterien

Diese Flächen werden anschließend anhand weicher Kriterien weiter differenziert bewertet. Bevorzugt werden Standorte:

- mit geringer Hangneigung,
- in der Nähe von Straßen,
- in der Nähe von Bahntrassen,
- nahe an Ortslagen,
- nahe an Strominfrastruktur.

Das kann den Erschließungsaufwand reduzieren und hilft zugleich, eher an bereits vorgeprägte Räume anzuschließen, statt neue Landschaftsbereiche zusätzlich zu beanspruchen. Auch die Bodengüte spielt eine Rolle: Flächen mit geringerer Ertragsfähigkeit sind günstiger zu bewerten als besonders fruchtbare Böden. Hinzu kommt das **Solarpotenzial**, das als zentrales Kriterium am stärksten gewichtet wird.

#### 3. Rasterbasierte Gesamtbewertung

Die eigentliche Bewertung erfolgte rasterbasiert. Ein Raster kann man sich dabei wie ein Schachbrettmuster vorstellen: Die Untersuchungsfläche wird in viele kleine, gleich große quadratische Felder unterteilt, und jedes dieser Felder erhält für die jeweiligen Kriterien einen Wert.

Für jede Rasterzelle wurde aus mehreren Kriterienlayern ausgelesen, wie gut oder schlecht sie in den einzelnen Kriterien abschneidet. Diese Einzelbewertungen wurden anschließend im Rahmen der MCDA zu einer Gesamtbewertung zusammengeführt. So entsteht aus mehreren thematischen Karten eine flächendeckende Eignungskarte.

**Abbildung X:** Von Einzelkriterien zur Gesamtbewertung: rasterbasierte Multikriterienanalyse (MCDA) durch die Überlagerung mehrerer Kriterienlayer.

#### 4. Aggregation auf Schlagebene

Da für die Planung nicht das einzelne Pixel, sondern der landwirtschaftliche Schlag entscheidend ist, wurden die rasterbasierten Ergebnisse im letzten Schritt auf Schlagebene aggregiert. Dadurch erhält jeder Schlag eine zusammenfassende Eignungsbewertung, die als planerisch nutzbare Grundlage dient.

#### 5. Abschätzung des Energieertrags

Für die am besten bewerteten Schläge wird abschließend eine Abschätzung des potenziellen Energieertrags vorgenommen. Dadurch wird nicht nur sichtbar, welche Flächen grundsätzlich geeignet sind, sondern auch, wie viel Energie dort näherungsweise im Jahr erzeugt werden könnte.

#### 6. Automatisierter Workflow

Der gesamte Workflow ist skriptbasiert in Python umgesetzt und dadurch vollständig automatisiert. Ein besonderer Vorteil besteht darin, dass bereits die Änderung des Gemeindenamens ausreicht, um Datenbeschaffung und Analyse für eine andere Gemeinde in Niedersachsen erneut durchlaufen zu lassen.

Mit Ausnahme der Standorte von Umspannwerken und der Hochwasserschutzgebiete HQ100 werden alle benötigten Daten über Schnittstellen (APIs) vom Landesamt für Geoinformation und Landesvermessung Niedersachsen (LGLN) bezogen. Dabei erkennt das Programm, welche Gemeinde untersucht wird, und zieht die entsprechend benötigten Daten automatisch.

Die Standorte der Umspannwerke werden über die Overpass API abgefragt. Für die HQ100-Hochwassergebiete steht hingegen keine moderne API-Schnittstelle zur Verfügung. Diese Daten werden daher lokal auf einem Server vorgehalten und vom Programm automatisch für das jeweilige Untersuchungsgebiet zugeschnitten.


---

## Results

Um die Ergebnisse greifbar zu machen, veranschaulichen wir den Workflow exemplarisch an einer Beispielsgemeinde in Niedersachsen. So lässt sich Schritt für Schritt zeigen, wie aus vielen einzelnen Geodaten am Ende eine nachvollziehbare Eignungsbewertung für landwirtschaftliche Flächen entsteht.

### 1. Eignungsbewertung auf Pixelebene

Die erste Karte zeigt die flächendeckende Eignungsbewertung auf Pixelebene.

Dabei wird sichtbar, dass sich geeignete und weniger geeignete Bereiche nicht gleichmäßig über den Raum verteilen, sondern kleinräumig stark unterscheiden. Besonders gut bewertete Bereiche liegen dort, wo mehrere günstige Faktoren zusammenkommen – etwa ein hohes Solarpotenzial, geringe Hangneigung und die Nähe zu bestehender Infrastruktur. Gleichzeitig zeichnen sich auch Bereiche ab, die trotz landwirtschaftlicher Nutzung aufgrund ungünstiger Rahmenbedingungen schlechter abschneiden.




<img src="https://github.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/blob/main/images/karte.jpg?raw=true" title="Das müsste beim drübergehen kommen." alt="Dies ist beschreibung" width="480">
*Abbildung 3: Karte mit html.*


### 2. Einfluss einzelner Kriterien

Anschließend macht eine Karte zu einem einzelnen Kriterium sichtbar, wie stark bereits ein einzelner Standortfaktor die spätere Gesamtbewertung beeinflussen kann. Dadurch wird deutlich, dass die Analyse keine Black Box ist: Die räumlichen Muster der Endbewertung lassen sich aus den zugrunde liegenden Kriterien gut nachvollziehen.

### 3. Aggregation auf Schlagebene

Besonders relevant für die Praxis ist dann die Aggregation auf Schlagebene. Statt vieler kleiner Rasterzellen werden die Ergebnisse pro landwirtschaftlichem Schlag zusammengefasst. Dadurch entsteht eine deutlich besser lesbare Karte, aus der unmittelbar hervorgeht, welche Schläge innerhalb der Beispielsgemeinde insgesamt besonders gut geeignet sind. Die Bewertung wird damit von einer technischen Rasteranalyse in eine Form übersetzt, die für planerische Entscheidungen tatsächlich nutzbar ist.

### 4. Die fünf bestbewerteten Flächen

Darauf aufbauend zeigt eine weitere Karte die fünf am besten bewerteten Flächen. Diese Auswahl macht die Ergebnisse noch konkreter, weil sie den Schritt von der allgemeinen Eignungsbewertung hin zu einer priorisierten Flächenkulisse vollzieht. So wird unmittelbar sichtbar, welche Standorte sich innerhalb der Beispielsgemeinde besonders für eine vertiefte planerische Prüfung eignen.

### 5. Abschätzung des Energieertrags

Für diese bestbewerteten Flächen wird abschließend noch der potenzielle Energieertrag abgeschätzt. Damit zeigt die Analyse nicht nur, welche Flächen grundsätzlich geeignet sind, sondern auch, auf welchen Standorten besonders hohe Stromerträge zu erwarten wären.

### Einordnung der Ergebnisse

Insgesamt zeigt die Beispielsgemeinde, dass sich die Standortsuche für Freiflächen-PV mit dem entwickelten Workflow deutlich systematischer und nachvollziehbarer gestalten lässt. Die Kombination aus Ausschlusskriterien, abgestufter Bewertung und Aggregation auf Schlagebene macht räumliche Unterschiede sichtbar und erlaubt es, besonders geeignete landwirtschaftliche Schläge gezielt zu priorisieren.

Damit liefert der Ansatz genau das, worauf das Projekt abzielt: eine transparente und übertragbare Grundlage, um potenzielle Standorte für Freiflächen-PV datenbasiert zu identifizieren.

---

## Conclusion

Unser Projekt zeigt, dass sich die Suche nach geeigneten landwirtschaftlichen Flächen für Freiflächen-PV deutlich systematischer gestalten lässt als durch rein manuelle Einzelfallanalysen. Durch die Kombination aus Ausschlusskriterien, abgestufter Bewertung und Aggregation auf Schlagebene entsteht ein transparenter und reproduzierbarer Workflow, der nachvollziehbar macht, warum bestimmte Flächen besser geeignet sind als andere.

Besonders gelernt haben wir, wie wichtig die saubere Zusammenführung unterschiedlicher Geodaten und eine klare Trennung zwischen harten und weichen Kriterien für eine belastbare Bewertung sind. Gleichzeitig hat sich gezeigt, dass ein skriptbasierter Ansatz große Vorteile bietet: Der Workflow ist grundsätzlich auf andere Gemeinden übertragbar, und Kriterien sowie Gewichtungen lassen sich flexibel anpassen.

Trotzdem gibt es auch Grenzen. Datenqualität und Datenverfügbarkeit können regional variieren, und bisher bieten nur sehr wenige Bundesländer passende API-Schnittstellen für ihre Daten an. Außerdem sind Gewichtungen nie völlig neutral, und eine automatisierte Analyse kann die lokale Detailprüfung vor Ort nicht vollständig ersetzen. Der Workflow liefert also keine fertige Planungsentscheidung, sondern eine fundierte Grundlage für weitere Prüfungen.

Für die nächsten Schritte gibt es mehrere Erweiterungsmöglichkeiten. So könnte das Solarpotenzial künftig noch stärker an die Umgebung angepasst werden, etwa durch einen differenzierten „Smog-Faktor“ oder zusätzliche Informationen zur Wolkenbildung. Auch weitere Kriterien, etwa Moorflächen mit Wiedervernässungspotenzial, könnten integriert werden. Darüber hinaus bietet der Ansatz Potenzial, um künftig auch Fragestellungen rund um Agri-PV in den Workflow einzubeziehen.



# *Literature*
Umweltbundesamt. (2023). Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz
UMWELTBUNDESAMT (UBA) (2023): Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz (24.03.2026).
BUNDESNETZAGENTUR (2026a): Ausbau erneuerbarer Energien 2025. https://www.bundesnetzagentur.de/SharedDocs/Pressemitteilungen/DE/2026/20260108_EEG.html (24.03.2026).
BUNDESNETZAGENTUR (2026b): Bundesnetzagentur ver­öf­fent­licht Da­ten zum Strom­markt 2025. https://www.bundesnetzagentur.de/1087156 (24.03.2026).
UMWELTBUNDESAMT (UBA) (2023): Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz (24.03.2026).
UMWELTBUNDESAMT (UBA) (2025): Photovoltaik-Freiflächenanlagen. https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/photovoltaik/photovoltaik-freiflaechenanlagen (24.03.2026).

# Automatisierte Standortsuche für Freiflächen-PV

## Warum die Suche nach PV-Flächen so wichtig und doch so schwierig ist

<div align="justify">
  Nicht jede sonnige Fläche ist automatisch ein guter PV-Standort. Zwischen Schutzgebieten, Hochwassergefahr, Bodengüte und Infrastrukturanbindung wird schnell deutlich, dass die Standortsuche eine komplexe planerische Abwägung erfordert. Umso sinnvoller wäre es, wenn nicht jede Kommune dafür eigene methodische Ansätze entwickeln müsste. Gegenwärtig ist dies jedoch häufig noch der Fall. 
  
  Ziel unseres Projekts ist es deshalb, diese fragmentierte Vorgehensweise zu überwinden und eine übertragbare und automatisierte Methodik für die Planung von PV-Freiflächenanlagen (PV-FFA) zu entwickeln.
</div>

<div align="justify">
<p>Denn der Ausbau der Photovoltaik ist ein zentraler Baustein der Energiewende in Deutschland. Ende 2025 waren bundesweit rund 117 GW PV-Leistung installiert; im Jahr 2025 wurden ca. 74 TWh Strom und damit etwa 17 % der inländischen Stromproduktion durch Photovoltaik erzeugt (BNETZA 2026a, 2026b). 
Gleichzeitig sieht das EEG bis 2030 ein Ausbauziel von 215 GW vor, sodass in den kommenden Jahren ein weiterer deutlicher Ausbau notwendig ist (UBA 2023).
Zugleich werden PV-Module zunehmend effizienter und günstiger. Während im Jahr 2006 noch 4 ha pro MW installierter Leistung benötigt wurden, lag dieser Wert 2024 bereits bei unter 1 ha/MW (UBA 2025).   
  Damit wird es auch für die Kommunen zunehmend attraktiver, Bauflächen für PV-FFA zu schaffen. </p>
</div>

<div align="justify">
  Mit dem Ausbau steigt jedoch auch die Bedeutung einer gezielten räumlichen Steuerung. Ende 2024 waren in Deutschland bereits etwa 45.000 ha mit PV-FFA belegt, davon rund 15.200 ha auf Ackerflächen. Trotz eines Flächenanteils am Bundesgebiet von nur etwa 0,1 % zeigt sich, dass der Ausbau nicht konfliktfrei ist, da landwirtschaftliche Nutzung, Energieproduktion, Naturschutz und planerische Vorgaben miteinander konkurrieren (UBA 2025).

Entsprechend wächst der Bedarf an einem Tool, mit dem Kommunen durch die Eingabe ihres Gemeindenamens und gegebenenfalls ergänzt um eigene Anforderungen geeignete landwirtschaftliche Flächen für Freiflächen-PV identifizieren können. Eine GIS-gestützte Analyse eignet sich hierfür besonders, da sie datenbasiert, reproduzierbar und entsprechend transparent bei Planungs- und Entscheidungsprozessen unterstützen kann.
> **Ziel des Projekts:** Entwicklung eines GIS-basierten Workflows, mit dem geeignete landwirtschaftliche Schläge für Freiflächen-Photovoltaikanlagen automatisiert identifiziert werden können. Dafür werden relevante räumliche Kriterien zusammengeführt und so ausgewertet, dass potenziell geeignete Flächen nachvollziehbar ausgegeben werden.

> **Untersuchungsgebiet:** Viele rechtliche Vorgaben zur Errichtung von PV-FFA sind föderal strukturiert und damit in weiten Teilen Ländersache. Das Projekt wird daher exemplarisch für das Land Niedersachsen durchgeführt.</div>

---

## Method

### Vom Geodatensatz zur Eignungsbewertung

<div align="justify">
 Am Anfang stellt sich die Frage, wie sich aus vielen einzelnen Geodaten am Ende eine nachvollziehbare PV-Eignungsbewertung für landwirtschaftliche Flächen ableiten lässt. Denn erst im Zusammenspiel verschiedener Informationen wird sichtbar, welche Flächen grundsätzlich infrage kommen und welche aufgrund bestimmter Rahmenbedingungen ausgeschlossen oder schlechter bewertet werden sollten. Um diese Einflussfaktoren systematisch zusammenzuführen, haben wir mit einer <strong>Multikriterienanalyse (MCDA)</strong> gearbeitet.

Zur Bewertung wurden zwei Arten von Kriterien abgeleitet.
</div>

<div align="justify">
 Um diese unterschiedlichen Einflussfaktoren systematisch zusammenzuführen, haben wir mit einer  gearbeitet. Dieser Ansatz eignet sich besonders dann, wenn mehrere räumliche Kriterien gleichzeitig berücksichtigt und zu einer gemeinsamen Bewertung zusammengeführt werden sollen.
</div>

<div align="justify">
  Dafür wurden unterschiedliche räumliche Datensätze zusammengeführt, darunter landwirtschaftliche Schläge, Schutzgebiete, Hochwasserflächen, Siedlungsnähe, Verkehrsinfrastruktur und Bodengüte. Diese Informationen wurden so aufbereitet, dass sie räumlich vergleichbar und gemeinsam auswertbar sind.
</div>

#### 1. Harte Ausschlusskriterien

<div align="justify">
<p>Zunächst kommen harte Ausschlusskriterien zum Einsatz: Sie filtern alle Flächen heraus, die für Freiflächen-PV rechtlich, ökologisch oder praktisch nicht infrage kommen. Diese sind in der Abbildung aufgezählt. Unter Schutzgebiete fallen jegliche naturschutzrechtlichen Fläche wie bspw. Naturschutzgebiete, Vogelschutzgebiete und Natura 2000-Gebiete. Da die Pachtung bzw. der Erwerb eines Schlags mit einem bürokratischen Aufwand verbunden ist, werden außerdem nur landwirtschaftliche Schläge mit mindestens einem Hektar Fläche berücksichtigt.</p>

Übrig bleiben die landwirtschaftlichen Flächen, die grundsätzlich bebaut werden könnten.

</div>

![Das ist das erste Bild](https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_harte_Kriterien.png "Das ist ein Bild")
*Abbildung 1: Rasterbasierte Eignungsbewertung der Flächen. (schematische Darstellung)*



<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_harte_Kriterien.png" title="Das müsste beim drübergehen kommen. Erstes Bild." alt="Dies ist beschreibung" width="480">


<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/harte_Krit_JPEG_2.jpg" title="Das müsste beim drübergehen kommen. Erstes Bild." alt="Dies ist beschreibung" width="480">



#### 2. Weiche Bewertungskriterien

<div align="justify">

Diese verbleibenden, potenziell bebaubaren Flächen werden anschließend anhand weicher Kriterien weiter differenziert bewertet. 

Bevorzugt werden dabei Standorte:
- mit geringer Hangneigung,
- in der Nähe von Straßen, 
- in der Nähe von Bahntrassen, 
- in der Nähe von Ortslagen,
- in der Nähe von Strominfrastruktur, also Hochspannungsleitungen und Umspannwerke. 

Das reduziert den Erschließungsaufwand und nutzt bereits vorgeprägte Räume, anstatt neue Landschaftsbereiche zusätzlich zu beanspruchen. 

Die Nähe zur Strominfrastruktur ist dabei besonders wichtig, da ein Netzanschluss mit zunehmender Entfernung aufwendiger und teurer wird. Weil öffentlich zugängliche Daten zu konkreten Netzanschlusspunkten nur eingeschränkt verfügbar sind, wird dieser Aspekt neben der Nähe zu Umspannwerken näherungsweise eben auch über weitere bestehende Infrastrukturen wie Ortslagen und Bahnstrecken berücksichtigt, die auf vorhandene Strominfrastruktur schließen lassen.

Bevorzugt werden außerdem Standorte mit: 
- einer geringen Bodengüte bzw. Ertragsfähigkeit,
- einem hohen jährlichen Solarpotenzial.

Die individuellen Gewichtungen und das allgemeine Bewertungsschema werden nachfolgend abgebildet. Die Gewichtungen der Kriterien wurden im Projekt selbst festgelegt und orientieren sich an vergleichbaren Ansätzen, insbesondere an HAUGER et al. (2025).

</div>


![Das ist das erste Bild](https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_weiche_Kriterien.png "Das ist ein Bild")
*Abbildung 1: Rasterbasierte Eignungsbewertung der Flächen. (schematische Darstellung)*

**HIER NACH 1 ha nochmal gucken, also wie selektieren wir?**


#### 3. Rasterbasierte Gesamtbewertung
<div align="justify">
Die eigentliche Bewertung erfolgte rasterbasiert. Ein Raster kann man sich dabei wie ein Schachbrettmuster vorstellen: Die Untersuchungsfläche wird in viele kleine, gleich große, quadratische Felder unterteilt, und jedes Feld erhält für die jeweiligen Kriterien einen Wert zwischen 1 (sehr schlecht geeignet) und 5 (sehr gut geeignet), welcher die PV-Eignung detailliert beschreibt. Die genauen Bewertungszuordnungen finden sich im Anhang der ausführlicheren Methodik-Dokumentation. HIER DANN LINK!!!!!


**OBEN LINK!**

Die klassifizierten Raster werden anschließend vertikal „durchstochen“ und unter Berücksichtigung der Gewichtungsfaktoren miteinander gemittelt. Das Ergebnis ist ein Wert zwischen 1 und 5, der die Gesamtbewertung repräsentiert. 
</div>

![Das ist das erste Bild](https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_harte_Kriterien.png "Das ist ein Bild")
*Abbildung 1: Rasterbasierte Eignungsbewertung der Flächen. (schematische Darstellung)*

#### 4. Aggregation auf Schlagebene
<div align="justify">
Da für die Planung nicht das einzelne Pixel, sondern der landwirtschaftliche Schlag entscheidend ist, wurden die rasterbasierten Ergebnisse anschließend auf Schlagebene gemittelt.

Für die Schläge wird abschließend noch der gemittelte potenzielle jährliche Energieertrag abgeschätzt. 
</div>

#### 5. Automatisierter Workflow

<div align="justify">
Der gesamte Workflow ist skriptbasiert in Python umgesetzt und dadurch vollständig automatisiert. Bereits die Änderung des Gemeindenamens reicht aus, um Datenbeschaffung und Analyse für eine andere Gemeinde in Niedersachsen erneut durchzuführen.

Mit Ausnahme der Standorte von Umspannwerken und der HQ100-Hochwassergebiete werden alle benötigten Daten automatisiert über Schnittstellen (APIs) vom Landesamt für Geoinformation und Landesvermessung Niedersachsen bezogen (LGLN 2026). Dabei erkennt das Programm, welche Gemeinde untersucht wird und ruft die entsprechend benötigten Daten ab..

Die Umspannwerke werden über die Overpass API abgefragt. Für die HQ100-Daten steht keine moderne API-Schnittstelle zur Verfügung; sie werden daher lokal vorgehalten und automatisch passend für das jeweilige Untersuchungsgebiet zugeschnitten.
</div>


---

## Results
<div align="justify">
Um die Ergebnisse greifbar zu machen, veranschaulichen wir den Workflow exemplarisch an der Beispielsgemeinde Cuxhaven. So lässt nachvollziehen, wie aus vielen einzelnen Geodaten am Ende eine nachvollziehbare Eignungsbewertung für landwirtschaftliche Flächen entsteht.

Die erste Karte zeigt zunächst ein Beispiel eines einzelnen Kriteriums, in diesem Fall der Bodengüte. Es wird sichtbar, wie ungleichmäßig die Kriterien über den  Raum verteilt sind und entsprechend die Gesamtbewertung prägen können.  
  
<img src="https://github.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/blob/main/images/karte.jpg?raw=true" title="Das müsste beim drübergehen kommen." alt="Dies ist beschreibung" width="480">

*Abbildung 3: Karte mit html.*

Die nächste Karte veranschaulicht die Umsetzung des Abzugs der beschriebenen Negativflächen von den Positivflächen in Form der mindestens 1 ha großen landwirtschaftlichen Flächen. 

<img src="https://github.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/blob/main/images/karte.jpg?raw=true" title="Das müsste beim drübergehen kommen." alt="Dies ist beschreibung" width="480">

*Abbildung 3: Karte mit html.*


Die erste konkrete Ergebniskarte zeigt die PV-FFA-Eignung auf Pixelebene. 

Hier wird deutlich, welcher Einfluss von einzelnen Faktoren wie beispielsweise der Nähe zu Stromleitungen ausgeht und wie kleinräumig sich die Bewertung im Raum unterscheidet.


<img src="https://github.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/blob/main/images/karte.jpg?raw=true" title="Das müsste beim drübergehen kommen." alt="Dies ist beschreibung" width="480">

*Abbildung 3: Karte mit html.*


Besonders relevant für die Praxis ist dann die Aggregation auf Schlagebene. Statt vieler kleiner Rasterzellen werden die Ergebnisse pro landwirtschaftlichem Schlag zusammengefasst. Dadurch entsteht eine deutlich besser lesbare Karte, aus der unmittelbar hervorgeht, welche Schläge innerhalb der Beispielsgemeinde insgesamt besonders gut geeignet sind. Die Bewertung wird damit von einer technischen Rasteranalyse in eine Form übersetzt, die für planerische Entscheidungen tatsächlich nutzbar ist. So könnten auch größere, zusammenhängende PV-FFA-Anlagen geplant werden, welche sich nicht ausschließlich aus den bestbewerteten Flächen zusammensetzen.

Darauf aufbauend zeigt eine weitere Karte die fünf am besten bewerteten Flächen. Diese Auswahl macht die Ergebnisse noch konkreter, weil sie den Schritt von der allgemeinen Eignungsbewertung hin zu einer priorisierten Flächenkulisse vollzieht. So wird unmittelbar sichtbar, welche Standorte bspw. in einer Detailuntersuchung genauer betrachtet werden sollten.

Die letzte Karte zeigt außerdem die gemittelte Ertragsabschätzung je Feld. Damit zeigt die Analyse nicht nur, welche Flächen grundsätzlich geeignet sind, sondern auch, auf welchen Standorten besonders hohe Stromerträge zu erwarten wären.

</div>

---

## Conclusion

<div align="justify">
Insgesamt zeigen unser Projekt und die Ergebnisse der Beispielsgemeinde, dass sich die Standortsuche für Freiflächen-PV mit dem entwickelten Workflow deutlich systematischer und nachvollziehbarer gestalten lässt als durch rein manuelle Einzelfallanalysen. Durch die Kombination aus Ausschlusskriterien, abgestufter Bewertung und Aggregation auf Schlagebene entsteht ein transparenter und reproduzierbarer Ansatz, der auch für Laien nachvollziehbar macht, warum bestimmte Flächen besser geeignet sind als andere.

Besonders gelernt haben wir, dass der initiale Aufwand eines skriptbasierten Ansatzes zwar hoch ist, langfristig aber große Vorteile bietet. Der Workflow ist grundsätzlich auf andere Gemeinden übertragbar, Kriterien und Gewichtungen lassen sich flexibel anpassen, und auch eine automatische Kartengenerierung wäre problemlos möglich. Perspektivisch ließe sich das Tool weiter ausbauen, etwa durch eine eigene Bedienoberfläche oder Regler zur individuellen Gewichtung der Kriterien. Denkbar wäre sogar, unterschiedliche Vorgaben verschiedener Bundesländer direkt im Programm zu hinterlegen und den Workflow damit deutlich breiter nutzbar zu machen.

Gleichzeitig bestehen Grenzen. Datenqualität und Datenverfügbarkeit können regional stark variieren, und bislang stellen nur wenige Bundesländer ihre Daten über verlässliche API-Schnittstellen bereit. Niedersachsen gehört hier zu den wenigen Ländern, in denen dies ohne größere Workarounds möglich ist. Hinzu kommt, dass bei einzelnen Kriterien bewusst Vereinfachungen getroffen wurden, etwa bei Bahnstrecken, wo die EEG-Förderung eigentlich beispielsweise zwischen ein- und zweigleisigen Strecken unterscheidet. Zudem wurden die Gewichtungen im Projekt selbst festgelegt und könnten durch Expertenbefragungen und etablierte Gewichtungsverfahren fundierter bestimmt werden. Eine automatisierte Analyse ersetzt daher keine lokale Detailprüfung, sondern liefert vor allem eine fundierte Grundlage für weiterführende planerische Entscheidungen.

Für die nächsten Schritte bieten sich mehrere Erweiterungen an. So könnte das Solarpotenzial künftig noch stärker an die jeweilige Umgebung angepasst werden, etwa durch einen differenzierten „Smog-Faktor“ je nach Umgebung. Auch weitere Kriterien wie Moorflächen mit Wiedervernässungspotenzial, insbesondere in Norddeutschland, oder Anwendungsfälle wie Agri-PV ließen sich integrieren. Insgesamt steckt in dem Ansatz noch viel Entwicklungspotenzial, weshalb wir uns gut vorstellen können, ihn auch über das Projekt hinaus weiter zu verfolgen.
</div>


**OBEN LINK!**
**Bindestrcihe weg!**

### *Literature*
Umweltbundesamt. (2023). Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz
UMWELTBUNDESAMT (UBA) (2023): Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz (24.03.2026).
BUNDESNETZAGENTUR (BNetzA) (2026a): Ausbau erneuerbarer Energien 2025. https://www.bundesnetzagentur.de/SharedDocs/Pressemitteilungen/DE/2026/20260108_EEG.html (24.03.2026).
BUNDESNETZAGENTUR (BNetzA) (2026b): Bundesnetzagentur ver­öf­fent­licht Da­ten zum Strom­markt 2025. https://www.bundesnetzagentur.de/1087156 (24.03.2026).
LANDESAMT FÜR GEOINFORMATION UND LANDESVERMESSUNG NIEDERSACHSEN (LGLN) (2026): Webdienste. https://ni-lgln-opengeodata.hub.arcgis.com/pages/geodatendienste (24.03.2026).
UMWELTBUNDESAMT (UBA) (2023): Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz (24.03.2026).
UMWELTBUNDESAMT (UBA) (2025): Photovoltaik-Freiflächenanlagen. https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/photovoltaik/photovoltaik-freiflaechenanlagen (24.03.2026).

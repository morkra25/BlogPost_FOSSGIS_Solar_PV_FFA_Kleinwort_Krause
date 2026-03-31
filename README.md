# Automatisierte Freiflächen-PV-Standortsuche 

## Warum die Suche nach PV-Flächen so wichtig und doch so schwierig ist

<div align="justify">
  Nicht jede sonnige Fläche ist automatisch ein guter PV-Standort. Zwischen Schutzgebieten, Hochwassergefahr, Bodengüte und Infrastrukturanbindung wird schnell klar, dass die Standortsuche eine komplexe planerische Abwägung erfordert. Umso sinnvoller wäre es, wenn nicht jede Kommune dafür eigene methodische Ansätze entwickeln müsste. Gegenwärtig ist dies jedoch häufig noch der Fall. 
  
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

Entsprechend wächst der Bedarf an einem Tool, mit dem Kommunen durch die Eingabe ihres Gemeindenamens und gegebenenfalls ergänzt um eigene Anforderungen geeignete landwirtschaftliche Flächen für Freiflächen-PV identifizieren können. Eine GIS-gestützte Analyse eignet sich hierfür besonders, da sie datenbasiert, reproduzierbar und entsprechend transparent bei Planungs- und Entscheidungsprozessen unterstützen kann.</div>

<div align="justify">

<div style="border-left: 4px solid #b8b9ba; padding: 0.5em 1em; margin: 1em 0;">
  <p style="margin: 0 0 0.75em 0;"><strong>Ziel des Projekts:</strong> Entwicklung eines GIS-basierten Workflows, mit dem geeignete landwirtschaftliche Schläge für Freiflächen-Photovoltaikanlagen automatisiert identifiziert werden können. Dafür werden relevante räumliche Kriterien zusammengeführt und so ausgewertet, dass potenziell geeignete Flächen nachvollziehbar ausgegeben werden.</p>
  <p style="margin: 0;"><strong>Untersuchungsgebiet:</strong> Viele rechtliche Vorgaben zur Errichtung von PV-FFA sind föderal strukturiert und damit in weiten Teilen Ländersache. Das Projekt wird daher exemplarisch für das Land Niedersachsen durchgeführt.</p>
</div>
</div>

---

## Methodik

### Vom Geodatensatz zur Eignungsbewertung

<div align="justify">
 Am Anfang stellt sich die Frage, wie sich aus vielen einzelnen Geodaten am Ende eine nachvollziehbare PV-Eignungsbewertung für landwirtschaftliche Flächen ableiten lässt. Denn erst im Zusammenspiel verschiedener Informationen wird sichtbar, welche Flächen grundsätzlich infrage kommen und welche aufgrund bestimmter Rahmenbedingungen ausgeschlossen oder schlechter bewertet werden sollten. Um diese Einflussfaktoren systematisch zusammenzuführen, haben wir mit einer <strong>Multikriterienanalyse (MCDA)</strong> gearbeitet.

Zur Bewertung wurden zwei Arten von Kriterien abgeleitet.
</div>

<div align="justify">
 Dieser Ansatz eignet sich besonders dann, wenn mehrere räumliche Kriterien gleichzeitig berücksichtigt und zu einer gemeinsamen Bewertung zusammengeführt werden sollen.
</div>

<div align="justify">
  Dafür wurden unterschiedliche räumliche Datensätze zusammengeführt, darunter landwirtschaftliche Schläge, Schutzgebiete, Hochwasserflächen, Siedlungsnähe, Verkehrsinfrastruktur und Bodengüte. Diese Informationen wurden so aufbereitet, dass sie räumlich vergleichbar und gemeinsam auswertbar sind.
</div>

#### 1. Harte Ausschlusskriterien

<div align="justify">
Zunächst kommen harte Ausschlusskriterien zum Einsatz: Sie filtern alle Flächen heraus, die für Freiflächen-PV rechtlich, ökologisch oder praktisch nicht infrage kommen. Diese sind in der Abbildung aufgezählt. Zu den Schutzgebieten zählen sämtliche naturschutzrechtlich geschützten Flächen wie bspw. Naturschutzgebiete, Vogelschutzgebiete und Natura 2000-Gebiete.</div>
<div align="justify">
<p>Übrig bleiben die landwirtschaftlichen Flächen, die grundsätzlich bebaut werden könnten.</p>
</div>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_harte_Kriterien.png" title="Harte Kriterien" width="75%">

*Abbildung 1: Harte Bewertungskriterien*


#### 2. Weiche Bewertungskriterien

<div align="justify">

  <p>Diese verbleibenden, potenziell bebaubaren Flächen werden anschließend anhand weicher Kriterien weiter differenziert bewertet.</p>

  <p>Bevorzugt werden dabei Standorte:</p>

  <ul>
    <li>mit geringer Hangneigung,</li>
    <li>in der Nähe von Straßen,</li>
    <li>in der Nähe von Bahntrassen,</li>
    <li>in der Nähe von Ortslagen,</li>
    <li>in der Nähe von Strominfrastruktur, also Hochspannungsleitungen und Umspannwerke.</li>
  </ul>

  <p>Das reduziert den Erschließungsaufwand und nutzt bereits vorgeprägte Räume, anstatt neue Landschaftsbereiche zusätzlich zu beanspruchen.</p>

  <p>Die Nähe zur Strominfrastruktur ist dabei besonders wichtig, da ein Netzanschluss mit zunehmender Entfernung aufwendiger und teurer wird. Weil öffentlich zugängliche Daten zu konkreten Netzanschlusspunkten nur eingeschränkt verfügbar sind, wird dieser Aspekt neben der Nähe zu Umspannwerken näherungsweise eben auch über weitere bestehende Infrastrukturen wie Ortslagen und Bahnstrecken berücksichtigt, die auf vorhandene Strominfrastruktur schließen lassen.</p>

  <p>Bevorzugt werden außerdem Standorte mit:</p>

  <ul>
    <li>einer geringen Bodengüte bzw. Ertragsfähigkeit,</li>
    <li>einem hohen jährlichen Solarpotenzial.</li>
  </ul>

  <p>Die individuellen Gewichtungen und das allgemeine Bewertungsschema werden nachfolgend abgebildet. Die Gewichtungen der Kriterien wurden im Projekt selbst festgelegt und orientieren sich an vergleichbaren Ansätzen, insbesondere an HAUGER et al. (2025).</p>

</div>



<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_weiche_Kriterie_ohne_HG.png" title="Weiche Bewertungskriterien und das allgemeine Bewertungsschema." alt="Dies ist beschreibung" width= "100%">
<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 2: Weiche Bewertungskriterien und das allgemeine Bewertungsschema</em></div>


#### 3. Rasterbasierte Gesamtbewertung
<div align="justify">
<p>Die eigentliche Bewertung erfolgt rasterbasiert. Ein Raster kann man sich dabei wie ein Schachbrettmuster vorstellen: Die Untersuchungsfläche wird in viele kleine, gleich große, quadratische Felder unterteilt, und jedes Feld erhält für die jeweiligen Kriterien einen Wert zwischen 1 (sehr schlecht geeignet) und 5 (sehr gut geeignet), welcher die PV-Eignung detailliert beschreibt. Die genauen Bewertungszuordnungen finden sich im Anhang der ausführlicheren <a href="https://github.com/morkra25/FOSSGIS_Solar_Project_Kleinwort_Krause/tree/main/Dokumentation">Methodik-Dokumentation.</a>
</div>

<div align="justify">Die klassifizierten Raster werden anschließend vertikal „durchstochen“ und unter Berücksichtigung der Gewichtungsfaktoren miteinander gemittelt. Das Ergebnis ist ein Wert zwischen 1 und 5, der die Gesamtbewertung repräsentiert.</div>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Abbildung_Raster_MCDA.png" title="Schematische Darstellung der Multilayer-Rasteranalyse" alt="Dies ist beschreibung" width= "100%">
<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 3: Rasterbasierte Eignungsbewertung der Flächen (schematische Darstellung)</em></div>

#### 4. Aggregation auf Schlagebene
<div align="justify">
Da für die Planung nicht das einzelne Pixel, sondern der landwirtschaftliche Schlag entscheidend ist, wurden die rasterbasierten Ergebnisse anschließend auf Schlagebene gemittelt.

Hier findet noch eine weitere, abschließende Filterung statt: da mit der Pachtung bzw. dem Kauf eines Schlags ein gewisser bürokratischer Aufwand einhergeht, werden in diesem Schritt nur jene Schläge berücksichtigt, welche mit mind. **1 ha an PV-Fläche** bestückt werden können.

Zur Ergänzung der Eignungsbewertung wird abschließend für jeden potenziell geeigneten Schlag ein vereinfachter jährlicher Energieertrag abgeschätzt. Grundlage ist die aufsummierte jährliche Einstrahlungsmenge aus der Solarpotenzialanalyse, die mit einem Flächenkorrekturfaktor, einem Modulwirkungsgrad und einem Aufständerungsfaktor verrechnet wird und so den bewerteten Flächen als zusätzliches Attribut in Form der erwartbaren jährlichen Energie in MWh zugewiesen werden kann.
</div>

#### 5. Automatisierter Workflow

<div align="justify">
<p>Der gesamte Workflow ist skriptbasiert in Python umgesetzt und dadurch vollständig automatisiert. Bereits die Änderung des Gemeindenamens reicht aus, um Datenbeschaffung und Analyse für eine andere Gemeinde in Niedersachsen erneut durchzuführen.</p></div>

<div align="justify">
Mit Ausnahme der Umspannwerke, der HQ100-Hochwassergebiete und der Wasserschutzgebiete werden alle Daten automatisiert über Schnittstellen (APIs) vom Landesamt für Geoinformation und Landesvermessung Niedersachsen bezogen (LGLN 2026). Dabei erkennt das Programm, welche Gemeinde untersucht wird und ruft die entsprechend benötigten Daten ab. </div>
<div align="justify">
Die Umspannwerke werden über die Overpass API abgefragt. Für die HQ100-Daten sowie für die Wasserschutzgebiete stehen keine API-Schnittstellen zur Verfügung; sie werden daher lokal vorgehalten und automatisch passend für das jeweilige Untersuchungsgebiet zugeschnitten.
</div>

---

## Ergebnisse
<div align="justify">
Um die Ergebnisse greifbar zu machen, veranschaulichen wir den Workflow exemplarisch an der Beispielgemeinde <strong>Dollern</strong>. So lässt nachvollziehen, wie aus vielen einzelnen Geodaten am Ende eine nachvollziehbare Eignungsbewertung für landwirtschaftliche Flächen entsteht.

###### *Hinweis: Aufgrund eines Serverausfalls konnten die den Karten zugrunde liegenden Berechnungen nicht mit den ALKIS-Bodenbewertungen durchgeführt werden. Daher sind auch keine genauen Wertbereiche angegeben.*

Die erste Karte zeigt zunächst ein Beispiel eines einzelnen Kriteriums, in diesem Fall der Nähe zu Straßen. Es wird sichtbar, wie ungleichmäßig die Kriterien über den Raum verteilt sind und entsprechend die Gesamtbewertung prägen können.</div>  
  
<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Karte_Bsp_Strassen.png" title="Beispiel eines Einzelkriteriums (Bodengüte)" alt="Beispiel eines Einzelkriteriums (hier Bodengüte)" width="75%">

<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 4: Beispiel eines Einzelkriteriums (Nähe zu Straßen)</em></div>

Die nächste Karte veranschaulicht die Umsetzung des Abzugs der beschriebenen Negativflächen von den Positivflächen, also den landwirtschaftlichen Flächen. 

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Karte_Abzugslogik.png" title="Abzug der nicht-bebaubaren Flächen von den landwirtschaftlichen Flächen" alt="Abzug der nicht-bebaubaren Flächen von den landwirtschaftlichen Flächen" width="75%">


<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 5: Abzug der nicht-bebaubaren Flächen von den landwirtschaftlichen Flächen</em></div>


Die erste konkrete Ergebniskarte zeigt die PV-FFA-Eignung auf Pixelebene.

Hier wird deutlich, welcher Einfluss von einzelnen Faktoren wie beispielsweise der Nähe zu Stromleitungen ausgeht und wie kleinräumig sich die Bewertung im Raum unterscheidet.


<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Karte_Pixelbewertung.png" title="Pixelweise Eignungsbewertung für eine Bebauung mit einer PV-FFA" alt="Pixelweise Eignungsbewertung für eine Bebauung mit einer PV-FFA" width="100%">

<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 6: Pixelweise Eignungsbewertung für eine Bebauung mit einer PV-FFA</em></div>

<div align="justify">
<p>Besonders relevant für die Praxis ist dann die Aggregation auf Schlagebene. Statt vieler kleiner Rasterzellen werden die Ergebnisse pro landwirtschaftlichem Schlag zusammengefasst. Dadurch entsteht eine deutlich besser lesbare Karte, aus der unmittelbar hervorgeht, welche Schläge innerhalb der Beispielsgemeinde insgesamt besonders gut geeignet sind. Die Bewertung wird damit von einer technischen Rasteranalyse in eine Form übersetzt, die für planerische Entscheidungen tatsächlich nutzbar ist. So könnten auch größere, zusammenhängende PV-FFA-Anlagen geplant werden, welche sich nicht ausschließlich aus den bestbewerteten Flächen zusammensetzen.</p>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Karte_aggregierte_Bewertung.png" title="Schlagweise Eignungsbewertung für eine Bebauung mit einer PV-FFA" alt="Schlagweise Eignungsbewertung für eine Bebauung mit einer PV-FFA" width="100%">


<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 7: Schlagweise Eignungsbewertung für eine Bebauung mit einer PV-FFA</em></div>

<p>Die letzte Karte zeigt außerdem die gemittelte Ertragsabschätzung der Felder in MWh pro Hektar. Damit zeigt die Analyse nicht nur, welche Flächen grundsätzlich geeignet sind, sondern auch, auf welchen Standorten besonders hohe Stromerträge zu erwarten wären. In den Daten kann auch der absolute Wert abgelesen werden. Werte von rund 1000 MWh/ha entsprechen gängigen Erwartungswerten (vgl. MÜNCHNER SOLARKRAFTWERKE 2024). </p>

</div>

<img src="https://raw.githubusercontent.com/morkra25/BlogPost_FOSSGIS_Solar_PV_FFA_Kleinwort_Krause/refs/heads/main/images/Karte_Ertragsabschätzung.png" title="Jährliche Energieertragsschätzung" alt="Jährliche Energieertragsschätzung" width="100%">


<div style="font-size: 0.85em; margin-top: 0; padding-top: 0;"><em>Abbildung 8: Jährliche Energieertragsschätzung 
</em></div>

---

## Zusammenfassung, Fazit und Ausblick

<div align="justify">
<p>
Insgesamt zeigen unser Projekt und die Ergebnisse der Beispielsgemeinde, dass sich die Standortsuche für Freiflächen-PV mit dem entwickelten Workflow deutlich systematischer und nachvollziehbarer gestalten lässt als durch rein manuelle Einzelfallanalysen. Durch die Kombination aus Ausschlusskriterien, abgestufter Bewertung und Aggregation auf Schlagebene entsteht ein transparenter und reproduzierbarer Ansatz, der auch für Laien nachvollziehbar macht, warum bestimmte Flächen besser geeignet sind als andere.</p>

<p>Besonders gelernt haben wir, dass der initiale Aufwand eines skriptbasierten Ansatzes zwar hoch ist, langfristig aber große Vorteile bietet. Der Workflow ist grundsätzlich auf andere Gemeinden übertragbar, Kriterien und Gewichtungen lassen sich flexibel anpassen, und auch eine automatische Kartengenerierung wäre problemlos möglich. Perspektivisch ließe sich das Tool weiter ausbauen, etwa durch eine eigene Bedienoberfläche oder Regler zur individuellen Gewichtung der Kriterien. Denkbar wäre sogar, unterschiedliche Vorgaben verschiedener Bundesländer direkt im Programm zu hinterlegen und den Workflow damit deutlich breiter nutzbar zu machen.</p>


<p> Gleichzeitig bestehen Grenzen. Datenqualität und Datenverfügbarkeit können regional stark variieren, und bislang stellen nur wenige Bundesländer ihre Daten über verlässliche API-Schnittstellen bereit. Niedersachsen gehört hier zu den wenigen Ländern, in denen dies ohne größere Workarounds möglich ist. Hinzu kommt, dass bei einzelnen Kriterien bewusst Vereinfachungen getroffen wurden, etwa bei Bahnstrecken, wo die EEG-Förderung eigentlich beispielsweise zwischen ein- und zweigleisigen Strecken unterscheidet. Zudem wurden die Gewichtungen im Projekt selbst festgelegt und könnten durch Expertenbefragungen und etablierte Gewichtungsverfahren fundierter bestimmt werden. Eine automatisierte Analyse ersetzt daher keine lokale Detailprüfung, sondern liefert vor allem eine fundierte Grundlage für weiterführende planerische Entscheidungen.</p>

<p> Für die nächsten Schritte bieten sich mehrere Erweiterungen an. So könnte das Solarpotenzial künftig noch stärker an die jeweilige Umgebung angepasst werden, etwa durch einen differenzierten „Smog-Faktor“ je nach Umgebung. Auch weitere Kriterien wie Moorflächen mit Wiedervernässungspotenzial, insbesondere in Norddeutschland, oder Anwendungsfälle wie Agri-PV ließen sich integrieren. Insgesamt steckt in dem Ansatz noch viel Entwicklungspotenzial, weshalb wir uns gut vorstellen können, ihn auch über das Projekt hinaus weiter zu verfolgen. </p>
</div>

### *Literatur*


<p>BUNDESNETZAGENTUR (BNetzA) (2026a): Ausbau erneuerbarer Energien 2025. https://www.bundesnetzagentur.de/SharedDocs/Pressemitteilungen/DE/2026/20260108_EEG.html (24.03.2026).</p>
<p>BUNDESNETZAGENTUR (BNetzA) (2026b): Bundesnetzagentur ver­öf­fent­licht Da­ten zum Strom­markt 2025. https://www.bundesnetzagentur.de/1087156 (24.03.2026).</p>
<p>LANDESAMT FÜR GEOINFORMATION UND LANDESVERMESSUNG NIEDERSACHSEN (LGLN) (2026): Webdienste. https://ni-lgln-opengeodata.hub.arcgis.com/pages/geodatendienste (24.03.2026).</p>

<p>MÜNCHNER SOLARKRAFTWERKE (2024): Solarpark Rendite: was Sie wissen müssen. https://muenchner-solarkraftwerke.de/solarpark-rendite/ (29.03.2024).</p>
<p>UMWELTBUNDESAMT (UBA) (2023): Was sind die Kernelemente des Erneuerbare-Energien-Gesetzes? https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/erneuerbare-energien-gesetz (24.03.2026).</p>
<p>UMWELTBUNDESAMT (UBA) (2025): Photovoltaik-Freiflächenanlagen. https://www.umweltbundesamt.de/themen/klima-energie/erneuerbare-energien/photovoltaik/photovoltaik-freiflaechenanlagen (24.03.2026).</p>

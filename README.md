# 03_K-Means_Clustering

 Binder Badge zum starten des Jupyter Notebooks (K-Means_Clustering_Projekt_Musterloesung.ipynb) via myBinder: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tristii/03_K-Means_Clustering/main?labpath=K_Means_Clustering_Projekt_Musterloesung.ipynb) 

In der Umgebung von mybinder können Sie das Übungsbeispiel ausführen lassen, eigene Lösungen codieren (bestehenden Code modifizieren), um das Übungsbeispiel mit dem erwartenden Ergebnis zu reproduzieren.

## Dokumentation zur Übungsaufgabe: 
Aufgebaut ist die Übungsaufgabe in jeweils in Beschreibungsabschnitt was explizit gemacht werden soll. Die jeweilige darunterliegende Zelle stellt den Code Bereich dar, in der dieser Aufgabenabschnitt codiert wird und ggf. den dazugehörigen Output nach der Ausführung (SHIFT + Enter) der jeweiligen Codezelle darstellt.

! Um das zu erwartendee Ergebnis (Output) der Lösung im Übungsbeispiel nicht zu verlieren bzw. zu überschreiben, können Sie nach der Beschreibung der jeweiligen Teil-Aufgabe eine Zwischenzeile(neue Zeile) einfügen, in der Sie Ihre Lösung codieren um danach Ihren Code mit dem darunter liegenden Mustercode + dessen Output vergleichen/überprüfen zu können. 

**Vorgehensweise im Übungsbeispiel:**

Fallbeispiel: Für dieses Projekt werden wir versuchen K-Means Clustering zu verwenden, um Universitäten in den USA in zwei Gruppen zu unterteilen: Private und öffentliche.
Ein wichtiger Hinweis: Für diese Universitäten wissen wir die tatsächliche Zuordnung und finden sie im Datensatz. Wir werden sie aber ignorieren da K-Means Clustering ein Unsupervised Learning Algorithmus ist.
Normalerweise verwendet man den K-Means Clustering Algorithmus für Daten, deren Zugehörigkeit zu einem Cluster man nicht kennt. In diesem Fall verwenden wir die Zuteilung, um beurteilen zu können, wie gut der Algorithmus performt. Da das in echten Anwendungen nicht möglich ist sind Confusion Matrix und Classification Report am Ende des Projekts nur theoretische Auswertungen

**1. Libraries**
* notwendige Libraries müssen importiert werden (pandas, numpy, matplotlib.pyplot, seaborn) für die Datenverarbeitung und Datenvisualisierung

**2. Rohdaten**
* Rohdaten (College_Data.csv) einlesen und DataFrame erstellen
* Deskriptive Statistiken anzeigen und analysieren mit der head(), info() und describe() Funktion

**3. Explorative Datenanalyse**

mittels Plots aus der Seaborn und Pandas Library können die Daten visualisiert werden, um sie besser analysieren zu können. 
* Erstelle ein Scatterplot von "Grad.Rate" vs. "Room.Board" in dem die Punkte nach der "Private" Spalte eingefärbt bzw. aufgeteilt sind
* Erstelle ein Scatterplot von "F.Undergrad" vs. "Outstate" in dem die Punkte nach der "Private" Spalte eingefärbt bzw. aufgeteilt sind
* Erstelle ein Histogramm zweier Betrachtungen in einem Diagramm. Es soll die "Out of State Tuition" ("Outstate" Spalte) gezeigt werden und die Histogramme nach "Private" geteilt werden
* Erstelle das gleiche Histogramm wie im vorherigen Punkt für "Grad.Rate"
* Filter nach den Universitäten mit einer Abschlussrate mit mehr als 100%
* Setzte für die Universität die Abschlussrate ("Grad.Rate") auf 100, damit es Sinn ergibt


**4. K-Means Cluster erstellen**
* Importiere KMeans von sklearn.cluster
* Erstelle eine Instanz von einem K-Means Modell mit 2 Clustern.
* Fitte das Modell auf alle Daten (ohne die "Private" Spalte) mit der fit() Methode 


**5. Auswertung**
* Füge dem DataFrame eine neue Spalte "Cluster" hinzu, welche die binäre Werte 1 für private 0 für öffentliche Universitäten annehmen kann. 
* import classification_report,confusion_matrix von sklearn.metrics, um zu sehen wie gut das K Means Clustering die Universitäten zugeordnet hat
* Klassifizierungsreport für das Modell, um die Perfomance in Bezug auf Precision und Recall Werte zu erhalten 
* Confusion Matrix erstellen, um die Leistung des Algorithmus visualisieren zu können



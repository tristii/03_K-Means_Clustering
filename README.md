# 03_K-Means_Clustering

 Binder Badge zum starten des Jupyter Notebooks (K-Means_Clustering_Projekt_Musterloesung.ipynb) via myBinder: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tristii/02_Decision_Tree/main?labpath=Decision_Trees_und_Random_Forests_Projekt_Musterloesung.ipynb) 

In der Umgebung von mybinder können Sie das Übungsbeispiel ausführen lassen, eigene Lösungen codieren (bestehenden Code modifizieren), um das Übungsbeispiel mit dem erwartenden Ergebnis zu reproduzieren.

## Dokumentation zur Übungsaufgabe: 
Aufgebaut ist die Übungsaufgabe in jeweils in Beschreibungsabschnitt was explizit gemacht werden soll. Die jeweilige darunterliegende Zelle stellt den Code Bereich dar, in der dieser Aufgabenabschnitt codiert wird und ggf. den dazugehörigen Output nach der Ausführung (SHIFT + Enter) der jeweiligen Codezelle darstellt.

! Um das zu erwartendee Ergebnis (Output) der Lösung im Übungsbeispiel nicht zu verlieren bzw. zu überschreiben, können Sie nach der Beschreibung der jeweiligen Teil-Aufgabe eine Zwischenzeile(neue Zeile) einfügen, in der Sie Ihre Lösung codieren um danach Ihren Code mit dem darunter liegenden Mustercode + dessen Output vergleichen/überprüfen zu können. 

**Vorgehensweise im Übungsbeispiel:**

Fallbeispiel: Für dieses Projekt werden wir öffentlich verfügbare Daten von LendingClub.com verwenden. Lending Club bringt Leute zusammen, die Geld brauchen (Leihende) und solche, die Geld investieren möchten (Geldgeber). Als Invester möchte man dann verständlicherweise vor allem an die Leute sein Geld verleihen, die es mit einer hohen Wahrscheinlichkeit zurückzahlen. Wir werden versuchen ein Modell zu erstellen, dass bei dieser Vorhersage hilft.
Wir werden Daten von 2007 bis 2010 verwenden, bevor das Unternehmen an die Börse ging. Anhand der Daten werden wir versuchen vorherzusagen, ob ein Leihender das Geld zurückgezahlt hat oder nicht. Die Daten haben wir als CSV in den Kursunterlagen beigefügt. Diese Datei wurde bereits um die nicht verfügbaren Einträge gesäubert.

**1. Libraries**
* notwendige Libraries müssen importiert werden (pandas, numpy, matplotlib.pyplot, seaborn) für die Datenverarbeitung und Datenvisualisierung

**2. Rohdaten**
* Rohdaten(load_data.csv) einlesen und DataFrame erstellen
* Deskriptive Statistiken anzeigen und analysieren mit der head(), info() und describe() Funktion

**3. Explorative Datenanalyse**

mittels Plots aus der Seaborn und Pandas Library können die Daten visualisiert werden, um sie besser analysieren zu können. 
* Histogram zweier FICO Verteilungen übereinandern erstellen, je eins nach dem credit.policy Ergebnis
* Erstelle ein gleiches Diagramm, dass dieses mal nach der "not.fully.paid" Spalte getrennt wird.
* Countplot mit Seaborn erstellen, der die  Anzahl der Leihgaben ("loans") nach Zweck ("purpose") anzeigt. Der Hue (Aufteilung) soll durch die Spalte ("not fully paid") definiert sein
* Jointplot, der den Trend zwischen FICO Score und den Zinsen ("interest rate") betrachtet
* Erstelle zwei lmplots, um zu sehen, ob sich der Trend zwischen "not.fully.paid" und "credit.policy" unterscheidet

**4. Vorbereitung der Daten**

Umwandlung der kategorische Spalte "purpose" in Dummy-Variablen mit pd.get_dummies(), damit sklearn mit den Daten arbeiten kann 
* Erstellen eine Liste die die kategorische Spalte "purpose" enthält
* Nutze pd.get_dummies(loans,columns=...,drop_first=True), um einen korrigiertes und größeres DataFrame zu erstellen


**5. Train Test Split**
* import train_test_split von sklearn.model_selection
* Aufteilen der Daten in Trainings- und Testdaten

**6. Trainieren eines Decision Tree
* import DecisionTreeClassifier von sklearn.tree
* Instanz eines DecisionTreeClassifier erstellen und die Traningsdaten darauf fitten mit der fit() Funktion

**7. Vorhersagen und Auswertung (erwartendes Ergebnis/Output)**
* Vorhersage erstellen aus den Testdaten mit der predict() Funktion, welche auf das zuvor erstellte Modell angewendet wird
* import classification_report,confusion_matrix von sklearn.metrics 
* Klassifizierungsreport für das Modell, um die Perfomance in Bezug auf Precision und Recall Werte zu erhalten 
* Confusion Matrix erstellen, um die Leistung des Algorithmus visualisieren zu können

---
title: Beherrschen der MS Project-Zeitskalenzählung in Aspose.Tasks
linktitle: Legen Sie die Anzahl der Zeitskalen in Aspose.Tasks fest
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie die Zeitskalenanzahl in MS Project mithilfe von Aspose.Tasks für Java effektiv verwalten. Optimieren Sie die Projektvisualisierung und -verwaltung mühelos.
type: docs
weight: 22
url: /de/java/project-file-operations/set-time-scale-count/
---
## Einführung
Die Verwaltung der Zeitskalenanzahl in MS Project kann sich erheblich auf die Projektvisualisierung und -verwaltung auswirken. Mit Aspose.Tasks für Java, einer leistungsstarken API zur programmgesteuerten Bearbeitung von Projektmanagementaufgaben, können Sie die Zeitskalenanzahl effizient manipulieren, um Projektansichten an Ihre spezifischen Anforderungen anzupassen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist.
2.  Aspose.Tasks for Java-Bibliothek: Laden Sie die Aspose.Tasks for Java-Bibliothek herunter und installieren Sie sie. Sie können es von bekommen[Hier](https://releases.aspose.com/tasks/java/).
3. Grundkenntnisse der Java-Programmierung: Vertrautheit mit der Programmiersprache Java ist von Vorteil.

## Pakete importieren
Importieren Sie die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Schritt 1: Datenverzeichnis festlegen
Definieren Sie den Pfad zum Datenverzeichnis, in dem Ihre Projektdateien gespeichert werden:
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrem Datenverzeichnis.
## Schritt 2: Projektinstanz erstellen
 Instanziieren Sie eine neue`Project` Objekt:
```java
Project project = new Project();
```
Dadurch wird ein neues Projektobjekt erstellt.
## Schritt 3: Gantt-Diagrammansicht konfigurieren
 Ein ... kreieren`GanttChartView` Objekt zum Konfigurieren der Gantt-Diagrammansicht:
```java
GanttChartView view = new GanttChartView();
```
## Schritt 4: Legen Sie die Zeitskalenanzahl für die unterste Ebene fest
Legen Sie die Anzahl und die Tick-Sichtbarkeit für die unterste Zeitskalaebene fest:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Dies gibt die Anzahl der Intervalle an und ob Ticks für die unterste Ebene angezeigt werden sollen.
## Schritt 5: Legen Sie die Zeitskalenanzahl für die mittlere Ebene fest
Konfigurieren Sie auf ähnliche Weise die mittlere Zeitskalenebene:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Schritt 6: Ansicht zum Projekt hinzufügen
Fügen Sie die konfigurierte Ansicht zum Projekt hinzu:
```java
project.getViews().add(view);
```
Dadurch wird die benutzerdefinierte Ansicht zum Projekt hinzugefügt.
## Schritt 7: Testdaten zum Projekt hinzufügen
Fügen Sie dem Projekt zur Demonstration einige Testdaten hinzu:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Dadurch werden zwei Aufgaben mit festgelegter Dauer erstellt.
## Schritt 8: Projekt als PDF speichern
Speichern Sie das Projekt als PDF-Datei:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Dadurch wird das Projekt mit den angewendeten Konfigurationen in einer PDF-Datei gespeichert.

## Abschluss
Durch die effektive Verwaltung der Zeitskalenanzahl in MS Project mit Aspose.Tasks für Java können Sie Projektansichten für eine bessere Visualisierung und Verwaltung anpassen.
## FAQs
### F: Kann Aspose.Tasks für Java große Projektdateien verarbeiten?
A: Ja, Aspose.Tasks für Java ist in der Lage, große Projektdateien effizient zu verarbeiten.
### F: Ist Aspose.Tasks für Java mit verschiedenen Java-IDEs kompatibel?
A: Ja, Aspose.Tasks für Java funktioniert nahtlos mit beliebten Java Integrated Development Environments (IDEs) wie Eclipse und IntelliJ IDEA.
### F: Kann ich das Erscheinungsbild von Gantt-Diagrammen mit Aspose.Tasks für Java anpassen?
A: Absolut, Aspose.Tasks für Java bietet umfangreiche Möglichkeiten, das Erscheinungsbild von Gantt-Diagrammen an Ihre Anforderungen anzupassen.
### F: Gibt es eine Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).
### F: Wo erhalte ich Unterstützung für Aspose.Tasks für Java?
 A: Unterstützung und Hilfe finden Sie im Aspose.Tasks-Forum[Hier](https://forum.aspose.com/c/tasks/15).
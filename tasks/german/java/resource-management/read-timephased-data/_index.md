---
title: Lesen Sie Zeitphasendaten für Ressourcen in Aspose.Tasks
linktitle: Lesen Sie Zeitphasendaten für Ressourcen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Zeitphasendaten aus MS Project-Ressourcen extrahieren. Schritt-für-Schritt-Anleitung.
type: docs
weight: 15
url: /de/java/resource-management/read-timephased-data/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess des Lesens von Zeitphasendaten für MS Project-Ressourcen mit Aspose.Tasks für Java. Diese Bibliothek bietet leistungsstarke Funktionen für die programmgesteuerte Verwaltung von Microsoft Project-Dateien.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es hier herunterladen[Webseite](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) und befolgen Sie die Installationsanweisungen.
2.  Aspose.Tasks für Java-Bibliothek: Laden Sie die Aspose.Tasks für Java-Bibliothek von herunter[Download-Seite](https://releases.aspose.com/tasks/java/) und befolgen Sie die Installationsanweisungen in der Dokumentation.

## Pakete importieren
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Schritt 1: Datenverzeichnis einrichten
Definieren Sie zunächst das Verzeichnis, in dem sich Ihre MS Project-Datei befindet.
```java
String dataDir = "Your Data Directory";
```
## Schritt 2: Lesen Sie die MS Project-Vorlagendatei
Geben Sie den Namen Ihrer MS Project-Vorlagendatei an.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Schritt 3: Eingabedatei als Projekt lesen
Lesen Sie die Eingabedatei mit Aspose.Tasks und laden Sie sie als Projektobjekt.
```java
Project project = new Project(dataDir + fileName);
```
## Schritt 4: Ressource nach ID abrufen
Rufen Sie die gewünschte Ressource anhand ihrer eindeutigen Kennung (ID) aus dem Projekt ab.
```java
Resource resource = project.getResources().getByUid(1);
```
## Schritt 5: Zeitphasendaten für Ressourcenarbeit drucken
Drucken Sie die Zeitphasendaten für die Ressourcenarbeit.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Schritt 6: Zeitphasendaten für Ressourcenkosten drucken
Drucken Sie die Zeitphasendaten für Ressourcenkosten.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java Zeitphasendaten für MS Project-Ressourcen liest. Wenn Sie diese Schritte befolgen, können Sie wertvolle Informationen effizient und programmgesteuert aus Ihren Projektdateien extrahieren.
## FAQs
### Kann Aspose.Tasks neben Microsoft Project auch andere Arten von Projektdateien verarbeiten?
Ja, Aspose.Tasks unterstützt verschiedene Dateiformate, darunter MPP, XML und CSV.
### Ist Aspose.Tasks mit verschiedenen Java-Entwicklungsumgebungen kompatibel?
Ja, Aspose.Tasks ist mit allen wichtigen Java-IDEs und Frameworks kompatibel.
### Kann ich Projektdaten mit Aspose.Tasks manipulieren?
Aspose.Tasks bietet auf jeden Fall umfangreiche APIs zum Erstellen, Ändern und Analysieren von Projektdaten.
### Ist Aspose.Tasks für Projekte auf Unternehmensebene geeignet?
Ja, Aspose.Tasks wird aufgrund seiner Zuverlässigkeit und Skalierbarkeit häufig in Unternehmensumgebungen verwendet.
### Wo finde ich Unterstützung, wenn bei der Verwendung von Aspose.Tasks Probleme auftreten?
 Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für die Unterstützung der Community und des Support-Teams.
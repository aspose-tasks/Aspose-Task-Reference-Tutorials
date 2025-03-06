---
title: Generieren Sie Zeitphasendaten in Aspose.Tasks
linktitle: Generieren Sie Zeitphasendaten für Ressourcenzuweisungen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Zeitphasendaten für Ressourcenzuweisungen generieren. Verbessern Sie die Effizienz Ihres Projektmanagements mit diesem umfassenden Leitfaden.
weight: 24
url: /de/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generieren Sie Zeitphasendaten in Aspose.Tasks

## Einführung
In diesem Tutorial führen wir den Prozess der Generierung von Zeitphasendaten für Ressourcenzuweisungen mithilfe von Aspose.Tasks für Java durch. Zeitphasendaten liefern wertvolle Erkenntnisse darüber, wie Ressourcen im Laufe der Zeit innerhalb eines Projekts zugewiesen werden, und helfen Projektmanagern, fundierte Entscheidungen zu treffen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können JDK von herunterladen und installieren[Hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java-Bibliothek: Sie benötigen die Aspose.Tasks for Java-Bibliothek. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Importieren wir zunächst die notwendigen Pakete, um mit Aspose.Tasks zu arbeiten:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Schritt 1: Lesen Sie die Quell-MPP-Datei
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
// Lesen Sie die MPP-Quelldatei
Project project = new Project(dataDir + "project.mpp");
```
## Schritt 2: Aufgaben- und Ressourcenzuweisung abrufen
```java
// Holen Sie sich die erste Aufgabe des Projekts
Task task = project.getRootTask().getChildren().getById(1);
// Rufen Sie die erste Ressourcenzuweisung des Projekts ab
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Schritt 3: Zeitphasendaten mit flacher Kontur generieren
```java
// Flache Kontur ist die Standardkontur
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 4: Ändern Sie die Kontur in „Schildkröte“.
```java
// Ändern Sie die Kontur in Schildkröte
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 5: Ändern Sie die Kontur in „BackLoaded“.
```java
// Ändern Sie die Kontur in „BackLoaded“.
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 6: Ändern Sie „Contour“ in „FrontLoaded“.
```java
// Kontur auf FrontLoaded ändern
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 7: Ändern Sie die Kontur in „Glocke“.
```java
// Ändern Sie die Kontur in Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 8: Ändern Sie Contour auf EarlyPeak
```java
// Kontur auf EarlyPeak ändern
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 9: Ändern Sie Contour auf LatePeak
```java
// Kontur auf LatePeak ändern
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Schritt 10: Ändern Sie Contour in DoublePeak
```java
// Kontur auf DoublePeak ändern
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Abschluss
In diesem Tutorial haben wir behandelt, wie Sie mit Aspose.Tasks für Java Zeitphasendaten für Ressourcenzuweisungen generieren. Das Verständnis verschiedener Arbeitskonturen kann Projektmanagern dabei helfen, die Ressourcenzuweisung und -planung in ihren Projekten effektiv zu verwalten.
## FAQs
### Kann ich Aspose.Tasks mit anderen Java-Bibliotheken verwenden?
Ja, Aspose.Tasks kann in andere Java-Bibliotheken integriert werden, um die Projektmanagementfunktionen zu verbessern.
### Ist Aspose.Tasks für große Unternehmensprojekte geeignet?
Aspose.Tasks ist auf jeden Fall für die Abwicklung von Projekten jeder Größe, einschließlich großer Unternehmensprojekte, konzipiert.
### Bietet Aspose.Tasks Unterstützung für verschiedene Projektdateiformate?
Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate, einschließlich MPP, XML und MPX.
### Kann ich Arbeitskonturen entsprechend meinen Projektanforderungen anpassen?
Ja, mit Aspose.Tasks können Benutzer benutzerdefinierte Arbeitskonturen definieren, die ihren spezifischen Projektanforderungen entsprechen.
### Gibt es ein Community-Forum, in dem ich Hilfe zu Aspose.Tasks erhalten kann?
 Ja, Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung und Diskussionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

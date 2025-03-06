---
title: Lesen Sie MS Project von Primavera mit Aspose.Tasks für Java
linktitle: Lesen Sie das Projekt von Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java nahtlos MS Project-Dateien aus Primavera XML lesen können. Steigern Sie die Effizienz Ihres Projektmanagements.
type: docs
weight: 20
url: /de/java/project-management/read-primavera/
---
## Einführung
Im Projektmanagement ist die Interoperabilität zwischen verschiedenen Softwareplattformen entscheidend für einen reibungslosen Arbeitsablauf. Aspose.Tasks für Java bietet robuste Funktionen zum Lesen von Microsoft Project-Dateien aus Primavera XML. Dieses Tutorial führt Sie durch den Prozess des Lesens von MS Project-Dateien aus Primavera mit Aspose.Tasks für Java und ermöglicht Ihnen die effiziente Untersuchung der Primavera-spezifischen Eigenschaften von Aufgaben.
## Voraussetzungen
Bevor Sie fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen installiert und eingerichtet sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java: Laden Sie Aspose.Tasks für Java herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Schritt 1: Datenverzeichnis einrichten
```java
String dataDir = "Your Data Directory";
```
 Stellen Sie sicher, dass Sie es ersetzen`"Your Data Directory"` mit dem tatsächlichen Pfad zu Ihrem Datenverzeichnis.
## Schritt 2: Projekt aus Primavera XML lesen
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Stellen Sie sicher, dass Sie es ersetzen`"PrimaveraProject.xml"` mit dem tatsächlichen Namen Ihrer Primavera XML-Datei.
## Schritt 3: Aufgaben durchlaufen und Primavera-spezifische Eigenschaften abrufen
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Dieser Code durchläuft jede Aufgabe im Projekt und gibt relevante Primavera-spezifische Eigenschaften aus.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Tasks für Java MS Project-Dateien aus Primavera XML lesen. Diese Funktionalität ermöglicht die nahtlose Integration und Analyse von Projektdaten über verschiedene Plattformen hinweg und steigert so die Gesamteffizienz des Projektmanagements.
## FAQs
### F: Kann ich die Primavera-spezifischen Eigenschaften von Aufgaben mit Aspose.Tasks für Java ändern?
A: Ja, Aspose.Tasks für Java bietet APIs, um Primavera-spezifische Eigenschaften von Aufgaben nach Bedarf zu ändern.
### F: Unterstützt Aspose.Tasks für Java das Lesen anderer Projektdateiformate?
A: Ja, Aspose.Tasks für Java unterstützt das Lesen verschiedener Projektdateiformate, einschließlich MPP, XML und Primavera XML.
### F: Ist Aspose.Tasks für Java für Projektmanagementanwendungen auf Unternehmensebene geeignet?
A: Absolut, Aspose.Tasks für Java bietet robuste Funktionen und Skalierbarkeit und eignet sich daher für Projektmanagementanwendungen auf Unternehmensebene.
### F: Kann ich mit Aspose.Tasks für Java Ressourceninformationen aus Primavera-Projekten extrahieren?
A: Ja, mit Aspose.Tasks für Java können Sie Ressourceninformationen zusammen mit Aufgabendetails aus Primavera-Projekten extrahieren.
### F: Wo finde ich zusätzliche Unterstützung oder Dokumentation für Aspose.Tasks für Java?
 A: Eine umfassende Dokumentation und Zugang zu Foren zur Unterstützung finden Sie unter[Aspose.Tasks für Java-Dokumentation](https://reference.aspose.com/tasks/java/) Seite.
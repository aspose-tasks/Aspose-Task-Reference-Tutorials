---
date: 2026-04-24
description: Erfahren Sie, wie Sie Aspose.Tasks Java verwenden, um Primavera‑XML in
  MS Project zu importieren, und ermöglichen Sie so einen nahtlosen Datenaustausch
  und ein verbessertes Projektmanagement.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Projekt aus Primavera in Aspose.Tasks lesen
second_title: Aspose.Tasks Java API
title: aspose tasks java – Primavera-XML in MS Project einlesen
url: /de/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project von Primavera mit Aspose.Tasks für Java lesen

## Einführung
In der heutigen schnelllebigen Projektmanagement-Welt müssen Sie häufig Zeitpläne zwischen Primavera P6 und Microsoft Project übertragen, ohne Details zu verlieren. Dieses Tutorial zeigt **wie man Primavera‑XML**‑Dateien liest und sie mit **aspose tasks java** in MS Project importiert. Am Ende der Anleitung können Sie Primavera‑spezifische Aufgabeneigenschaften in eine Java‑Anwendung übernehmen, wodurch Sie eine einzige Wahrheitsquelle für Analyse, Berichterstellung oder weitere Automatisierung erhalten.

## Schnelle Antworten
- **Was macht Aspose.Tasks für Java?** Es liest und schreibt viele Projektdateiformate, einschließlich Primavera XML und Microsoft Project (MPP).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion eignet sich zur Evaluierung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher ist erforderlich.  
- **Kann ich neben Primavera XML weitere Formate importieren?** Ja, aspose tasks java unterstützt ebenfalls MPP, XML und viele weitere.  
- **Ist dieser Ansatz für große Unternehmensprojekte geeignet?** Absolut – Aspose.Tasks ist für Hochleistungs‑ und Unternehmensszenarien konzipiert.

## aspose tasks java – Lesen von Primavera XML
Das Lesen von Primavera XML bedeutet, den XML‑Export von Oracle Primavera P6 zu parsen, um Projektdaten wie Aufgaben, Dauern, Ressourcen und Primavera‑spezifische Attribute abzurufen, damit sie von anderen Tools wie Microsoft Project verwendet werden können.

## Warum Aspose.Tasks für Java zum Lesen von Primavera XML verwenden?
- **Vollständige Treue:** Alle Primavera‑spezifischen Eigenschaften bleiben erhalten.  
- **Keine externen Abhängigkeiten:** Reine Java‑Bibliothek, keine Installation von Primavera oder MS Project erforderlich.  
- **Skalierbar:** Verarbeitet große Projekte mit Tausenden von Aufgaben effizient.  
- **Plattformübergreifend:** Funktioniert unter Windows, Linux und macOS.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:
1. **Java Development Kit (JDK)** – Java 8 oder neuer installiert.  
2. **Aspose.Tasks for Java** – Laden Sie es von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. Eine Primavera‑XML‑Datei (z. B. `PrimaveraProject.xml`), die Sie lesen möchten.

## Wie liest man eine Projektdatei in Java mit Aspose.Tasks?
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die Sie durch den gesamten Vorgang führt.

### Pakete importieren
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Schritt 1: Datenverzeichnis einrichten
Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad, in dem sich Ihre Primavera‑XML‑Datei befindet.
```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projekt aus Primavera XML lesen
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Aktualisieren Sie `"PrimaveraProject.xml"` mit dem tatsächlichen Dateinamen Ihres Primavera‑Exports.

### Schritt 3: Durch Aufgaben iterieren und Primavera‑spezifische Eigenschaften abrufen
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
Diese Schleife gibt die Primavera‑spezifischen Details jeder Aufgabe aus, wie Aktivitäts‑ID, WBS‑Sequenz, Dauertypen, Kostenaufstellungen und mehr.

## Häufige Probleme und Lösungen
- **Fehler Datei nicht gefunden:** Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`/` oder `\\`) endet und der XML‑Dateiname korrekt ist.  
- **Fehlende Primavera‑Eigenschaften:** Vergewissern Sie sich, dass das XML mit allen erforderlichen Feldern exportiert wurde; ältere Primavera‑Versionen können einige Attribute weglassen.  
- **Leistung bei großen Dateien:** Erwägen Sie, die JVM‑Heap‑Größe (`-Xmx2g` oder höher) für Projekte mit Zehntausenden von Aufgaben zu erhöhen.

## Häufig gestellte Fragen
### Q: Kann ich die Primavera‑spezifischen Eigenschaften von Aufgaben mit Aspose.Tasks für Java ändern?
A: Ja, Aspose.Tasks für Java bietet APIs, um Primavera‑spezifische Eigenschaften von Aufgaben nach Bedarf zu ändern.

### Q: Unterstützt Aspose.Tasks für Java das Lesen anderer Projektdateiformate?
A: Ja, Aspose.Tasks für Java unterstützt das Lesen verschiedener Projektdateiformate, einschließlich MPP, XML und Primavera XML.

### Q: Ist Aspose.Tasks für Java für Unternehmens‑Projektmanagement‑Anwendungen geeignet?
A: Absolut, Aspose.Tasks für Java bietet robuste Funktionen und Skalierbarkeit, wodurch es für Unternehmens‑Projektmanagement‑Anwendungen geeignet ist.

### Q: Kann ich Ressourceninformationen aus Primavera‑Projekten mit Aspose.Tasks für Java extrahieren?
A: Ja, Aspose.Tasks für Java ermöglicht das Extrahieren von Ressourceninformationen zusammen mit Aufgabendetails aus Primavera‑Projekten.

### Q: Wo finde ich zusätzliche Unterstützung oder Dokumentation für Aspose.Tasks für Java?
A: Sie finden umfassende Dokumentation und Zugriff auf Support‑Foren auf der Seite [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Fazit
Sie haben nun gelernt, **wie man Primavera‑XML**‑Dateien liest und detaillierte Aufgabendaten in eine Java‑Anwendung mit **aspose tasks java** übernimmt. Diese Fähigkeit schließt die Lücke zwischen Primavera und Microsoft Project, bietet Ihnen vollständige Sichtbarkeit über Plattformen hinweg und steigert die Gesamteffizienz des Projektmanagements.

---

**Zuletzt aktualisiert:** 2026-04-24  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
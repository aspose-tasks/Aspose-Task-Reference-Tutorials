---
title: Überwachen Sie Überstunden, verbleibende Kosten und Arbeit in Aspose.Tasks
linktitle: Überwachen Sie Überstunden, verbleibende Kosten und Arbeit in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks Überstunden, Restkosten und Arbeit in Java-Projekten überwachen. Einfache Schritte für ein effektives Projektmanagement.
weight: 18
url: /de/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Überwachen Sie Überstunden, verbleibende Kosten und Arbeit in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java Überstunden, verbleibende Kosten und die Arbeit in einem Projekt überwachen. Dies kann für Projektmanager und Teamleiter von unschätzbarem Wert sein, um sicherzustellen, dass Projekte auf Kurs und innerhalb des Budgets bleiben.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java Development Kit (JDK): Aspose.Tasks für Java erfordert Java SE 6 oder höher.
2.  Aspose.Tasks für Java-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/java/).
3. Integrierte Entwicklungsumgebung (IDE): Jede Java-IDE wie Eclipse, IntelliJ IDEA oder NetBeans.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihre Java-Datei:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Schritt 1: Richten Sie das Datenverzeichnis ein
Definieren Sie das Verzeichnis, in dem sich Ihre Projektdatei befindet:
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrer Projektdatei.
## Schritt 2: Laden Sie das Projekt
 Instanziieren Sie a`Project` Objekt und laden Sie die Projektdatei:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Ersetzen`"ResourceAssignmentOvertimes.mpp"` mit dem Namen Ihrer Projektdatei.
## Schritt 3: Durchlaufen Sie die Ressourcenzuweisungen
Durchlaufen Sie jede Ressourcenzuweisung im Projekt:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Schritt 4: Überstundenkosten und Arbeit drucken
Überstundenkosten und Arbeit für jede Ressourcenzuweisung abrufen und ausdrucken:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Schritt 5: Verbleibende Kosten und Arbeit ausdrucken
Restkosten und Arbeit für jede Ressourcenzuweisung abrufen und ausdrucken:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Schritt 6: Verbleibende Überstundenkosten und Arbeit ausdrucken
Rufen Sie verbleibende Überstundenkosten und Arbeit für jede Ressourcenzuweisung ab und drucken Sie sie aus:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Abschluss
Die Überwachung von Überstunden, Restkosten und Arbeit in einem Projekt ist entscheidend für ein erfolgreiches Projektmanagement. Mit Aspose.Tasks für Java können Sie einfach auf diese Informationen zugreifen und sie verfolgen, um sicherzustellen, dass Ihre Projekte im Zeitplan und innerhalb des Budgets bleiben.
## FAQs
### Kann ich Aspose.Tasks für Java mit anderen Java-Bibliotheken verwenden?
Ja, Aspose.Tasks für Java ist mit anderen Java-Bibliotheken und Frameworks kompatibel.
### Unterstützt Aspose.Tasks verschiedene Projektdateiformate?
Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate, darunter MPP, XML und mehr.
### Gibt es eine Testversion?
 Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung, wenn ich auf Probleme stoße?
 Sie können das Aspose.Tasks-Forum besuchen[Hier](https://forum.aspose.com/c/tasks/15) zur Unterstützung.
### Wie kann ich eine Lizenz für Aspose.Tasks erwerben?
 Sie können eine Lizenz kaufen bei[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

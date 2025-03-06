---
title: Stoppen und Fortsetzen von Ressourcenzuweisungen in Aspose.Tasks
linktitle: Stoppen und Fortsetzen von Ressourcenzuweisungen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie Ressourcenzuweisungen in Aspose.Tasks für Java effektiv verwalten.
weight: 23
url: /de/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stoppen und Fortsetzen von Ressourcenzuweisungen in Aspose.Tasks

## Einführung
In diesem Tutorial erfahren Sie, wie Sie Ressourcenzuweisungen mit Aspose.Tasks für Java stoppen und fortsetzen. Aspose.Tasks ist eine leistungsstarke Java-API, die es Entwicklern ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project auf ihren Systemen installiert sein muss. Wir unterteilen den Prozess in überschaubare Schritte, damit er leicht nachvollziehbar ist.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Tasks für Java-Bibliothek heruntergeladen. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).
- Grundlegendes Verständnis der Java-Programmierung.
## Pakete importieren
Importieren wir zunächst die notwendigen Pakete in unser Java-Projekt:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Schritt 1: Laden Sie die Projektdatei
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
// Laden Sie die Projektdatei
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 In diesem Schritt laden wir die Projektdatei in eine`Project` Objekt mithilfe des Dateipfads.
## Schritt 2: Durchlaufen Sie die Ressourcenzuweisungen
```java
// Mindesttermin festlegen
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Durchlaufen Sie Ressourcenzuweisungen
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Hier definieren wir ein Mindestdatum und beginnen mit der Iteration durch jede Ressourcenzuweisung im Projekt.
## Schritt 3: Überprüfen Sie die Stopp- und Wiederaufnahmedaten
```java
    // Überprüfen Sie das Stoppdatum
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Überprüfen Sie das Lebenslaufdatum
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
In diesem Schritt prüfen wir, ob die Stopp- und Wiederaufnahmedaten jeder Ressourcenzuweisung vor dem Mindestdatum liegen. Wenn ja, drucken wir „NA“, andernfalls drucken wir die entsprechenden Daten.
## Abschluss
In diesem Tutorial haben wir gelernt, wie man Ressourcenzuweisungen in Aspose.Tasks für Java stoppt und fortsetzt. Wenn Sie die bereitgestellten Schritte befolgen, können Sie diese Funktionalität problemlos in Ihren Java-Projekten implementieren.

## FAQs
### Kann ich Aspose.Tasks verwenden, ohne dass Microsoft Project installiert ist?
Ja, mit Aspose.Tasks können Sie mit Microsoft Project-Dateien arbeiten, ohne dass Microsoft Project auf Ihrem System installiert sein muss.
### Wo finde ich weitere Dokumentation?
 Eine ausführliche Dokumentation finden Sie hier[Hier](https://reference.aspose.com/tasks/java/).
### Gibt es eine kostenlose Testversion?
 Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### Wie kann ich Unterstützung erhalten, wenn ich auf Probleme stoße?
Sie können Unterstützung von der Community erhalten[Hier](https://forum.aspose.com/c/tasks/15).
### Kann ich eine temporäre Lizenz erwerben?
 Ja, Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Behandeln Sie die Eigenschaften der Ausgleichsverzögerung in Aspose.Tasks
linktitle: Behandeln Sie die Eigenschaften der Ausgleichsverzögerung für Ressourcenzuweisungen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie in diesem umfassenden Tutorial, wie Sie mit Nivellierungsverzögerungseigenschaften für Ressourcenzuweisungen in Aspose.Tasks für Java umgehen.
type: docs
weight: 17
url: /de/java/resource-assignments/leveling-delay-properties/
---
## Einführung
In diesem Tutorial führen wir den Prozess der Handhabung von Nivellierungsverzögerungseigenschaften für Ressourcenzuweisungen in Aspose.Tasks für Java durch. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die es Ihnen ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project auf Ihrem System installiert sein muss.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass Java JDK auf Ihrem System installiert ist. Sie können es herunterladen und installieren[Webseite](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks für Java-Bibliothek: Laden Sie die Aspose.Tasks für Java-Bibliothek von herunter[Download-Seite](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt, um die Funktionen von Aspose.Tasks zu nutzen:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Schritt 1: Erstellen Sie ein Projektobjekt
 Instanziieren Sie a`Project` Objekt:
```java
Project prj = new Project();
```
## Schritt 2: Erstellen Sie eine Aufgabe
Fügen Sie dem Projekt eine Aufgabe hinzu:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Schritt 3: Legen Sie das Startdatum und die Dauer der Aufgabe fest
Legen Sie das Startdatum und die Dauer der Aufgabe fest:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Schritt 4: Fügen Sie eine Ressource hinzu
Fügen Sie dem Projekt eine Ressource hinzu:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Schritt 5: Erstellen Sie eine Ressourcenzuweisung
Erstellen Sie eine Ressourcenzuweisung für die Aufgabe und die Ressource:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Schritt 6: Nivellierungsverzögerung einstellen
Legen Sie die Nivellierungsverzögerung für die Aufgabe fest:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Schritt 7: Ergebnisse anzeigen
Drucken Sie die Nivellierungsverzögerung und andere relevante Informationen aus:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit den Eigenschaften der Ausgleichsverzögerung für Ressourcenzuweisungen in Aspose.Tasks für Java umgeht. Wenn Sie diese Schritte befolgen, können Sie Ressourcenzuweisungen in Ihren Java-Projekten effizient verwalten.
## FAQs
### F: Kann ich Aspose.Tasks mit anderen Java-Bibliotheken verwenden?

A: Ja, Aspose.Tasks kann in andere Java-Bibliotheken integriert werden, um die Projektmanagementfunktionen zu verbessern.

### F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project-Dateien kompatibel?

A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project-Dateien und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.

### F: Wo finde ich zusätzliche Unterstützung für Aspose.Tasks?

 A: Unterstützung und Ressourcen finden Sie auf der[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).

### F: Kann ich Aspose.Tasks vor dem Kauf testen?

 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks erhalten[Veröffentlichungsseite](https://releases.aspose.com/).

### F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?

 A: Sie können eine temporäre Lizenz bei der beantragen[temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/) zu Auswertungszwecken.
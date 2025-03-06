---
title: Verwalten Sie MS Project-Eigenschaften effizient in Aspose.Tasks
linktitle: Verwalten Sie Standardprojekteigenschaften in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Standardeigenschaften von MS Project mit Aspose.Tasks für Java verwalten. Optimieren Sie mühelos Ihren Projektmanagement-Workflow.
type: docs
weight: 11
url: /de/java/project-management/default-properties/
---
## Einführung
Möchten Sie Ihren Projektmanagementprozess mit Aspose.Tasks für Java optimieren? Das Verwalten von Standardeigenschaften in Microsoft Project-Dateien kann die Effizienz erheblich steigern. In diesem Tutorial führen wir Sie Schritt für Schritt durch, wie Sie Standardeigenschaften von MS Project mithilfe von Aspose.Tasks verwalten.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Java Development Kit (JDK)
   - Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
   -  Sie können es herunterladen unter[Hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks für Java-Bibliothek
   - Laden Sie die Aspose.Tasks für Java-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein.
   -  Sie können es hier herunterladen[Webseite](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihre Java-Datei:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Lassen Sie uns den Prozess in überschaubare Schritte unterteilen:
## Schritt 1: Projektdatei laden
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Schritt 2: Standardeigenschaften anzeigen
```java
// Standardeigenschaften anzeigen
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Schritt 3: Standardeigenschaften festlegen
```java
// Legen Sie Standardeigenschaften fest
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Schritt 4: Projekt im XML-Format speichern
```java
// Speichern Sie das Projekt im XML-Format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Schritt 5: Ergebnis anzeigen
```java
// Ergebnis der Konvertierung anzeigen.
System.out.println("Process completed Successfully");
```
Wenn Sie diese Schritte befolgen, können Sie Standardeigenschaften von MS Project mithilfe von Aspose.Tasks für Java effizient verwalten.
## Abschluss
In diesem Tutorial haben wir gelernt, wie man Standardeigenschaften von MS Project mit Aspose.Tasks für Java verwaltet. Durch den Einsatz dieser Techniken können Sie Ihren Projektmanagement-Workflow optimieren und so Produktivität und Organisation steigern.
## FAQs
### F1: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?
A1: Ja, Aspose.Tasks unterstützt verschiedene Programmiersprachen wie .NET, Python und Java.
### F2: Ist Aspose.Tasks sowohl für den persönlichen als auch für den geschäftlichen Gebrauch geeignet?
A2: Auf jeden Fall! Egal, ob Sie kleine persönliche Projekte oder große Unternehmensinitiativen verwalten, Aspose.Tasks ist für jeden etwas dabei.
### F3: Bietet Aspose.Tasks Kundensupport?
A3: Ja, Hilfe und Community-Unterstützung finden Sie auf der[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
### F4: Kann ich Aspose.Tasks vor dem Kauf ausprobieren?
 A4: Natürlich! Sie können eine kostenlose Testversion von der nutzen[Webseite](https://releases.aspose.com/).
### F5: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?
 A5: Sie können eine temporäre Lizenz von erhalten[Kaufseite](https://purchase.aspose.com/temporary-license/) zu Test- und Evaluierungszwecken.
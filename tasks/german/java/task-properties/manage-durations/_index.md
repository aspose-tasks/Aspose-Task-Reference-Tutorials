---
title: Verwalten Sie die Dauer von Aufgaben in Aspose.Tasks
linktitle: Verwalten Sie die Dauer von Aufgaben in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Entdecken Sie Aspose.Tasks für Java und lernen Sie, die Dauer von Aufgaben mühelos zu verwalten. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine effektive Projektplanung und -durchführung.
weight: 20
url: /de/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten Sie die Dauer von Aufgaben in Aspose.Tasks

## Einführung
Aspose.Tasks für Java bietet eine robuste Lösung für die effiziente Verwaltung von Projektaufgaben und -dauern. In diesem Tutorial erfahren Sie, wie Sie die Dauer von Aufgaben mit Aspose.Tasks verwalten und führen Sie durch die einzelnen Schritte. Unabhängig davon, ob Sie ein erfahrener Entwickler oder ein Anfänger sind, hilft Ihnen dieser Leitfaden dabei, die Grundlagen der Arbeit mit Aufgabendauern in Ihren Projekten zu verstehen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem Computer installiert ist. Sie können es herunterladen[Hier](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein. Sie finden die Bibliothek[Hier](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete, um mit Aspose.Tasks zu arbeiten:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Schritt 1: Richten Sie Ihr Projekt ein
```java
// Erstellen Sie ein neues Projekt
Project project = new Project();
```
## Schritt 2: Fügen Sie eine neue Aufgabe hinzu
```java
// Fügen Sie dem Projekt eine neue Aufgabe hinzu
Task task = project.getRootTask().getChildren().add("Task");
```
## Schritt 3: Aufgabendauer abrufen und konvertieren
```java
// Aufgabendauer in Tagen abrufen (Standardzeiteinheit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Konvertieren Sie die Dauer in die Zeiteinheit Stunden
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Schritt 4: Aktualisieren Sie die Aufgabendauer auf 1 Woche
```java
// Erhöhen Sie die Aufgabendauer auf 1 Woche
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Schritt 5: Verringern Sie die Aufgabendauer
```java
// Verringern Sie die Aufgabendauer
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Durch Befolgen dieser Schritte haben Sie die Dauer der Aufgaben in Ihrem Aspose.Tasks für Java-Projekt erfolgreich verwaltet.
## Abschluss
In diesem Tutorial haben wir die Grundlagen der Verwaltung von Aufgabendauern mit Aspose.Tasks für Java behandelt. Jetzt können Sie diese Techniken sicher in Ihre Projekte integrieren, um die Aufgabendauer effektiv zu verwalten.
## FAQs
### Ist Aspose.Tasks mit allen Java-Versionen kompatibel?
Aspose.Tasks ist mit Java 6 und späteren Versionen kompatibel.
### Kann ich Aspose.Tasks für kommerzielle Projekte verwenden?
 Ja, Sie können Aspose.Tasks sowohl für persönliche als auch für kommerzielle Projekte verwenden. Besuchen[Hier](https://purchase.aspose.com/buy) für Lizenzdetails.
### Wo finde ich zusätzliche Unterstützung und Ressourcen?
 Besuche den[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und Diskussionen.
### Wie kann ich eine temporäre Lizenz zu Testzwecken erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zum Testen und Bewerten.
### Gibt es eine kostenlose Testversion für Aspose.Tasks?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/) um Aspose.Tasks zu erkunden, bevor Sie einen Kauf tätigen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Berechnungen des Prozentsatzes der abgeschlossenen Aufgaben für Aufgaben in Aspose.Tasks
linktitle: Berechnungen des Prozentsatzes der abgeschlossenen Aufgaben für Aufgaben in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Entdecken Sie Aspose.Tasks für Java und optimieren Sie die Verfolgung des Projektfortschritts. Berechnen Sie mühelos Aufgabenprozentsätze für ein effizientes Projektmanagement.
weight: 25
url: /de/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Berechnungen des Prozentsatzes der abgeschlossenen Aufgaben für Aufgaben in Aspose.Tasks

## Einführung
Willkommen zu unserem ausführlichen Leitfaden zum Beherrschen von Aufgabenprozentsatzberechnungen mit Aspose.Tasks für Java. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die für die Arbeit mit Microsoft Project-Dateien entwickelt wurde und eine Reihe robuster Funktionen für das Projektmanagement bietet. In diesem Tutorial konzentrieren wir uns auf die Berechnung des Prozentsatzes der abgeschlossenen Arbeiten und vermitteln Ihnen das Wissen, um den Projektfortschritt effektiv zu überwachen und zu analysieren.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java-Entwicklungsumgebung: Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
-  Aspose.Tasks-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek für Java herunter von[dieser Link](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Beginnen wir mit dem Importieren der erforderlichen Pakete für Ihr Aspose.Tasks für Java-Projekt. Fügen Sie den folgenden Codeausschnitt in Ihr Projekt ein:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Lassen Sie uns nun jeden Schritt mit detaillierten Erklärungen aufschlüsseln.
## Schritt 1: Pakete importieren
Im ersten Schritt importieren wir die notwendigen Pakete, um unser Aspose.Tasks-Projekt einzurichten.
## Schritt 2: Dokumentverzeichnis festlegen
 Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis mit`dataDir`Variable. Stellen Sie sicher, dass sich Ihre Microsoft Project-Datei, z. B. „Software Development.mpp“, in diesem Verzeichnis befindet.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
```
## Schritt 3: Laden des Projekts
 Initialisieren Sie eine neue`Project` Objekt und laden Sie Ihre Microsoft Project-Datei in die Projektinstanz.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Schritt 4: Aufgabensammlung abrufen
 Rufen Sie die Stammaufgabe des Projekts ab und rufen Sie seine untergeordneten Aufgaben als Sammlung ab`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Schritt 5: Prozentsatz der Fertigstellung drucken
Durchlaufen Sie jede Aufgabe in der Sammlung und drucken Sie den Fertigstellungsgrad, den Prozentsatz der abgeschlossenen Arbeit und den Prozentsatz der physischen Fertigstellung aus.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Wiederholen Sie diese Schritte für jede Aufgabe in Ihrem Projekt, um Einblicke in den Fortschritt der einzelnen Aufgaben zu erhalten.
## Abschluss
Glückwunsch! Sie haben die Aufgabenprozentsatzberechnung mit Aspose.Tasks für Java erfolgreich gemeistert. Diese leistungsstarke Bibliothek ermöglicht Entwicklern die effiziente Verwaltung und Analyse des Projektfortschritts.
## FAQs
### F: Wo finde ich die Aspose.Tasks-Dokumentation?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/tasks/java/).
### F: Wie kann ich die Aspose.Tasks-Bibliothek für Java herunterladen?
 Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/java/).
### F: Gibt es eine kostenlose Testversion?
Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wo kann ich Unterstützung für Aspose.Tasks erhalten?
 Besuchen Sie das Support-Forum[Hier](https://forum.aspose.com/c/tasks/15).
### F: Wie erhalte ich eine temporäre Lizenz?
 Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

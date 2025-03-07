---
title: Mit der Aufgabe in Aspose.Tasks verknüpfter PSP
linktitle: Mit der Aufgabe in Aspose.Tasks verknüpfter PSP
second_title: Aspose.Tasks Java-API
description: Master-PSP mit Aspose.Tasks für Java – Lernen Sie, Aufgaben-PSP-Codes zu lesen und neu zu nummerieren. Steigern Sie die Effizienz Ihres Projektmanagements!
weight: 36
url: /de/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mit der Aufgabe in Aspose.Tasks verknüpfter PSP

## Einführung
Willkommen in der Welt des Projektmanagements mit Aspose.Tasks für Java! In diesem Tutorial befassen wir uns mit den Feinheiten des Projektstrukturplans (WBS), der mit Aufgaben verbunden ist, die Aspose.Tasks für Java verwenden. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, hilft Ihnen dieser Leitfaden dabei, sich durch die Grundlagen der effizienten Verwaltung von WBS-Codes zu navigieren.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
-  Aspose.Tasks für Java-Bibliothek heruntergeladen und Ihrem Projekt hinzugefügt. Sie können es von bekommen[Hier](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Pakete importieren, um Ihr Projekt zu starten:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Lesen Sie WBS-Codes
Beginnen wir mit dem Lesen der WBS-Codes, die den Aufgaben zugeordnet sind. Folge diesen Schritten:
## Schritt 1: Laden Sie das Projekt
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Schritt 2: Aufgaben sammeln
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Schritt 3: Analysieren und anpassen
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Dieses Snippet liest und passt WBS-Codes an, die mit Aufgaben in Ihrem Projekt verknüpft sind.
## Aufgaben-PSP-Codes neu nummerieren
Sehen wir uns nun die Neunummerierung von WBS-Codes für Aufgaben an:
## Schritt 1: Laden Sie das Projekt
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Schritt 2: Wählen Sie „Alle Aufgaben“ aus
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Schritt 3: Ausgangs-PSP-Codes ausgeben
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Schritt 4: WBS-Codes neu nummerieren
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Schritt 5: Aktualisierte WBS-Codes ausgeben
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Wenn Sie diese Schritte befolgen, nummerieren Sie die WBS-Codes für Aufgaben in Ihrem Projekt effektiv neu.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Tasks für Java mit WBS-Codes arbeiten. Mit diesem Wissen können Sie die Aufgabenhierarchie Ihres Projekts effizient verwalten und anpassen.
## FAQs
### F: Wo finde ich die Dokumentation für Aspose.Tasks für Java?
 A: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/tasks/java/).
### F: Wie kann ich Aspose.Tasks für Java herunterladen?
 A: Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/java/).
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### F: Wo erhalte ich Unterstützung für Aspose.Tasks für Java?
 A: Besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) zur Unterstützung.
### F: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?
 A: Ja, besorgen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-03-03
description: Erfahren Sie, wie Sie WBS in Aspose.Tasks für Java neu nummerieren, die
  Arbeitsstruktur verwalten und WBS‑Codes effizient mit Schritt‑für‑Schritt‑Beispielen
  anpassen.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man die WBS in Aspose.Tasks für Java neu nummeriert
url: /de/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man WBS in Aspose.Tasks für Java neu nummeriert

## Einführung
Wenn Sie **wie man WBS neu nummeriert** in einer Microsoft Project-Datei mit Aspose.Tasks für Java benötigen, sind Sie hier genau richtig. Dieses Tutorial führt Sie durch das Lesen vorhandener WBS-Codes, deren Anpassung und anschließend das Neu‑Nummerieren der Hierarchie, damit Ihr Projekt organisiert bleibt. Egal, ob Sie einen Legacy‑Zeitplan bereinigen oder einen neuen von Grund auf erstellen, das Beherrschen dieser Schritte hilft Ihnen, **Work Breakdown Structures** mit Zuversicht zu verwalten.

## Schnelle Antworten
- **Was bewirkt das Neu‑Nummerieren von WBS?** Es berechnet die hierarchische Nummerierung von Aufgaben neu, um strukturelle Änderungen widerzuspiegeln.  
- **Welche Klasse führt das Neu‑Nummerieren durch?** `Project.renumberWBSCode`.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich das WBS‑Format anpassen?** Ja – verwenden Sie `Task.set(Tsk.WBS, "...")`, um eine beliebige Zeichenkette zuzuweisen.  
- **Was sind die wichtigsten Voraussetzungen?** Java JDK, Aspose.Tasks für Java‑Bibliothek und eine gültige Projektdatei (.mpp).

## Was ist eine Work Breakdown Structure (WBS)?
Eine Work Breakdown Structure (WBS) ist eine hierarchische Darstellung der Lieferobjekte und Aufgaben eines Projekts. Jeder Aufgabe wird ein Code zugewiesen (z. B. 1.2.3), der ihre Position in der Hierarchie widerspiegelt. Das Neu‑Nummerieren wird wichtig, wenn Aufgaben hinzugefügt, entfernt oder neu angeordnet werden, damit die Codes logisch und leicht lesbar bleiben.

## Warum Work Breakdown verwalten und WBS‑Codes anpassen?
- **Klarheit:** Klare WBS‑Codes erleichtern es den Stakeholdern, Aufgaben zu finden.  
- **Reporting:** Viele Reporting‑Tools basieren auf konsistenter Nummerierung.  
- **Flexibilität:** Benutzerdefinierte Codes ermöglichen es, die Projektstruktur an interne Standards anzupassen.  

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Tasks für Java‑Bibliothek zu Ihrem Projekt hinzugefügt. Sie können sie von [hier](https://releases.aspose.com/tasks/java/) erhalten.  

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

## WBS‑Codes lesen
Zuerst lesen wir die vorhandenen WBS‑Codes, damit Sie sehen, womit Sie arbeiten.

### Schritt 1: Projekt laden
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Schritt 2: Aufgaben sammeln
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Schritt 3: Analysieren und Anpassen
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Das obige Snippet gibt den aktuellen WBS und das Level jeder Aufgabe aus und demonstriert dann das **Anpassen von WBS‑Codes**, indem ein neuer String zugewiesen wird.

## Aufgaben‑WBS‑Codes neu nummerieren
Nun nummerieren wir die WBS‑Hierarchie tatsächlich neu.

### Schritt 1: Projekt laden (Beispiel für Neu‑Nummerierung)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Schritt 2: Alle Aufgaben auswählen
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Schritt 3: Anfangs‑WBS‑Codes ausgeben
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Schritt 4: WBS‑Codes neu nummerieren
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Schritt 5: Aktualisierte WBS‑Codes ausgeben
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Wenn Sie diese Schritte befolgen, können Sie **wie man WBS neu nummeriert** für jede Aufgabenmenge in Ihrer Projektdatei effektiv anwenden.

## Häufige Probleme und Lösungen
- **WBS ändert sich nach dem `set`‑Aufruf nicht:** Stellen Sie sicher, dass Sie mit der richtigen Aufgabeninstanz arbeiten und das Projekt nach den Änderungen gespeichert wird.  
- **`renumberWBSCode` wirft eine Ausnahme:** Prüfen Sie, ob die ID‑Liste mit der Anzahl der obersten Aufgaben übereinstimmt; andernfalls kann die Methode die neuen Nummern nicht korrekt zuordnen.  
- **Fehlende WBS‑Werte:** Einige Aufgaben können ein `null`‑WBS haben, wenn sie aus einer Datei importiert wurden, die keinen definiert hat. Verwenden Sie vor dem Ausgeben einen Ersatzwert.  

## Häufig gestellte Fragen

**F: Wo finde ich die Dokumentation für Aspose.Tasks für Java?**  
A: Die Dokumentation ist [hier](https://reference.aspose.com/tasks/java/) verfügbar.

**F: Wie kann ich Aspose.Tasks für Java herunterladen?**  
A: Sie können es [hier](https://releases.aspose.com/tasks/java/) herunterladen.

**F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**F: Wo kann ich Support für Aspose.Tasks für Java erhalten?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Support.

**F: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?**  
A: Ja, erhalten Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

**F: Kann ich das WBS‑Format nach dem Neu‑Nummerieren umbenennen?**  
A: Absolut. Nach dem Aufruf von `renumberWBSCode` können Sie über die Aufgaben iterieren und `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` anwenden, um Ihre Namenskonventionen zu erfüllen.

**F: Wirkt sich das Neu‑Nummerieren auf Aufgabenabhängigkeiten aus?**  
A: Nein. Die Methode aktualisiert nur den WBS‑String; Aufgabenverknüpfungen und -einschränkungen bleiben unverändert.

---

**Zuletzt aktualisiert:** 2026-03-03  
**Getestet mit:** Aspose.Tasks für Java 24.12 (neueste)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
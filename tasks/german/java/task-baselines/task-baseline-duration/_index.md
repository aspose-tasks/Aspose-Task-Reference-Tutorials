---
date: 2026-01-23
description: Erfahren Sie, wie Sie die Basisliniendauer festlegen und ein Projektinstanz
  mit Aspose.Tasks für Java erstellen. Diese Schritt‑für‑Schritt‑Anleitung hilft Ihnen,
  Aufgabenbaselines effizient zu verwalten.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Wie man die Basisliniendauer in Aspose.Tasks für Java festlegt
url: /de/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Basisliniendauer in Aspose.Tasks für Java festlegt

## Einführung
Das Festlegen einer Basislinie ist ein grundlegender Schritt, um den Projektfortschritt mit dem ursprünglichen Plan zu vergleichen. In diesem Tutorial lernen Sie **wie man die Basisliniendauer** für Aufgaben in Microsoft Project mit der Aspose.Tasks‑Bibliothek für Java festlegt und erfahren, warum das frühe Festlegen einer Basislinie Ihnen später Zeit und Kopfschmerzen ersparen kann.

## Schnelle Antworten
- **Was bedeutet „Baseline festlegen“?** Sie zeichnet den ursprünglichen Start, das Ende und die Dauer einer Aufgabe auf, sodass Sie zukünftige Änderungen vergleichen können.  
- **Welche Aspose.Tasks‑Klasse erstellt ein Projekt?** Die `Project`‑Klasse – Sie erfahren außerdem, wie man **ein Projekt‑Objekt korrekt erstellt**.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Evaluierungslizenz reicht für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Zwischensbaseline abrufen?** Ja, Aspose.Tasks ermöglicht das Abfragen von Zwischensbaselines und deren Festkosten.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher wird empfohlen.

## Was ist eine Aufgaben‑Baseline und warum sie setzen?
Eine Aufgaben‑Baseline erfasst den geplanten Zeitplan (Startdatum, Enddatum und Dauer) zu einem bestimmten Zeitpunkt. Durch das Festlegen einer Basislinie schaffen Sie einen Referenzpunkt, der es leicht macht, Terminabweichungen, Kostenüberschreitungen und Ressourcenüberlastungen zu erkennen, während das Projekt voranschreitet.

## Warum Aspose.Tasks für das Baseline‑Management verwenden?
- **Vollständige .mpp‑Kompatibilität** – Lesen und schreiben Sie native Microsoft‑Project‑Dateien, ohne dass Office installiert sein muss.  
- **Umfangreiche API** – Greifen Sie programmgesteuert auf Baseline‑Daten, Zwischensbaselines und zeitphasenbezogene Informationen zu.  
- **Plattformübergreifend** – Funktioniert unter Windows, Linux und macOS mit jedem gängigen JDK.

## Voraussetzungen
1. **Java‑Entwicklungsumgebung** – JDK 8+ installiert und konfiguriert.  
2. **Aspose.Tasks für Java** – Laden Sie die Bibliothek von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE oder Build‑Tool** – Maven, Gradle oder jede IDE Ihrer Wahl.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Klassen in Ihr Java‑Projekt:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Schritt 1: Ein Projekt‑Objekt erstellen
Ein Projekt‑Objekt zu erstellen ist die Grundlage für jede weitere Manipulation. Dieser Schritt zeigt, wie man **ein Projekt‑Objekt** mit Aspose.Tasks erstellt:

```java
Project project = new Project();
```

## Schritt 2: Eine Aufgaben‑Baseline erstellen
Fügen Sie dem Projekt‑Root eine neue Aufgabe hinzu und setzen Sie deren Basislinie. Damit wird der ursprüngliche Zeitplan für die Aufgabe gespeichert:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Schritt 3: Aufgaben‑Baseline‑Informationen anzeigen
Rufen Sie die gerade erstellte Basislinie ab und geben Sie deren wichtige Eigenschaften aus. So stellen Sie sicher, dass die Basislinie korrekt gesetzt wurde:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Schritt 4: Zwischensbaseline und Festkosten prüfen
Arbeiten Sie mit Zwischensbaselines, können Sie abfragen, ob die aktuelle Basislinie eine Zwischensbaseline ist und welche Festkosten ggf. zugeordnet sind:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Schritt 5: Zeitphasen‑Daten ausgeben
Zeitphasen‑Daten zeigen, wie die Basislinie über die Zeit verteilt ist. Durchlaufen Sie die Sammlung, um jeden Eintrag zu inspizieren:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Wenn Sie diese Schritte befolgen, können Sie **wie man die Basisliniendauer** für jede Aufgabe festlegt und detaillierte Baseline‑Informationen mit Aspose.Tasks für Java abrufen.

## Häufige Probleme und Lösungen
- **Baseline erscheint nicht in MS Project:** Stellen Sie sicher, dass Sie `project.setBaseline(BaselineType.Baseline)` **nach** dem Hinzufügen der Aufgabe aufgerufen haben.  
- **NullPointerException bei `getBaselines()`:** Vergewissern Sie sich, dass die Aufgabe dem Projekt hinzugefügt wurde, bevor die Basislinie gesetzt wird.  
- **Zeit‑Einheit‑Mismatch:** Verwenden Sie `TimeUnitType`, um die Dauer korrekt zu formatieren, insbesondere bei benutzerdefinierten Kalendern.

## FAQ's
### Was ist eine Aufgaben‑Baseline in MS Project?
Eine Aufgaben‑Baseline in MS Project ist ein Schnappschuss des ursprünglich geplanten Zeitplans einer Aufgabe, einschließlich Startdatum, Enddatum und Dauer.

### Warum ist das Verwalten von Aufgaben‑Baselines wichtig?
Das Verwalten von Aufgaben‑Baselines erleichtert den Vergleich des geplanten Zeitplans mit dem tatsächlichen Projektfortschritt und unterstützt ein besseres Tracking sowie fundierte Entscheidungen.

### Kann ich eine Aufgaben‑Baseline nach dem Setzen ändern?
Ja, Sie können Aufgaben‑Baselines in MS Project ändern, um Anpassungen im Projektplan widerzuspiegeln. Es ist jedoch wichtig, Abweichungen von der ursprünglichen Basislinie zu dokumentieren.

### Unterstützt Aspose.Tasks weitere Projektmanagement‑Funktionen?
Ja, Aspose.Tasks bietet ein breites Spektrum an Funktionen für das Projektmanagement, einschließlich Aufgabenplanung, Ressourcenallokation und Gantt‑Diagrammerstellung.

### Wo finde ich Support für Aspose.Tasks?
Support für Aspose.Tasks finden Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15), wo Sie Fragen stellen und sich mit anderen Nutzern austauschen können.

## Weitere häufig gestellte Fragen
**F: Muss ich `setBaseline` für jede Aufgabe einzeln aufrufen?**  
A: Nein. Der Aufruf von `project.setBaseline(BaselineType.Baseline)` zeichnet die Basislinie für alle Aufgaben im Projekt gleichzeitig auf.

**F: Wie kann ich eine Zwischensbaseline für eine bestimmte Aufgabe festlegen?**  
A: Verwenden Sie `project.setBaseline(BaselineType.Baseline1)` (oder Baseline2‑Baseline10) nach der Aktualisierung des Aufgaben‑Zeitplans.

**F: Ist es möglich, die Baseline‑Daten als CSV zu exportieren?**  
A: Ja. Durchlaufen Sie `task.getBaselines()` und schreiben Sie die gewünschten Felder mit Standard‑Java‑I/O in eine CSV‑Datei.

**F: Kann ich eine bereits vorhandene .mpp‑Datei einlesen, die Baselines enthält?**  
A: Absolut. Laden Sie die Datei mit `new Project("myproject.mpp")` und greifen Sie anschließend auf die Baselines jeder Aufgabe zu, wie oben gezeigt.

**F: Unterstützt Aspose.Tasks Multi‑Projekt‑Dateien?**  
A: Aspose.Tasks arbeitet mit einzelnen .mpp‑Dateien. Für Multi‑Projekt‑Szenarien kombinieren Sie die Projekte programmgesteuert.

---

**Zuletzt aktualisiert:** 2026-01-23  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
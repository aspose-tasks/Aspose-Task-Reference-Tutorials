---
date: 2025-12-21
description: Erfahren Sie, wie Sie Gantt‑Diagrammansichten anpassen, die Projektvisualisierung
  verwalten und das Projekt mit Aspose.Tasks für Java als PDF speichern. Passen Sie
  die Zeitskalenanzahl mühelos an.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gantt-Diagramm anpassen – Meistern der Zeitachsen‑Anzahl von MS Project in
  Aspose.Tasks
url: /de/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gantt-Diagramm anpassen – Zeitmaßstab‑Anzahl in MS Project mit Aspose.Tasks meistern

## Einführung
Wenn Sie die **Darstellung des Gantt‑Diagramms** in Microsoft Project anpassen möchten, ist die Steuerung der Zeitmaßstab‑Anzahl eine zentrale Technik. Mit Aspose.Tasks für Java können Sie programmgesteuert die untere und mittlere Zeitmaßstab‑Ebene festlegen, die Sichtbarkeit von Markierungen feinjustieren und anschließend **das Projekt als PDF speichern**, um es mit Stakeholdern zu teilen. Dieses Tutorial führt Sie durch den gesamten Prozess – von der Einrichtung der Umgebung bis zur Erstellung eines professionellen PDFs, das Ihre angepasste Gantt‑Ansicht widerspiegelt.

## Schnellantworten
- **Was bedeutet „Gantt‑Diagramm anpassen“?** Anpassen von Zeitmaßstab‑Ebenen, Farben und Layout, um Ihren Berichtserfordernissen zu entsprechen.  
- **Welche API‑Methode legt die untere Ebene fest?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Kann ich ein PDF direkt aus dem Projekt erzeugen?** Ja – verwenden Sie `project.save(..., SaveFileFormat.Pdf)`.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz ist erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher funktioniert mit der neuesten Aspose.Tasks‑Bibliothek.

## Was bedeutet „Gantt‑Diagramm anpassen“ in Aspose.Tasks?
Ein Gantt‑Diagramm anzupassen bedeutet, seine visuellen Komponenten programmgesteuert zu verändern – etwa Zeitmaßstab‑Intervalle, Markierungen und Aufgabenbalken – sodass das Diagramm Ihrer gewünschten **Projektvisualisierung** entspricht. Durch Ändern der Zeitmaßstab‑Anzahl bestimmen Sie, wie viele Tage, Wochen oder Monate jedes Segment darstellt, wodurch das Diagramm für unterschiedliche Zielgruppen klarer wird.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8 oder neuer installiert.  
2. **Aspose.Tasks für Java Bibliothek** – Laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **Grundkenntnisse in Java** – Vertrautheit mit Java‑Syntax und objektorientierten Konzepten.

## Pakete importieren
Importieren Sie die notwendigen Klassen in Ihr Java‑Projekt:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis festlegen
Definieren Sie, von wo Ihre Projektdateien gelesen und wohin sie geschrieben werden:

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad auf Ihrem Rechner.

### Schritt 2: Neue Projektinstanz erstellen
Instanziieren Sie ein frisches `Project`‑Objekt, das alle Aufgaben und Ansichtseinstellungen enthält:

```java
Project project = new Project();
```

### Schritt 3: Gantt‑Diagramm‑Ansicht konfigurieren
Erzeugen Sie ein `GanttChartView`‑Objekt – hier werden Sie **Gantt‑Ansicht Java**‑Code erzeugen, um das Erscheinungsbild zu steuern:

```java
GanttChartView view = new GanttChartView();
```

### Schritt 4: Zeitmaßstab‑Anzahl für die untere Ebene festlegen
Passen Sie die untere Ebene an, um zwei Intervalle anzuzeigen und die Markierungen auszublenden:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Schritt 5: Zeitmaßstab‑Anzahl für die mittlere Ebene festlegen
Wenden Sie dieselbe Konfiguration auf die mittlere Ebene an:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Schritt 6: Angepasste Ansicht dem Projekt hinzufügen
Fügen Sie die gerade konfigurierte Ansicht dem `Project`‑Objekt hinzu:

```java
project.getViews().add(view);
```

### Schritt 7: Beispielaufgaben hinzufügen (Testdaten)
Erstellen Sie ein paar Aufgaben mit konkreten Dauern, um das angepasste Gantt‑Diagramm zu veranschaulichen:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Schritt 8: Projekt als PDF speichern
Exportieren Sie schließlich das Projekt – einschließlich Ihres **angepassten Gantt‑Diagramms** – in eine PDF‑Datei:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Das resultierende PDF zeigt, wie die untere und mittlere Zeitmaßstab‑Ebene **angepasst** wurden und bietet Stakeholdern eine klare, druckbare Ansicht des Zeitplans.

## Häufige Probleme & Fehlerbehebung
- **PDF ist leer** – Stellen Sie sicher, dass der `dataDir`‑Pfad mit einem Dateiseparator (`/` oder `\`) endet und das Verzeichnis existiert.  
- **Markierungen erscheinen weiterhin** – Prüfen Sie, ob `setShowTicks(false)` für beide Ebenen aufgerufen wurde.  
- **Dauer wurde nicht übernommen** – Vergewissern Sie sich, dass Sie `TimeUnitType.Hour` (oder die passende Einheit) beim Erzeugen von Dauern verwenden.

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks für Java große Projektdateien verarbeiten?**  
A: Ja, die Bibliothek ist für die Hochleistungs‑Verarbeitung umfangreicher Projektdaten optimiert.

**F: Ist Aspose.Tasks für Java mit verschiedenen Java‑IDEs kompatibel?**  
A: Absolut – es funktioniert nahtlos mit Eclipse, IntelliJ IDEA, NetBeans und anderen gängigen IDEs.

**F: Kann ich das Aussehen von Gantt‑Diagrammen über die Zeitmaßstab‑Einstellungen hinaus anpassen?**  
A: Ja, Aspose.Tasks bietet umfangreiche Styling‑Optionen wie Balkenfarben, Schriftarten und Gitternetzlinien.

**F: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) erhalten.

**F: Wo finde ich Support für Aspose.Tasks für Java?**  
A: Unterstützung und Hilfe finden Sie im Aspose.Tasks‑Forum [hier](https://forum.aspose.com/c/tasks/15).

**F: Wie ändere ich programmgesteuert die Hintergrundfarbe des Gantt‑Diagramms?**  
A: Verwenden Sie nach dem Import von `java.awt.Color` die Methode `view.getGanttChartProperties().setBackgroundColor(Color)`.

## Fazit
Durch Befolgen dieser Schritte haben Sie gelernt, wie Sie **Gantt‑Diagramm‑Zeitmaßstab‑Ebenen** anpassen, die **Projektvisualisierung** verbessern und das **Projekt als PDF speichern** mit Aspose.Tasks für Java. Dieser Ansatz gibt Ihnen volle Kontrolle über die visuelle Ausgabe, sodass Sie klare, professionelle Zeitpläne leicht mit Ihrem Team oder Kunden teilen können.

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
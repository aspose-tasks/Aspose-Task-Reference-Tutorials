---
date: 2026-03-29
description: Lernen Sie, wie Sie Projekt‑PDF‑Dateien erstellen und dabei die Zeitachsen‑Anzahl
  des Gantt‑Diagramms mit Aspose.Tasks für Java anpassen. Dieser Leitfaden zeigt Ihnen
  Schritt für Schritt, wie Sie Gantt in PDF exportieren und dabei die volle Kontrolle
  haben.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt-PDF erstellen – Gantt-Diagramm‑Zeitskala anpassen
url: /de/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt-PDF erstellen – Gantt-Diagramm-Zeitskala anpassen

## Einführung
Wenn Sie **Projekt-PDFs** erstellen müssen, die ein perfekt abgestimmtes Gantt‑Diagramm widerspiegeln, ist die Steuerung der Zeitskala‑Anzahl der Schlüssel. Mit Aspose.Tasks für Java können Sie programmgesteuert die unteren und mittleren Zeitskala‑Ebenen festlegen, Tick‑Markierungen ausblenden und dann **Projekt als PDF speichern** für eine einfache Verteilung. In diesem Tutorial führen wir Sie durch alles, was Sie benötigen – von der Einrichtung der Entwicklungsumgebung bis zur Erzeugung eines professionellen PDFs, das Ihre angepasste Gantt‑Ansicht präsentiert.

## Schnelle Antworten
- **Was bedeutet „Gantt-Diagramm anpassen“?** Anpassen von Zeitskala‑Ebenen, Farben und Layout, um Ihren Berichtserfordernissen zu entsprechen.  
- **Welche API‑Methode legt die Anzahl der unteren Ebene fest?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Kann ich ein PDF direkt aus dem Projekt erzeugen?** Ja – verwenden Sie `project.save(..., SaveFileFormat.Pdf)`.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz ist erforderlich; ein kostenloser Testzeitraum ist verfügbar.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher funktioniert mit der neuesten Aspose.Tasks‑Bibliothek.

## Was bedeutet „Gantt-Diagramm anpassen“ in Aspose.Tasks?
Das Anpassen eines Gantt‑Diagramms bedeutet, seine visuellen Komponenten programmgesteuert zu verändern – wie Zeitskala‑Intervalle, Tick‑Markierungen und Aufgabenbalken – sodass das Diagramm mit der gewünschten **Projektvisualisierung** übereinstimmt. Durch Ändern der Zeitskala‑Anzahl steuern Sie, wie viele Tage, Wochen oder Monate jedes Segment darstellt, wodurch das Diagramm für verschiedene Zielgruppen klarer wird.

## Warum ein Projekt-PDF mit einem angepassten Gantt-Diagramm erstellen?
- **Stakeholder‑geeignete Ausgabe:** PDF ist universell einsehbar und stellt sicher, dass jeder das gleiche Zeitplan‑Layout sieht.  
- **Druckfreundlich:** Präzise Kontrolle über Zeitskala‑Ebenen verhindert überfüllte oder mehrdeutige Ausdrucke.  
- **Automatisierung:** Integrieren Sie die PDF‑Erzeugung in CI‑Pipelines oder Reporting‑Dienste für null manuellen Aufwand.  

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java-Entwicklungsumgebung** – JDK 8 oder neuer installiert.  
2. **Aspose.Tasks für Java Bibliothek** – Laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **Grundlegende Java-Kenntnisse** – Vertrautheit mit Java‑Syntax und objektorientierten Konzepten.

## Pakete importieren
Importieren Sie die notwendigen Klassen in Ihr Java-Projekt:

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
Definieren Sie, wo Ihre Projektdateien gelesen und geschrieben werden:

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad auf Ihrem Rechner.

### Schritt 2: Neue Projektinstanz erstellen
Instanziieren Sie ein neues `Project`-Objekt, das alle Aufgaben und Ansichtseinstellungen enthält:

```java
Project project = new Project();
```

### Schritt 3: Gantt-Diagramm-Ansicht konfigurieren
Erstellen Sie ein `GanttChartView`-Objekt – hier werden Sie **Gantt-Ansicht-Java**-Code erzeugen, um das Erscheinungsbild des Diagramms zu steuern:

```java
GanttChartView view = new GanttChartView();
```

### Schritt 4: Zeitskala-Anzahl für die untere Ebene festlegen
Passen Sie die untere Ebene an, um zwei Intervalle anzuzeigen und die Tick-Markierungen auszublenden:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Schritt 5: Zeitskala-Anzahl für die mittlere Ebene festlegen
Wenden Sie dieselbe Konfiguration auf die mittlere Ebene an:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Schritt 6: Angepasste Ansicht zum Projekt hinzufügen
Fügen Sie die gerade konfigurierte Ansicht der `Project`-Instanz hinzu:

```java
project.getViews().add(view);
```

### Schritt 7: Beispielaufgaben hinzufügen (Testdaten)
Erstellen Sie ein paar Aufgaben mit spezifischen Dauern, um das angepasste Gantt-Diagramm zu veranschaulichen:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Schritt 8: Projekt als PDF speichern
Exportieren Sie schließlich das Projekt – einschließlich Ihres **angepassten Gantt-Diagramms** – in eine PDF-Datei:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Das resultierende PDF zeigt, wie die unteren und mittleren Zeitskala‑Ebenen **angepasst** wurden und bietet Stakeholdern eine klare, druckbare Ansicht des Zeitplans.

## Häufige Probleme & Fehlerbehebung
- **PDF ist leer** – Stellen Sie sicher, dass der `dataDir`-Pfad mit einem Dateiseparator (`/` oder `\`) endet und das Verzeichnis existiert.  
- **Ticks erscheinen weiterhin** – Vergewissern Sie sich, dass `setShowTicks(false)` für beide Ebenen aufgerufen wird.  
- **Dauer nicht angewendet** – Bestätigen Sie, dass Sie beim Erstellen von Dauern `TimeUnitType.Hour` (oder die passende Einheit) verwenden.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks für Java groß angelegte Projektdateien verarbeiten?**  
A: Ja, die Bibliothek ist für die Hochleistungs-Verarbeitung umfangreicher Projektdaten optimiert.

**Q: Ist Aspose.Tasks für Java mit verschiedenen Java-IDEs kompatibel?**  
A: Absolut – es funktioniert nahtlos mit Eclipse, IntelliJ IDEA, NetBeans und anderen gängigen IDEs.

**Q: Kann ich das Aussehen von Gantt-Diagrammen über die Zeitskala-Einstellungen hinaus anpassen?**  
A: Ja, Aspose.Tasks bietet umfangreiche Styling-Optionen wie Balkenfarben, Schriftarten und Rasterlinien.

**Q: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) erhalten.

**Q: Wo kann ich Unterstützung für Aspose.Tasks für Java erhalten?**  
A: Unterstützung und Hilfe finden Sie im Aspose.Tasks-Forum [hier](https://forum.aspose.com/c/tasks/15).

**Q: Wie ändere ich programmgesteuert die Hintergrundfarbe des Gantt-Diagramms?**  
A: Verwenden Sie die Methode `view.getGanttChartProperties().setBackgroundColor(Color)` nach dem Import von `java.awt.Color`.

## Fazit
Durch das Befolgen dieser Schritte haben Sie gelernt, wie Sie **Projekt-PDFs** mit einer vollständig angepassten Gantt-Diagramm-Zeitskala erstellen, die **Projektvisualisierung** verbessern und **Projekt als PDF speichern** mit Aspose.Tasks für Java. Dieser Ansatz gibt Ihnen die volle Kontrolle über die visuelle Ausgabe, sodass Sie klare, professionelle Zeitpläne leichter mit Ihrem Team oder Kunden teilen können.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Gantt-Diagrammansichten in Aspose.Tasks beherrschen
linktitle: Gantt-Diagrammansichten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Gantt-Diagrammansichten in Microsoft Project-Dateien mit Aspose.Tasks für .NET anpassen. Schritt-für-Schritt-Anleitung für effizientes Projektmanagement.
type: docs
weight: 22
url: /de/net/tasks-project-management/gantt-chart-views/
---
## Einführung
Gantt-Diagramme sind leistungsstarke Werkzeuge im Projektmanagement zur Visualisierung von Aufgaben, Zeitplänen und Abhängigkeiten. Aspose.Tasks für .NET bietet robuste Funktionen für die Arbeit mit Gantt-Diagrammansichten in Microsoft Project-Dateien. In diesem Tutorial erfahren Sie, wie Sie Aspose.Tasks verwenden, um Gantt-Diagrammansichten zu bearbeiten, ihr Erscheinungsbild anzupassen und sie als PDF-Dateien zu speichern.
## Voraussetzungen
Bevor Sie fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installation von Aspose.Tasks für .NET
 Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/tasks/net/) und befolgen Sie die Installationsanweisungen in der Dokumentation[Hier](https://reference.aspose.com/tasks/net/).
### 2. Microsoft Project-Datei
Bereiten Sie eine Microsoft Project-Datei vor (`Project2.mpp`), die Sie zum Arbeiten mit Gantt-Diagrammansichten verwenden werden.
### 3. Grundkenntnisse in C# und .NET Framework
In diesem Tutorial wird davon ausgegangen, dass Sie über grundlegende Kenntnisse der Programmiersprache C# und des .NET Frameworks verfügen.
## Namespaces importieren
Bevor Sie mit der Arbeit mit Gantt-Diagrammansichten in Aspose.Tasks beginnen, müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren. So können Sie es machen:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Lassen Sie uns den bereitgestellten Beispielcode in mehrere Schritte aufteilen und jeden Schritt im Detail erklären:
## Schritt 1: Laden Sie die Projektdatei
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Dieser Schritt umfasst das Laden der Microsoft Project-Datei (`Project2.mpp` ) in eine Instanz von`Project` Klasse.
## Schritt 2: Statusdatum festlegen
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Hier setzen wir das Statusdatum des Projekts auf sein Startdatum.
## Schritt 3: Greifen Sie auf die Gantt-Diagrammansicht zu
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Vom Projekt aus greifen wir auf die Gantt-Diagrammansicht zu. Aspose.Tasks ermöglicht den Zugriff auf Ansichten wie Gantt-Diagramm, Netzwerkdiagramm und Aufgabenverwendung.
## Schritt 4: Gantt-Diagrammansicht anpassen
Lassen Sie uns nun verschiedene Aspekte der Gantt-Diagrammansicht anpassen:
### Legen Sie die Balkenrundung fest
```csharp
view.BarRounding = false;
```
Dadurch wird festgelegt, ob die Balken im Gantt-Diagramm auf den nächsten Tag gerundet werden.
### Stellen Sie die Balkengröße ein
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Dadurch wird die Höhe der Gantt-Balken im Diagramm bestimmt.
### Rollup-Bars ausblenden
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Gibt an, ob Rollup-Balken beim Erweitern von Sammelaufgaben ausgeblendet werden.
### Legen Sie die Farbe der arbeitsfreien Zeit fest
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Definiert die Farbe für arbeitsfreie Zeit im Gantt-Diagramm.
### Gantt-Balken aufrollen
```csharp
view.RollUpGanttBars = true;
```
Gibt an, ob Balken im Gantt-Diagramm aufgerollt werden müssen.
### Balkenteilungen anzeigen
```csharp
view.ShowBarSplits = true;
```
Legt fest, ob Aufgabenaufteilungen im Gantt-Diagramm angezeigt werden müssen.
### Zeichnungen anzeigen
```csharp
view.ShowDrawings = true;
```
Gibt an, ob Zeichnungen im Gantt-Diagramm angezeigt werden müssen.
### Prozentsatz der Zeitskalengröße
```csharp
view.TimescaleSizePercentage = 10;
```
Legt einen Prozentsatz fest, um den Abstand zwischen Einheiten auf der Zeitskalaebene anzupassen.
## Schritt 5: Gantt-Diagrammansicht als PDF speichern
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Abschließend speichern wir die angepasste Gantt-Diagrammansicht als PDF-Datei.
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Gantt-Diagrammansichten in Aspose.Tasks für .NET arbeitet. Indem Sie die bereitgestellten Schritte befolgen, können Sie Gantt-Diagramme effizient bearbeiten und entsprechend Ihren Projektanforderungen anpassen.
## FAQs
### F: Kann ich das Erscheinungsbild von Gantt-Diagrammbalken weiter anpassen?
A: Ja, Aspose.Tasks bietet umfangreiche Optionen zum Anpassen des Erscheinungsbilds von Gantt-Diagrammbalken, einschließlich Farben, Formen und Größen.
### F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project-Dateien kompatibel?
A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich der Formate MPP, MPT und XML.
### F: Kann ich Gantt-Diagrammansichten in andere Formate als PDF exportieren?
A: Absolut, Aspose.Tasks unterstützt den Export von Gantt-Diagrammansichten in mehrere Formate, einschließlich PNG, JPEG und XPS.
### F: Bietet Aspose.Tasks Unterstützung für komplexe Projektplanungsalgorithmen?
A: Ja, Aspose.Tasks bietet erweiterte Planungsalgorithmen, um komplexe Projektpläne effektiv zu verwalten.
### F: Gibt es ein Community-Forum, in dem ich Hilfe suchen oder meine Erfahrungen mit Aspose.Tasks teilen kann?
 A: Ja, Sie können das besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um mit anderen Benutzern in Kontakt zu treten, Fragen zu stellen und Lösungen für Ihre Fragen zu finden.
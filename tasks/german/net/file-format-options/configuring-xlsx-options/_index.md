---
title: Konfigurieren Sie MS Project XLSX-Optionen in Aspose.Tasks für .NET
linktitle: Konfigurieren von XLSX-Optionen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project XLSX-Optionen in Aspose.Tasks für .NET konfigurieren. Passen Sie Spalten, Codierung usw. mühelos an.
type: docs
weight: 11
url: /de/net/file-format-options/configuring-xlsx-options/
---
## Einführung
Microsoft Project (MS Project) ist ein leistungsstarkes Tool für das Projektmanagement und Aspose.Tasks für .NET bietet eine nahtlose Integration für die programmgesteuerte Arbeit mit MS Project-Dateien. In diesem Tutorial führen wir Sie durch den Prozess der Konfiguration von MS Project XLSX-Optionen mithilfe von Aspose.Tasks für .NET.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
### 1. Aspose.Tasks für .NET installiert
 Stellen Sie sicher, dass Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert ist. Wenn nicht, können Sie es hier herunterladen[Aspose.Tasks für .NET-Downloadseite](https://releases.aspose.com/tasks/net/).
### 2. Grundlegendes Verständnis von C# und .NET Framework
Um diesem Tutorial folgen zu können, sind Kenntnisse der Programmiersprache C# und des .NET-Frameworks erforderlich.
### 3. Microsoft Project-Datei
Halten Sie eine Microsoft Project-Datei (MPP) bereit, die Sie konfigurieren und als XLSX-Datei speichern möchten.

## Namensräume importieren
Importieren Sie zunächst die erforderlichen Namespaces:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Schritt 1: Laden Sie das Projekt
```csharp
var project = new Project("YourProjectFile.mpp");
```
Laden Sie die Microsoft Project-Datei, die Sie konfigurieren möchten.
## Schritt 2: Definieren Sie XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Erstellen Sie eine Instanz von`XlsxOptions` um Einstellungen für das Speichern als XLSX zu konfigurieren.
## Schritt 3: Gantt-Diagrammspalten hinzufügen
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Fügen Sie den Optionen die gewünschten Gantt-Diagrammspalten hinzu.
## Schritt 4: Spalten für die Ressourcenansicht hinzufügen
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Fügen Sie gewünschte Spalten für die Ressourcenansicht in die Optionen ein.
## Schritt 5: Fügen Sie Spalten für die Aufgabenansicht hinzu
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Fügen Sie in den Optionen gewünschte Spalten für die Aufgabenansicht hinzu.
## Schritt 6: Kodierung festlegen
```csharp
options.Encoding = Encoding.Unicode;
```
Legen Sie die Kodierung für die Ausgabedatei fest.
## Schritt 7: Speichern Sie das Projekt als XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Speichern Sie das Projekt mit den konfigurierten Optionen als XLSX-Datei.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man MS Project XLSX-Optionen mit Aspose.Tasks für .NET konfiguriert. Wenn Sie diese Schritte befolgen, können Sie das Ausgabeformat an Ihre Anforderungen anpassen und so die Flexibilität und Benutzerfreundlichkeit Ihres Projektmanagement-Workflows verbessern.
## FAQs

### F: Kann ich verschiedene Spalten für das Gantt-Diagramm, die Ressourcenansicht und die Aufgabenansicht separat konfigurieren?

A: Ja, Sie können mit Aspose.Tasks für .NET Spalten für jede Ansicht unabhängig anpassen.

### F: Gibt es vor dem Kauf von Aspose.Tasks für .NET eine Testversion?

 A: Ja, Sie können eine kostenlose Testversion herunterladen[Aspose.Tasks für .NET-Versionsseite](https://releases.aspose.com/).

### F: Wie kann ich Unterstützung erhalten, wenn ich während der Implementierung auf Probleme stoße oder Fragen habe?

 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für die Unterstützung der Community und des Aspose-Supportteams.

### F: Kann ich XLSX-Dateien mit Aspose.Tasks für .NET auf Nicht-Windows-Plattformen generieren?

A: Aspose.Tasks für .NET ist in erster Linie für Windows-Plattformen konzipiert, Sie können jedoch auch Kompatibilitätsoptionen für andere Plattformen prüfen.

### F: Gibt es zu Testzwecken temporäre Lizenzoptionen?

 A: Ja, Sie können eine temporäre Lizenz von erhalten[Aspose.Tasks temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).
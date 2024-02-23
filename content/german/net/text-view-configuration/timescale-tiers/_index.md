---
title: Konfigurieren Sie die Zeitskalenstufen des Gantt-Diagramms in Aspose.Tasks
linktitle: Konfigurieren Sie Zeitskalenstufen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie Aspose.Tasks für .NET, um Zeitskalenebenen in Ihrer Gantt-Diagrammansicht für eine präzise Visualisierung der Projektzeitachse zu konfigurieren. #Aspose.Tasks #MS-Projekt
type: docs
weight: 16
url: /de/net/text-view-configuration/timescale-tiers/
---
## Einführung
In der dynamischen Landschaft des Projektmanagements ist eine effektive Visualisierung entscheidend für das Verständnis von Zeitplänen und Fristen. Aspose.Tasks für .NET bietet ein leistungsstarkes Toolset. In diesem Tutorial erfahren Sie, wie Sie Zeitskalenebenen für eine optimale Darstellung in der Gantt-Diagrammansicht konfigurieren. Befolgen Sie diese Schritt-für-Schritt-Anleitung, um Ihre Projektvisualisierung zu verbessern.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse in C# und .NET.
- Aspose.Tasks für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
- Eine für die .NET-Anwendungsentwicklung eingerichtete Entwicklungsumgebung.
## Namespaces importieren
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Lassen Sie uns nun jeden Schritt des bereitgestellten Beispiels aufschlüsseln.
## Schritt 1: Projekt initialisieren und Aufgabenlinks hinzufügen
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Hier erstellen wir ein Projekt und stellen Aufgabenverknüpfungen zwischen „Aufgabe 1“ und „Aufgabe 2“ her.
## Schritt 2: Gantt-Diagrammansicht konfigurieren
```csharp
var view = (GanttChartView)project.DefaultView;
```
Greifen Sie zur Anpassung auf die Gantt-Diagrammansicht zu.
## Schritt 3: Passen Sie die mittlere Zeitskalenstufe an
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Passen Sie die mittlere Zeitskalaebene an, um Wochen mit bestimmten Beschriftungen und Ausrichtung anzuzeigen.
## Schritt 4: Top-Zeitskalenstufe hinzufügen
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Fügen Sie eine oberste Zeitskalaebene hinzu, um Monate darzustellen.
## Schritt 5: Passen Sie die Daten der mittleren Ebene an
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personalisieren Sie die Monatsbeschriftungen zur besseren Visualisierung.
## Schritt 6: Projektzeitplan festlegen
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Definieren Sie den Projektzeitrahmen, um den gesamten Zeitplan zu steuern.
## Schritt 7: Speichern Sie das Projekt mit benutzerdefinierter Zeitskala
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Speichern Sie das Projekt mit den definierten Zeitskaleneinstellungen.
## Abschluss
Zusammenfassend lässt sich sagen, dass die Konfiguration von Zeitskalenebenen in Aspose.Tasks für .NET eine individuellere und optisch ansprechendere Darstellung der Projektzeitpläne ermöglicht. Mit diesen Schritten können Sie eine Gantt-Diagrammansicht erstellen, die genau Ihren Projektmanagementanforderungen entspricht.
## FAQs
### Kann ich Aspose.Tasks mit anderen .NET-Bibliotheken verwenden?
Ja, Aspose.Tasks lässt sich nahtlos in andere .NET-Bibliotheken integrieren und bietet so Flexibilität in Ihrem Entwicklungs-Stack.
### Ist eine temporäre Lizenz zu Testzwecken verfügbar?
 Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zur Auswertung.
### Gibt es zusätzliche Anpassungsmöglichkeiten für die Gantt-Diagrammansicht?
Aspose.Tasks bietet auf jeden Fall umfangreiche Anpassungsmöglichkeiten für die Gantt-Diagrammansicht, um den unterschiedlichen Projektanforderungen gerecht zu werden.
### Kann ich Zeitskalen in verschiedenen Formaten rendern?
Natürlich können Sie verschiedene Formate und Stile für die Zeitskalendarstellung erkunden, die am besten zum Kontext Ihres Projekts passen.
### Gibt es ein Community-Forum für den Aspose.Tasks-Support?
 Ja, besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und Diskussionen.
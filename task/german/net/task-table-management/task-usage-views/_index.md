---
title: Beherrschen der Aufgabennutzungsansichten in Aspose.Tasks für .NET
linktitle: Konfigurieren von Aufgabenverwendungsansichten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie Aspose.Tasks für .NET und erfahren Sie, wie Sie Aufgabennutzungsansichten konfigurieren. Passen Sie die Zeitskaleneinstellungen an und verbessern Sie die visuelle Darstellung Ihres Projektmanagements.
type: docs
weight: 24
url: /de/net/task-table-management/task-usage-views/
---
## Einführung
Im Bereich des Projektmanagements ist die Visualisierung der Aufgabennutzung von entscheidender Bedeutung für eine effektive Planung und Ausführung. Aspose.Tasks für .NET bietet eine robuste Lösung zum Rendern von Aufgabennutzungsansichten, mit der Sie Zeitskaleneinstellungen und Präsentationsformate anpassen können. In diesem Tutorial führen wir die Schritte zum Konfigurieren von Aufgabennutzungsansichten mithilfe von Aspose.Tasks durch.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Tasks für .NET: Stellen Sie sicher, dass die Aspose.Tasks-Bibliothek in Ihr .NET-Projekt integriert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
2. .NET-Umgebung: Richten Sie auf Ihrem Computer eine funktionierende .NET-Umgebung ein.
## Namespaces importieren
Importieren Sie in Ihrem .NET-Projekt die erforderlichen Namespaces, um auf die Funktionen von Aspose.Tasks zuzugreifen. Fügen Sie Ihrem Code die folgenden Zeilen hinzu:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Schritt 1: Legen Sie den Dokumentverzeichnispfad fest
 Bevor Sie mit den Aspose.Tasks-Funktionen arbeiten, legen Sie den Pfad zu Ihrem Dokumentenverzeichnis fest. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad.
```csharp
String DataDir = "Your Document Directory";
```
## Schritt 2: Laden Sie das Projekt
 Initialisieren Sie die Aspose.Tasks`Project` Objekt durch Laden Ihrer Projektdatei (z. B. TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Schritt 3: Definieren Sie SaveOptions
 Ein ... kreieren`SaveOptions`-Objekt, um die Rendering-Optionen anzugeben. Stellen Sie die Zeitskala auf „Tage“ und das Präsentationsformat auf „TaskUsage“ ein.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Schritt 4: Speichern Sie mit der Tageszeitskala
Speichern Sie das Projekt mit den vordefinierten Zeitskaleneinstellungen „Tage“.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Schritt 5: Speichern Sie mit der ThirdsOfMonths-Zeitskala
Ändern Sie die Zeitskaleneinstellungen in „ThirdsOfMonths“ und speichern Sie das Projekt.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Schritt 6: Sparen Sie mit der Zeitskala von Monaten
Stellen Sie die Zeitskala auf „Monate“ ein und speichern Sie das Projekt mit den aktualisierten Einstellungen.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Abschluss
Das Konfigurieren von Aufgabennutzungsansichten mit Aspose.Tasks für .NET ist ein unkomplizierter Prozess. Durch die Anpassung der Zeitskaleneinstellungen können Sie die Visualisierung Ihrer Projektaufgaben an Ihre spezifischen Bedürfnisse anpassen.
 Entdecken Sie weitere Features und Funktionalitäten im[Dokumentation](https://reference.aspose.com/tasks/net/).
## Häufig gestellte Fragen
### Kann ich die Zeitskala über die vordefinierten Einstellungen hinaus anpassen?
Ja, Sie können eine benutzerdefinierte Zeitskala festlegen, indem Sie die Intervalle und Einheiten angeben.
### Gibt es weitere Präsentationsformate?
Aspose.Tasks unterstützt verschiedene Präsentationsformate, darunter GanttChart, ResourceUsage und mehr.
### Ist Aspose.Tasks mit verschiedenen Projektdateiformaten kompatibel?
Ja, Aspose.Tasks unterstützt gängige Projektdateiformate wie MPP, XML und CSV.
### Kann ich unterschiedliche Zeitskaleneinstellungen auf bestimmte Aufgaben anwenden?
Selbstverständlich können Sie die Zeitskaleneinstellungen für einzelne Aufgaben innerhalb Ihres Projekts anpassen.
### Wie kann ich Unterstützung oder Hilfe für Aspose.Tasks erhalten?
 Besuche den[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für gemeinschaftliche Unterstützung und Anleitung.
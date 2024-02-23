---
title: Konfigurieren Sie die Anzeigeoptionen für MS Project in Aspose.Tasks
linktitle: Konfigurieren Sie Projektanzeigeoptionen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Anzeigeoptionen programmgesteuert mit Aspose.Tasks für .NET konfigurieren. Passen Sie das Erscheinungsbild Ihres Projekts mühelos an.
type: docs
weight: 17
url: /de/net/project-management-integration/project-display-options/
---
## Einführung
Microsoft Project bietet zahlreiche Anzeigeoptionen, mit denen Sie das Erscheinungsbild Ihres Projekts anpassen können. Aspose.Tasks für .NET bietet ein robustes Framework zur programmgesteuerten Bearbeitung dieser Optionen. In diesem Tutorial erfahren Sie, wie Sie die Anzeigeoptionen von MS Project mithilfe von Aspose.Tasks konfigurieren.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks für .NET: Laden Sie die Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
2. Microsoft Project-Datei: Halten Sie eine gültige MS Project-Datei (.mpp) bereit, um die Anzeigeoptionen anzuwenden.
3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist erforderlich.

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihren C#-Code importieren:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Schritt 1: Laden Sie die Projektdatei
 Laden Sie die MS Project-Datei mit`Project` Von Aspose.Tasks bereitgestellte Klasse:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Schritt 2: Anzeigeoptionen konfigurieren
Lassen Sie uns nun verschiedene in MS Project verfügbare Anzeigeoptionen konfigurieren:
### Deaktivieren Sie Warnungen zum Aufgabenplan
So deaktivieren Sie Warnungen für Planungskonflikte mit manuell geplanten Aufgaben (verfügbar für Project 2010 und höher):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Fügen Sie Leerzeichen vor der Beschriftung hinzu
Legen Sie fest, dass vor dem Zahlenwert und der Zeitabkürzung ein Leerzeichen eingefügt wird:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Konfigurieren Sie die Beschriftungsanzeige für Zeiteinheiten
Passen Sie an, wie verschiedene Zeiteinheiten angezeigt werden:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Projektzusammenfassungsaufgabe anzeigen
Zusammenfassende Informationen zum gesamten Projekt in einer einzigen Zeile anzeigen:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Aktivieren Sie Vorschläge für den Aufgabenplan
Anzeige von Vorschlägen für Planungskonflikte mit manuell geplanten Aufgaben zulassen:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Unterstreichen Sie Hyperlinks
Legen Sie fest, dass Hyperlinks innerhalb des Projekts unterstrichen werden sollen:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Schritt 3: Speichern Sie das Projekt
Speichern Sie abschließend das Projekt mit den angewendeten Anzeigeoptionen:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man MS Project-Anzeigeoptionen mit Aspose.Tasks für .NET konfiguriert. Mit diesen Funktionen können Sie das Erscheinungsbild Ihrer Projektdateien programmgesteuert effizient anpassen.
## FAQs
### F: Kann ich diese Anzeigeoptionen nur auf bestimmte Aufgaben anwenden?
A: Ja, Sie können mithilfe der Aspose.Tasks-API Anzeigeoptionen selektiv auf einzelne Aufgaben anwenden.
### F: Haben diese Anzeigeoptionen Auswirkungen auf die zugrunde liegenden Projektdaten?
A: Nein, diese Optionen verändern nur die visuelle Darstellung des Projekts und verändern nicht die zugrunde liegenden Daten.
### F: Sind diese Anzeigeoptionen mit allen Versionen von Microsoft Project kompatibel?
A: Nein, einige Optionen sind möglicherweise spezifisch für bestimmte Versionen von MS Project. Einzelheiten zur Kompatibilität finden Sie in der Dokumentation.
### F: Kann ich die Anzeigeoptionen auf die Standardeinstellungen zurücksetzen?
A: Ja, Sie können die Anzeigeoptionen mithilfe der Aspose.Tasks-API auf ihre Standardwerte zurücksetzen.
### F: Gibt es Einschränkungen beim programmgesteuerten Anpassen der Anzeigeoptionen?
A: Obwohl Aspose.Tasks umfangreiche Anpassungsmöglichkeiten bietet, sind bestimmte Anzeigeoptionen aufgrund von Einschränkungen im MS Project-Dateiformat möglicherweise nicht programmgesteuert verfügbar.
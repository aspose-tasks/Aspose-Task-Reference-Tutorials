---
title: Konfigurieren Sie die MS Project-Seiteneinstellungen mit Aspose.Tasks
linktitle: Konfigurieren von Seiteneinstellungen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Seiteneinstellungen mit Aspose.Tasks für .NET konfigurieren. Passen Sie Ausrichtung, Größe und mehr mit einfachen Schritten an.
type: docs
weight: 20
url: /de/net/outline-code-page-settings/page-settings/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess der Konfiguration von Microsoft Project-Seiteneinstellungen mit Aspose.Tasks für .NET. Aspose.Tasks ist eine leistungsstarke API, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit Visual Studio oder einer anderen bevorzugten IDE für die .NET-Entwicklung ein.

## Namensräume importieren
Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Diese Namespaces bieten Zugriff auf die Aspose.Tasks-Klassen und -Methoden, die zum Bearbeiten von MS Project-Dateien erforderlich sind.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Schritt 1: Laden Sie die Projektdatei
Zuerst müssen Sie die MS Project-Datei laden, für die Sie die Seiteneinstellungen konfigurieren möchten.
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Schritt 2: Greifen Sie auf die Seiteneinstellungen zu
Als Nächstes greifen Sie auf die Seiteneinstellungen der Projektdatei zu.
```csharp
// Holen Sie sich die Einstellungen
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Schritt 3: Seiteneinstellungen konfigurieren
Lassen Sie uns nun verschiedene Eigenschaften der Seiteneinstellungen entsprechend Ihren Anforderungen konfigurieren.
```csharp
// Stellen Sie die Seitenausrichtung auf Hochformat ein
settings.IsPortrait = true;
// Legen Sie die Anzahl der Seiten in der Breite fest, die gedruckt werden sollen
settings.PagesInWidth = 5;
// Legen Sie die Anzahl der Seiten in der Höhe fest, die gedruckt werden sollen
settings.PagesInHeight = 7;
// Legen Sie den Prozentsatz der Normalgröße fest, an den der Druck angepasst werden soll
settings.PercentOfNormalSize = 200;
// Stellen Sie das Papierformat ein
settings.PaperSize = PrinterPaperSize.PaperB4;
// Legen Sie die erste Seitenzahl für den Druck fest
settings.FirstPageNumber = 3;
```
## Schritt 4: Speichern Sie die Projektdatei
Speichern Sie abschließend die Projektdatei mit den aktualisierten Seiteneinstellungen.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Microsoft Project-Seiteneinstellungen mit Aspose.Tasks für .NET konfiguriert. Wenn Sie diese Schritte befolgen, können Sie die Seitenausrichtung, -größe und andere Druckoptionen ganz einfach an Ihre Anforderungen anpassen.

## FAQs
### F: Kann ich Seiteneinstellungen für mehrere MS Project-Dateien gleichzeitig konfigurieren?
A: Ja, Sie können mehrere Projektdateien durchlaufen und auf jede einzelne die gleichen Seiteneinstellungen anwenden.
### F: Ist es möglich, die Seiteneinstellungen auf die Standardeinstellungen zurückzusetzen?
A: Absolut, Sie können die Konfigurationsschritte einfach weglassen oder die Einstellungen auf ihre Standardwerte zurücksetzen.
### F: Gibt es Einschränkungen hinsichtlich der unterstützten Papierformate?
A: Aspose.Tasks unterstützt eine Vielzahl von Papierformaten, einschließlich Standard- und benutzerdefinierten Formaten.
### F: Kann ich den Konfigurationsprozess der Seiteneinstellungen automatisieren?
A: Natürlich können Sie diese Funktionalität in den Workflow Ihrer Anwendung integrieren, um die Konfiguration der Seiteneinstellungen zu automatisieren.
### F: Bietet Aspose.Tasks neben .mpp auch Unterstützung für andere Dateiformate?
A: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate wie unter anderem XML, MPT und HTML.
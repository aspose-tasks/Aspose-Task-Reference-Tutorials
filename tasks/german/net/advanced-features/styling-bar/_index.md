---
title: Styling-Leiste in Aspose.Tasks
linktitle: Styling-Leiste in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Balken in Aspose.Tasks für .NET formatieren, um die Projektvisualisierung zu verbessern.
weight: 19
url: /de/net/advanced-features/styling-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Styling-Leiste in Aspose.Tasks

## Einführung

Das Gestalten von Balken in Aspose.Tasks ist ein wesentlicher Aspekt bei der Erstellung optisch ansprechender Projektpläne. Mit der Flexibilität, die die Aspose.Tasks-API bietet, können Entwickler verschiedene Aspekte von Balken, wie z. B. Farbe, Form und Textstil, anpassen, um die Projektvisualisierung zu verbessern. In diesem Tutorial erfahren Sie, wie Sie Balken mit Aspose.Tasks für .NET formatieren, und unterteilen dabei jedes Beispiel in überschaubare Schritte.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek von herunter und installieren Sie sie[Download-Seite](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit .NET Framework-Unterstützung ein.
3. Grundkenntnisse von C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.

## Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces für den Zugriff auf Aspose.Tasks-Klassen und -Methoden:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Schritt 1: Laden Sie das Projekt

Laden Sie zunächst die Projektdatei mit der Aspose.Tasks-API:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Schritt 2: Speicheroptionen konfigurieren

Definieren Sie die Speicheroptionen und geben Sie die anzuwendenden Balkenstile an:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Schritt 3: Balkenstil definieren

Erstellen Sie einen neuen Balkenstil und passen Sie seine Eigenschaften an:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Legen Sie den Typ des Balkenelements fest
style.BarColor = Color.Green; // Balkenfarbe festlegen
style.BarShape = BarShape.HalfHeight; // Stabform einstellen
style.StartShape = Shape.LeftBracket; // Legen Sie die Form am Anfang des Balkens fest
style.StartShapeColor = Color.Aqua; // Legen Sie die Farbe der Startform fest
style.EndShape = Shape.RightBracket; // Form am Ende der Leiste festlegen
style.EndShapeColor = Color.Aquamarine; // Legen Sie die Farbe der Endform fest
style.TextStyle = new TextStyle(); // Textstil festlegen
style.TextStyle.BackgroundColor = Color.Black; // Hintergrundfarbe für Text festlegen
```

## Schritt 4: Passen Sie den Textkonverter an

Passen Sie optional den Textkonverter an, um die Textwiedergabe zu ändern:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Schritt 5: Balkenstil zu den Optionen hinzufügen

Fügen Sie den konfigurierten Balkenstil zu den Speicheroptionen hinzu:

```csharp
options.BarStyles.Add(style);
```

## Schritt 6: Speichern Sie das Projekt

Speichern Sie abschließend das Projekt mit den angewendeten Balkenstilen:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Abschluss

Das Anpassen von Balkenstilen in Aspose.Tasks für .NET bietet Entwicklern die Möglichkeit, optisch ansprechende Projektpläne zu erstellen. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Balken effizient so gestalten, dass sie bestimmte Anforderungen an die Projektvisualisierung erfüllen.

## FAQs

### F1: Kann ich mehrere Balkenstile auf ein einzelnes Projekt anwenden?

A1: Ja, Sie können mehrere Balkenstile definieren und auf verschiedene Arten von Aufgaben innerhalb desselben Projekts anwenden.
   
### F2: Ist es möglich, Balkenstile während der Laufzeit dynamisch zu ändern?

A2: Ja, Sie können Balkenstile basierend auf bestimmten Bedingungen oder Benutzerpräferenzen in Ihrer Anwendung dynamisch ändern.
   
### F3: Unterstützt Aspose.Tasks den Export von Projekten mit gestalteten Balken in verschiedene Dateiformate?

A3: Ja, Aspose.Tasks unterstützt den Export von Projekten mit gestalteten Balken in verschiedene Formate wie PDF, XLSX und HTML.
   
### F4: Sind in Aspose.Tasks vordefinierte Balkenstile verfügbar?

A4: Während Aspose.Tasks Standardleistenstile bereitstellt, können Entwickler auch benutzerdefinierte Balkenstile erstellen, die auf ihre Projektanforderungen zugeschnitten sind.
   
### F5: Kann ich mithilfe der API vorhandene Balkenstile innerhalb eines Projekts abrufen und ändern?

A5: Ja, Sie können vorhandene Balkenstile programmgesteuert mithilfe der Aspose.Tasks für .NET-API abrufen und ändern.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

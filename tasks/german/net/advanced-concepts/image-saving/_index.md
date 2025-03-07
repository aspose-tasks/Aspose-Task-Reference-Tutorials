---
title: Umgang mit dem Speichern von Bildern in Aspose.Tasks
linktitle: Umgang mit dem Speichern von Bildern in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie anhand von Schritt-für-Schritt-Anleitungen, wie Sie mit dem Speichern von Bildern in Aspose.Tasks für .NET umgehen. Integrieren Sie die Funktion zum Speichern von Bildern nahtlos in Ihre .NET-Anwendungen.
weight: 10
url: /de/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Umgang mit dem Speichern von Bildern in Aspose.Tasks

## Einführung

In diesem Tutorial befassen wir uns mit dem Prozess der Bildspeicherung in Aspose.Tasks für .NET. Aspose.Tasks ist eine leistungsstarke API, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten. Eine häufige Aufgabe bei der Arbeit mit Projektdateien ist das Speichern von Bildern, die Diagramme, Grafiken oder andere visuelle Elemente enthalten können. Wir werden den Prozess Schritt für Schritt aufschlüsseln und so für Klarheit und Verständnis sorgen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist.
2.  Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis von C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.

## Namespaces importieren

Importieren wir zunächst die notwendigen Namespaces in unser Projekt:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt 1: Erstellen Sie ein Projektobjekt

Erstellen Sie zunächst ein Project-Objekt aus Ihrer Microsoft Project-Datei:

```csharp
var project = new Project("Project1.mpp");
```

## Schritt 2: Speicheroptionen definieren

Definieren Sie die Speicheroptionen für Ihr Projekt, indem Sie die Seiten und andere Einstellungen angeben:

```csharp
var options = GetSaveOptions(1);
```

## Schritt 3: Speichern Sie das Projekt als HTML

Speichern Sie das Projekt als HTML mit den angegebenen Optionen:

```csharp
project.Save("document_out.html", options);
```

## Schritt 4: Implementieren Sie den Rückruf zum Speichern von Bildern

Implementieren Sie die ImageSavingCallback-Schnittstelle, um das Speichern von Bildern zu verwalten:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Hier kommt die Bildspeicherlogik zum Einsatz
    }
}
```

## Schritt 5: Bilder im angegebenen Verzeichnis speichern

Geben Sie innerhalb der ImageSaving-Methode die Logik zum Speichern von Bildern im gewünschten Verzeichnis an:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Sparen Sie verschachtelte Ressourcen
}
else
{
    // Sparen Sie regelmäßige Ressourcen
}
```

## Schritt 6: Spezifizieren Sie die Speicheroptionen

Geben Sie die Speicheroptionen an, einschließlich Rückrufen für CSS, Schriftarten und Bilder:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Geben Sie hier Speicheroptionen an
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Abschluss

Zusammenfassend lässt sich sagen, dass die Handhabung der Bildspeicherung in Aspose.Tasks für .NET die Definition von Speicheroptionen und die Implementierung von Rückrufen umfasst, um den Speichervorgang effektiv zu verwalten. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie die Funktion zum Speichern von Bildern nahtlos in Ihre .NET-Anwendungen integrieren.

## FAQs

### F1: Kann ich Aspose.Tasks verwenden, um Projektdateien in anderen Formaten als HTML zu bearbeiten?

A1: Ja, Aspose.Tasks unterstützt verschiedene Formate wie PDF, XLSX und MPP.

### F2: Bietet Aspose.Tasks Unterstützung für die Cloud-Speicherintegration?

A2: Ja, Aspose.Tasks bietet APIs für die Arbeit mit beliebten Cloud-Speicherdiensten wie Amazon S3 und Google Drive.

### F3: Ist Aspose.Tasks mit .NET Core kompatibel?

A3: Ja, Aspose.Tasks ist mit .NET Core kompatibel, sodass Sie plattformübergreifende Anwendungen entwickeln können.

### F4: Kann ich das Erscheinungsbild gespeicherter Bilder anpassen?

A4: Ja, Sie können das Erscheinungsbild gespeicherter Bilder anpassen, indem Sie die Bildspeicherlogik innerhalb der Rückrufmethoden ändern.

### F5: Bietet Aspose.Tasks Testversionen zu Evaluierungszwecken an?

 A5: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks unter erhalten[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

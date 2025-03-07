---
title: CSS-Speicherargumente in Aspose.Tasks
linktitle: CSS-Speicherargumente in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie CSS-Argumente in Aspose.Tasks für .NET speichern, um die HTML-Ausgabe anzupassen. Verbessern Sie die Präsentation mit maßgeschneiderten CSS-Einstellungen.
weight: 20
url: /de/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# CSS-Speicherargumente in Aspose.Tasks

## Einführung

In diesem Tutorial befassen wir uns mit dem Prozess des Speicherns von CSS-Argumenten mithilfe von Aspose.Tasks für .NET. Cascading Style Sheets (CSS) sind entscheidend für die Definition der Darstellung von HTML-Elementen. Mit Aspose.Tasks können wir diese CSS-Attribute effizient bearbeiten und speichern.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Installation: Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/tasks/net/).

2. Grundkenntnisse: Vertrautheit mit der C#- und .NET-Entwicklungsumgebung wird empfohlen.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Schritt 1: CSS-Speicherrückrufe definieren

Zunächst definieren wir die Callback-Methoden zum Speichern von CSS, um das Speichern von CSS-Dateien zu verwalten:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implementieren Sie hier Ihre CSS-Speicherlogik
    }
}
```

## Schritt 2: Implementieren Sie Rückrufe zum Speichern von Schriftarten und Bildern

Als Nächstes implementieren Sie die Rückrufmethoden zum Speichern von Schriftarten und Bildern auf ähnliche Weise:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implementieren Sie hier Ihre Logik zum Speichern von Schriftarten
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implementieren Sie hier Ihre Bildspeicherlogik
}
```

## Schritt 3: Konfigurieren Sie die Speicheroptionen

Konfigurieren Sie nun die HTML-Speicheroptionen, um die implementierten Rückrufe zu nutzen:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Konfigurieren Sie HTML-Speicheroptionen
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Schritt 4: Projekt mit benutzerdefiniertem CSS speichern

Speichern Sie abschließend Ihr Projekt mit den angepassten CSS-Einstellungen:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man CSS-Argumente mit Aspose.Tasks für .NET speichert. Durch die Definition von CSS-Speicherrückrufen und die Konfiguration von HTML-Speicheroptionen können wir CSS-Attribute entsprechend unseren Anforderungen effizient bearbeiten.

## FAQs

### F1: Was ist Aspose.Tasks für .NET?

A1: Aspose.Tasks für .NET ist eine leistungsstarke .NET-API, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten.

### F2: Kann ich CSS-Attribute anpassen, wenn ich HTML-Dateien mit Aspose.Tasks speichere?

A2: Ja, Sie können CSS-Speicherrückrufe definieren, um CSS-Attribute an Ihre Bedürfnisse anzupassen.

### F3: Ist Aspose.Tasks für .NET mit allen Versionen von Microsoft Project-Dateien kompatibel?

A3: Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project-Dateien und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.

### F4: Wo finde ich eine umfassende Dokumentation zu Aspose.Tasks für .NET?

A4: Sie können sich auf die beziehen[Dokumentation](https://reference.aspose.com/tasks/net/) Ausführliche Informationen und Beispiele finden Sie hier.

### F5: Bietet Aspose.Tasks für .NET Unterstützung für Entwickler?

 A5: Ja, Sie können Unterstützung von der Aspose.Tasks-Community über erhalten[Forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

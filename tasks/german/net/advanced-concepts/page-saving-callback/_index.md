---
date: 2026-03-16
description: Erfahren Sie, wie Sie den Page‑Saving‑Callback in Aspose.Tasks für .NET
  implementieren, um die benutzerdefinierte Handhabung von mehrseitigen Dokumentausgabeströmen
  zu ermöglichen.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Seiten‑Speicher‑Callback in Aspose.Tasks implementieren
url: /de/net/advanced-concepts/page-saving-callback/
weight: 12
---

Also need to translate "## Quick Answers" etc.

Now produce final content with all shortcodes and markdown.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementieren des Page‑Saving‑Callbacks in Aspose.Tasks

## Einführung

In diesem Tutorial lernen Sie, wie Sie den **Page‑Saving‑Callback** in Aspose.Tasks für .NET **implementieren**. Diese leistungsstarke Funktion ermöglicht es Ihnen, jede Seite eines mehrseitigen Dokuments in einen Stream Ihrer Wahl zu leiten, sodass Sie die Speicherung oder Weiterverarbeitung der Ausgabe vollständig kontrollieren können.

## Schnelle Antworten
- **Was macht der Page‑Saving‑Callback?** Er erfasst jede gerenderte Seite in einem separaten Stream, sodass Sie sie einzeln verarbeiten können.  
- **In welches Format kann ich exportieren?** Jedes von `ImageSaveOptions` unterstützte Format, z. B. PNG, JPEG, PDF.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich das mit .NET Core verwenden?** Ja, Aspose.Tasks unterstützt .NET Core sowie .NET 5/6+ vollständig.  
- **Ist der Callback thread‑sicher?** Der Callback wird im selben Thread ausgeführt, der das Rendering durchführt, daher gelten die üblichen Thread‑Sicherheitsregeln.

## Was ist **implement page saving callback**?
Das **implement page saving callback**‑Muster ermöglicht es Ihnen, benutzerdefinierte Logik in die Speicherschlauchleitung von Aspose.Tasks einzuklinken. Anstatt direkt in eine Datei zu schreiben, erhalten Sie für jede Seite ein `Stream`‑Objekt, das Sie im Speicher ablegen, in Cloud‑Speicher hochladen oder weiterverarbeiten können.

## Warum ein Projekt als PNG mit einem Callback exportieren?
Der Export eines Projekts als PNG liefert Ihnen ein Rasterbild jeder Gantt‑Diagramm‑Seite, was sich ideal für Berichte, E‑Mails oder das Einbetten in Webseiten eignet. Durch die Verwendung eines Callbacks können Sie jede Seite in einem separaten `MemoryStream` behalten, ohne temporäre Dateien auf der Festplatte zu erzeugen.

## Voraussetzungen

1. **C#‑Kenntnisse** – Grundlegende Vertrautheit mit Klassen, Schnittstellen und Streams.  
2. **Aspose.Tasks für .NET** – herunterladen und installieren von [hier](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider oder ein beliebiger .NET‑kompatibler Editor.

## Namespaces importieren

Um zu beginnen, importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Schritt 1: Erstellen eines Project‑Objekts

Laden Sie eine vorhandene MPP‑Datei in eine `Project`‑Instanz:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Schritt 2: Konfigurieren der Image‑Save‑Optionen

Richten Sie `ImageSaveOptions` für PNG‑Ausgabe ein und hängen Sie den benutzerdefinierten Callback an:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Profi‑Tipp:** Durch das Setzen von `RenderToSinglePage = false` wird sichergestellt, dass jede Gantt‑Diagramm‑Seite separat gerendert wird, was für den Callback notwendig ist, um unterschiedliche Streams zu erhalten.

## Schritt 3: Projekt mit Callback speichern

Rufen Sie die `Save`‑Methode auf und übergeben Sie `Stream.Null`, weil die tatsächlichen Streams vom Callback bereitgestellt werden:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Schritt 4: Gespeicherte Seiten‑Streams verarbeiten

Nachdem der Speicher‑Vorgang abgeschlossen ist, hält der Callback eine Sammlung von `MemoryStream`‑Objekten – eines pro Seite. Sie können nun über diese iterieren:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Schritt 5: Benutzerdefinierten Page‑Saving‑Callback implementieren

Erstellen Sie eine versiegelte Klasse, die `IPageSavingCallback` implementiert. Diese Klasse erfasst den Stream jeder Seite und speichert ihn in einer Liste zur späteren Verwendung.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Häufige Fallstricke & Fehlerbehebung

| Problem | Grund | Lösung |
|---------|-------|--------|
| **Keine Seiten werden zurückgegeben** | `RenderToSinglePage` wurde auf `true` belassen. | Setzen Sie `RenderToSinglePage = false`, um separate Seiten zu erzeugen. |
| **Streams sind leer** | `KeepStreamOpen` wurde auf `true` gesetzt, ohne später zu entsorgen. | Lassen Sie es `false` (Standard) und lassen Sie den Callback die Streams automatisch schließen. |
| **Out‑of‑Memory‑Fehler** | Sehr große Projekte erzeugen viele hochauflösende PNGs. | Verarbeiten Sie die Streams einzeln oder erhöhen Sie die VM‑Speichergrenzen. |

## Häufig gestellte Fragen

**Q1: Was ist ein Page‑Saving‑Callback in Aspose.Tasks?**  
A: Ein Page‑Saving‑Callback ermöglicht es Ihnen, den Speicherprozess jeder Seite eines mehrseitigen Dokuments abzufangen und einen benutzerdefinierten `Stream` für diese Seite bereitzustellen.

**Q2: Kann ich verschiedene Formate zum Speichern von Seiten mit diesem Callback verwenden?**  
A: Ja. Durch Ändern von `SaveFileFormat` können Sie zu PNG, JPEG, PDF, SVG usw. exportieren.

**Q3: Ist Aspose.Tasks mit .NET Core kompatibel?**  
A: Absolut. Aspose.Tasks unterstützt .NET Core, .NET 5 und .NET 6.

**Q4: Wie kann ich Fehler während des Seiten‑Speicher‑Prozesses behandeln?**  
A: Umhüllen Sie die Callback‑Logik in try/catch‑Blöcke und protokollieren Sie Ausnahmen. Die Methode `OnFinish` ist ein guter Ort für die abschließende Bereinigung.

**Q5: Wo finde ich weitere Ressourcen und Support für Aspose.Tasks?**  
A: Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Unterstützung besuchen, die Dokumentation [hier](https://reference.aspose.com/tasks/net/) aufrufen oder weitere Funktionen und Lizenzierungsoptionen auf der [Aspose.Tasks‑Website](https://purchase.aspose.com/buy) erkunden.

---

**Letzte Aktualisierung:** 2026-03-16  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
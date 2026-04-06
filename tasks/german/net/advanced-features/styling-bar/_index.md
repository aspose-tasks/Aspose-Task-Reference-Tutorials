---
date: 2026-04-06
description: Erfahren Sie, wie Sie die Balkenformatierung ändern und die Balkenfarben
  in Aspose.Tasks für .NET anpassen, um die Projektvisualisierung zu verbessern.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Styling‑Leiste in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man die Balkenstilierung in Aspose.Tasks ändert
url: /de/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Balkenformatierung in Aspose.Tasks ändert

## Einführung

Wenn Sie das **how to change bar** Aussehen in einer Microsoft Project-Datei ändern müssen, gibt Ihnen Aspose.Tasks für .NET die volle Kontrolle über Balkenfarben, Formen und Textstile. Durch die Anpassung von Balkenfarben und anderen visuellen Attributen können Sie Projektpläne deutlich leichter lesbar und besser an das Branding Ihrer Organisation angepasst machen. In diesem Tutorial führen wir Sie durch ein vollständiges, Schritt‑für‑Schritt‑Beispiel, das zeigt, wie Sie die Balkenformatierung ändern, vom Laden eines Projekts bis zum Export mit den neuen visuellen Regeln.

## Schnelle Antworten
- **Was kann ich formatieren?** Balken, Meilensteine und Aufgabentext in Gantt‑Diagrammen.  
- **Welches Format unterstützt formatierte Balken?** PDF, XLSX, HTML und native MPP, wenn mit `PdfSaveOptions` gespeichert.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich; eine kostenlose Testversion funktioniert für Tests.  
- **Kann ich mehrere Stile anwenden?** Ja – fügen Sie so viele `BarStyle`‑Objekte hinzu, wie Sie benötigen.  
- **Ist es .NET Core kompatibel?** Absolut – funktioniert mit .NET Framework und .NET Core/5/6+.

## Was ist Balkenformatierung in Aspose.Tasks?

Die Balkenformatierung ermöglicht es Ihnen, visuelle Regeln zu definieren, die die Aspose.Tasks‑Engine beim Rendern von Gantt‑Diagrammen anwendet. Jede Regel (ein **BarStyle**) richtet sich an einen bestimmten Elementtyp – Aufgaben, Meilensteine oder Zusammenfassungsaufgaben – und lässt Sie Farben, Formen und sogar benutzerdefinierten Text festlegen.

## Warum Balkenfarben anpassen?

Die Anpassung von Balkenfarben hilft Stakeholdern, kritische Pfade, verzögerte Aufgaben oder Meilensteine sofort zu erkennen. Sie ermöglicht es Ihnen außerdem, Unternehmensfarbschemata anzupassen, sodass Berichte professionell und markenkonform wirken.

## Voraussetzungen

1. **Aspose.Tasks for .NET** – laden Sie es von der [download page](https://releases.aspose.com/tasks/net/) herunter.  
2. Eine Entwicklungsumgebung, die .NET unterstützt (Framework 4.6+, .NET Core 3.1+ oder höher).  
3. Grundlegende Kenntnisse in C# – die Beispiele verwenden einfachen, eigenständigen Code.

## Namespaces importieren

Zuerst importieren Sie die Namespaces, die die Klassen enthalten, die wir verwenden werden:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt 1: Projekt laden

Laden Sie eine vorhandene MPP‑Datei (oder erstellen Sie eine neue), damit Sie ein Projektobjekt haben, mit dem Sie arbeiten können:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Schritt 2: Speicheroptionen konfigurieren

Erstellen Sie eine Instanz von `PdfSaveOptions` und initialisieren Sie die `BarStyles`‑Sammlung, in der wir unsere benutzerdefinierten Stile speichern:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Schritt 3: Balkenstil definieren

Jetzt erstellen wir ein `BarStyle`‑Objekt und setzen die Eigenschaften, die das Aussehen des Balkens steuern. Hier passen wir **Balkenfarben** und Formen an:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Schritt 4: Textkonverter anpassen (optional)

Wenn Sie den Text, der auf dem Balken erscheint, anpassen möchten, können Sie einen benutzerdefinierten Konverter zuweisen. Das Beispiel fügt Aufgaben­namen, die nicht bereits mit „T“ beginnen, das Präfix hinzu:

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

## Schritt 5: Balkenstil zu den Optionen hinzufügen

Fügen Sie den vollständig konfigurierten Stil zur `BarStyles`‑Sammlung der Speicheroptionen hinzu:

```csharp
options.BarStyles.Add(style);
```

## Schritt 6: Projekt speichern

Exportieren Sie schließlich das Projekt. Das PDF (oder ein anderes Format) rendert das Gantt‑Diagramm mit dem von uns definierten Balkenstil:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|-------|--------|-----|
| **Balkenstil nicht angewendet** | `BarStyles`‑Sammlung war leer oder nicht an die Speicheroptionen angehängt. | Stellen Sie sicher, dass Sie den `BarStyle` zu `options.BarStyles` hinzufügen, bevor Sie `Save` aufrufen. |
| **Farben sehen im PDF anders aus** | Die PDF‑Darstellung kann ein anderes Farbprofil verwenden. | Verwenden Sie Standardwerte von `System.Drawing.Color` oder definieren Sie benutzerdefinierte ARGB‑Farben. |
| **Textkonverter wirft Nullverweis** | Die Aufgabeneigenschaft `Tsk.Name` ist für einige Aufgaben null. | Fügen Sie eine Null‑Prüfung hinzu, bevor Sie `task.Get(Tsk.Name)` aufrufen. |

## FAQ's

### Q1: Kann ich mehrere Balkenstile auf ein einzelnes Projekt anwenden?

A1: Ja, Sie können mehrere Balkenstile definieren und auf verschiedene Aufgabentypen innerhalb desselben Projekts anwenden.

### Q2: Ist es möglich, Balkenstile zur Laufzeit dynamisch zu ändern?

A2: Ja, Sie können Balkenstile basierend auf bestimmten Bedingungen oder Benutzerpräferenzen in Ihrer Anwendung dynamisch ändern.

### Q3: Unterstützt Aspose.Tasks das Exportieren von Projekten mit formatierten Balken in verschiedene Dateiformate?

A3: Ja, Aspose.Tasks unterstützt den Export von Projekten mit formatierten Balken in verschiedene Formate wie PDF, XLSX und HTML.

### Q4: Gibt es vordefinierte Balkenstile in Aspose.Tasks?

A4: Obwohl Aspose.Tasks Standard‑Balkenstile bereitstellt, können Entwickler auch benutzerdefinierte Balkenstile erstellen, die auf ihre Projektanforderungen zugeschnitten sind.

### Q5: Kann ich vorhandene Balkenstile innerhalb eines Projekts über die API abrufen und ändern?

A5: Ja, Sie können vorhandene Balkenstile programmgesteuert über die Aspose.Tasks‑API für .NET abrufen und ändern.

## Häufig gestellte Fragen

**Q: Wie ändere ich die Balkenfarbe für reguläre Aufgaben statt für Meilensteine?**  
A: Setzen Sie `style.ItemType = BarItemType.Task;` und weisen Sie `style.BarColor` die gewünschte `Color` zu.

**Q: Kann ich diesen Ansatz verwenden, um Balken beim Export nach HTML zu formatieren?**  
A: Ja. Verwenden Sie `HtmlSaveOptions` und füllen Sie dessen `BarStyles`‑Sammlung auf dieselbe Weise.

**Q: Gibt es ein Limit für die Anzahl der Balkenstile, die ich definieren kann?**  
A: Praktisch gibt es kein Limit; Sie können beliebig viele hinzufügen, sollten jedoch die Leistung bei sehr großen Sammlungen im Auge behalten.

**Q: Muss ich `project.Calculate()` nach dem Ändern von Stilen aufrufen?**  
A: Nein, die Stile werden während des Speicher‑Vorgangs angewendet; eine Neuberechnung ist nur bei Terminplanänderungen erforderlich.

---

**Zuletzt aktualisiert:** 2026-04-06  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
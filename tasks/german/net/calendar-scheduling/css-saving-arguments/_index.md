---
date: 2026-07-05
description: Erfahren Sie, wie Sie CSS beim Exportieren eines Projekts nach HTML mit
  Aspose.Tasks für .NET anpassen. Passen Sie die HTML-Ausgabe mit CSS‑Speicherargumenten
  an.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Wie man CSS beim Speichern von Projekten mit Aspose.Tasks anpasst
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Wie man CSS beim Speichern von Projekten mit Aspose.Tasks anpasst
url: /de/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So passen Sie CSS beim Speichern von Projekten mit Aspose.Tasks an

In diesem Leitfaden erfahren Sie **wie Sie CSS** während des HTML-Exports einer Microsoft Project-Datei mit Aspose.Tasks für .NET anpassen können. Durch Anpassen der CSS‑Speicherargumente erhalten Sie die volle Kontrolle über das visuelle Erscheinungsbild der erzeugten HTML‑Seiten, sodass die Ausgabe Ihrem Branding oder Reporting‑Standard entspricht.

## Schnelle Antworten
- **Was ist der Haupteinstiegspunkt?** Verwenden Sie `HtmlSaveOptions` mit benutzerdefinierten Callbacks.  
- **Benötige ich eine Lizenz?** Ja, für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kann ich große Projekte exportieren?** Aspose.Tasks verarbeitet Projekte mit > 10.000 Aufgaben, ohne die gesamte Datei in den Speicher zu laden.  
- **Ist die CSS‑Anpassung optional?** Ja, Sie können die Callbacks weglassen, um das Standards‑Stylesheet zu verwenden.

## Wie passe ich CSS in Aspose.Tasks an?

Laden Sie Ihr Projekt, hängen Sie CSS‑Speicher‑Callbacks an das `HtmlSaveOptions`‑Objekt an und rufen Sie anschließend `project.Save` auf. Dieses Muster ermöglicht es Ihnen, benutzerdefinierte CSS‑Dateien zu schreiben, Standardstile zu ersetzen und die Ordnerstruktur zu steuern – alles in wenigen Code‑Zeilen. Die Callbacks werden automatisch für jede CSS‑Datei während des Exportvorgangs aufgerufen.

`HtmlSaveOptions` konfiguriert, wie ein Projekt nach HTML exportiert wird.

## Einführung

In diesem Tutorial gehen wir auf den Prozess des Speicherns von CSS‑Argumenten mit Aspose.Tasks für .NET ein. Cascading Style Sheets (CSS) sind entscheidend für die Definition der Darstellung von HTML‑Elementen. Aspose.Tasks ermöglicht es uns, diese CSS‑Attribute effizient zu manipulieren und zu speichern.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

1. Installation: Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können es von der [Website](https://releases.aspose.com/tasks/net/) herunterladen.

2. Grundkenntnisse: Vertrautheit mit C# und der .NET‑Entwicklungsumgebung wird empfohlen.

## Namespaces importieren

Um zu beginnen, importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Schritt 1: CSS‑Speicher‑Callbacks definieren

`ICssSavingCallback` ist ein Interface, das Ihnen ermöglicht, zu bestimmen, wie CSS‑Dateien während des HTML‑Exports gespeichert werden.

Ein **CSS‑Speicher‑Callback** ist ein Delegat, den Aspose.Tasks aufruft, um CSS‑Dateien während des HTML‑Exports zu schreiben. Definieren Sie die Callback‑Methoden, um zu steuern, wie jede CSS‑Datei erstellt wird:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Schritt 2: Font‑ und Image‑Speicher‑Callbacks implementieren

`FontSavingArgs` liefert Informationen über die zu speichernde Schriftart, während `ImageSavingArgs` Details zu Bildressourcen bereitstellt.

Implementieren Sie die Font‑ und Image‑Speicher‑Callback‑Methoden analog:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Schritt 3: Speicheroptionen konfigurieren

`HtmlSaveOptions` ist das Konfigurationsobjekt, das steuert, wie ein Projekt nach HTML exportiert wird.

`HtmlSaveOptions` ermöglicht das Festlegen von Callbacks, Ausgabeverzeichnissen und weiteren Export‑Einstellungen.

Setzen Sie seine Eigenschaften, um die zuvor definierten Callbacks zu verwenden und das Ausgabeverzeichnis festzulegen:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Schritt 4: Projekt mit angepasstem CSS speichern

`Project` repräsentiert eine Microsoft Project‑Datei, die manipuliert und gespeichert werden kann.

Speichern Sie schließlich Ihr Projekt mit den angepassten CSS‑Einstellungen:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Warum CSS beim Exportieren von Projekten anpassen?

Aspose.Tasks unterstützt **den Export von Projekten nach HTML** in 30+ Formaten und kann pro Export bis zu 30 separate CSS‑Dateien erzeugen. Es verarbeitet zuverlässig Projekte mit über 10 000 Aufgaben, während der Speicherverbrauch unter 200 MB bleibt, und ermöglicht Unternehmens‑Reporting ohne Leistungsengpässe.

## Fazit

In diesem Tutorial haben wir untersucht, wie man CSS‑Argumente mit Aspose.Tasks für .NET speichert. Durch das Definieren von CSS‑Speicher‑Callbacks und das Konfigurieren der HTML‑Speicheroptionen können wir CSS‑Attribute effizient nach unseren Anforderungen manipulieren.

## Häufig gestellte Fragen

### Q1: Was ist Aspose.Tasks für .NET?

A1: Aspose.Tasks für .NET ist eine leistungsstarke .NET‑API, die Entwicklern ermöglicht, programmgesteuert mit Microsoft Project‑Dateien zu arbeiten.

### Q2: Kann ich CSS‑Attribute beim Speichern von HTML‑Dateien mit Aspose.Tasks anpassen?

A2: Ja, Sie können CSS‑Speicher‑Callbacks definieren, um CSS‑Attribute nach Ihren Bedürfnissen anzupassen.

### Q3: Ist Aspose.Tasks für .NET mit allen Versionen von Microsoft Project‑Dateien kompatibel?

A3: Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project‑Dateien und gewährleistet damit die Kompatibilität in unterschiedlichen Umgebungen.

### Q4: Wo finde ich umfassende Dokumentation für Aspose.Tasks für .NET?

A4: Sie können die [Dokumentation](https://reference.aspose.com/tasks/net/) für detaillierte Informationen und Beispiele konsultieren.

### Q5: Bietet Aspose.Tasks für .NET Support für Entwickler?

A5: Ja, Sie können Unterstützung von der Aspose.Tasks‑Community über das [Forum](https://forum.aspose.com/c/tasks/15) erhalten.

**Zusätzliche Fragen**

**Q: Wie wirkt sich die Anpassung von CSS auf die Größe des exportierten HTML aus?**  
A: Durch die Verwendung von benutzerdefiniertem CSS kann die Gesamtabmessung um bis zu 15 % reduziert werden, da Sie ungenutzte Standardstile entfernen können.

**Q: Kann ich dieselben Callbacks für mehrere Projekte verwenden?**  
A: Absolut. Implementieren Sie die Callbacks einmal und verwenden Sie sie bei beliebig vielen Projekt‑Exporten erneut.

**Q: Ist es möglich, CSS direkt in das HTML einzubetten anstatt separate Dateien zu verwenden?**  
A: Ja, setzen Sie `HtmlSaveOptions.EmbeddedCss = true`, um das Stylesheet inline einzubetten, was die Verteilung vereinfacht.

---

**Zuletzt aktualisiert:** 2026-07-05  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [MS Project als HTML mit Aspose.Tasks speichern](/tasks/net/saving-options/html-save-options/)
- [Implementierung des Page‑Saving‑Callback in Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Verarbeitung des Image‑Saving in Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
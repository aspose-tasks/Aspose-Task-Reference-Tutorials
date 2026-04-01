---
date: 2026-03-08
description: Erfahren Sie, wie Sie eine Projektdatei mit Aspose.Tasks für .NET importieren,
  einschließlich der Angabe der Dateicodierung und des effizienten Ladens einer Microsoft‑Project‑Datei.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projektdatei importieren – Optionen zum Laden in Aspose.Tasks
url: /de/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektdatei importieren – Optionen zum Laden in Aspose.Tasks

## Einführung

Aspose.Tasks for .NET macht es einfach, **import project file**‑Daten aus Microsoft Project, Primavera und anderen Formaten zu importieren. Egal, ob Sie eine passwortgeschützte Datei lesen, eine benutzerdefinierte Codierung festlegen oder Parsing‑Fehler behandeln müssen, die Bibliothek bietet Ihnen feinkörnige Kontrolle über die Ladeoptionen. In diesem Tutorial führen wir Sie durch die gängigsten Szenarien, damit Sie **load Microsoft Project file**‑Objekte in Ihren .NET‑Anwendungen sicher laden können.

## Schnelle Antworten
- **Was ist die primäre Methode, um eine Projektdatei zu importieren?** Verwenden Sie den `Project`‑Konstruktor mit einer `LoadOptions`‑Instanz.  
- **Kann ich passwortgeschützte Dateien öffnen?** Ja – setzen Sie die `Password`‑Eigenschaft auf `LoadOptions`.  
- **Wie gebe ich die Dateicodierung an?** Weisen Sie ein `Encoding`‑Objekt `LoadOptions.Encoding` zu.  
- **Ist die Fehlerbehandlung anpassbar?** Absolut – übergeben Sie einen Delegaten an `LoadOptions.ErrorHandler`.  
- **Funktionieren diese Optionen mit Primavera‑Dateien?** Ja, über `PrimaveraReadOptions` innerhalb von `LoadOptions`.

## Voraussetzungen

1. **Visual Studio** (oder jede bevorzugte .NET‑IDE).  
2. **Aspose.Tasks for .NET** – laden Sie es von der [Website](https://releases.aspose.com/tasks/net/) herunter.  
3. Grundlegende Kenntnisse der **C#**‑Syntax und Projektstruktur.

Jetzt, da wir eingerichtet sind, importieren wir die erforderlichen Namespaces.

## Namespaces importieren

Fügen Sie in Ihrem C#‑Projekt die folgenden `using`‑Anweisungen hinzu, damit die API‑Klassen verfügbar sind:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## So importieren Sie Projektdateien mit Ladeoptionen

Im Folgenden finden Sie vier praktische Beispiele, die die häufigsten Ladeszenarien abdecken.

### Schritt 1: Ein passwortgeschütztes Projekt laden

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Schritt 2: Ein Primavera‑Projekt mit benutzerdefinierten Optionen laden

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Schritt 3: **Dateicodierung angeben** beim Import einer XER‑Datei

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Schritt 4: Ein Primavera‑Projekt mit benutzerdefinierter Fehlerbehandlung laden

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Wenn Sie diese Schritte befolgen, können Sie **import project file**‑Daten präzise importieren, den Ladevorgang an Ihre Bedürfnisse anpassen und Ihre Anwendung robust halten.

## Häufige Probleme & Tipps

- **Falsches Passwort** – die `Password`‑Eigenschaft löst eine Ausnahme aus; prüfen Sie die Anmeldeinformationen vor dem Laden.  
- **Nicht unterstützte Codierung** – stellen Sie sicher, dass die angegebene Codepage auf dem Zielsystem vorhanden ist (`Encoding.GetEncoding(1251)` funktioniert für Kyrillisch).  
- **Fehlende Primavera‑Optionen** – wenn Sie Aufgaben‑UIDs erhalten müssen, setzen Sie `PreserveUids = true`; andernfalls können doppelte IDs auftreten.  
- **Error handler returning null** – die Rückgabe von `null` signalisiert dem Parser, das problematische Element zu überspringen; passen Sie dies nach Bedarf an.

## Häufig gestellte Fragen

**F: Ist Aspose.Tasks for .NET mit allen Versionen von Microsoft Project kompatibel?**  
A: Ja, es unterstützt eine breite Palette von Microsoft Project‑Versionen, sodass Sie **load Microsoft Project file**‑Formate von älteren MPP‑Dateien bis zu den neuesten Formaten **laden** können.

**F: Kann ich Aspose.Tasks for .NET mit anderen Drittanbieter‑Bibliotheken integrieren?**  
A: Absolut. Die Bibliothek arbeitet nahtlos mit anderen .NET‑Paketen zusammen, sodass Sie sie mit Reporting‑, UI‑ oder Datenzugriffs‑Frameworks kombinieren können.

**F: Bietet Aspose.Tasks for .NET Dokumentations‑ und Support‑Ressourcen?**  
A: Ja, Sie können die umfassende [Dokumentation](https://reference.aspose.com/tasks/net/) konsultieren und über das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) Support erhalten.

**F: Gibt es Lizenzierungsoptionen für Aspose.Tasks for .NET?**  
A: Ja, Sie können verschiedene Lizenzierungsoptionen, einschließlich kostenloser Testversionen und temporärer Lizenzen, auf der [Aspose.Tasks‑Website](https://purchase.aspose.com/buy) erkunden.

**F: Wie häufig werden Updates und neue Funktionen für Aspose.Tasks for .NET veröffentlicht?**  
A: Aspose.Tasks erhält regelmäßige Updates, die Funktionen hinzufügen, die Leistung verbessern und die Kompatibilität mit den neuesten Microsoft Project‑Versionen sicherstellen.

---

**Zuletzt aktualisiert:** 2026-03-08  
**Getestet mit:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
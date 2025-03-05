---
title: Optionen zum Laden in Aspose.Tasks
linktitle: Optionen zum Laden in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie anhand einer Schritt-für-Schritt-Anleitung, wie Sie die Leistungsfähigkeit von Aspose.Tasks für .NET nutzen können, um Microsoft Project-Dokumente effizient zu verwalten.
type: docs
weight: 16
url: /de/net/advanced-concepts/loading-options/
---
## Einführung

Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Microsoft Project-Dokumente programmgesteuert zu bearbeiten. Unabhängig davon, ob Sie Projektdateien erstellen, lesen, schreiben oder konvertieren müssen, bietet Aspose.Tasks eine breite Palette an Funktionen zur Optimierung Ihrer Aufgaben. In diesem Tutorial befassen wir uns mit den Grundlagen der Verwendung von Aspose.Tasks für .NET und zerlegen wichtige Prozesse in einfache, umsetzbare Schritte.

## Voraussetzungen

Bevor Sie sich mit Aspose.Tasks für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio: Installieren Sie Visual Studio oder eine andere IDE Ihrer Wahl.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis von C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.

Nachdem wir nun alle Voraussetzungen erfüllt haben, erkunden wir die wesentlichen Namespaces und tauchen in die Schritt-für-Schritt-Anleitung ein.

## Namensräume importieren

Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um auf die Funktionen von Aspose.Tasks zuzugreifen:

1. Aspose.Tasks: Dieser Namespace stellt Kernklassen und Schnittstellen für die Arbeit mit Projektdokumenten bereit.

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

Lassen Sie uns nun verschiedene Aufgaben in Schritt-für-Schritt-Anleitungen aufschlüsseln.

## Schritt 1: Laden passwortgeschützter Projekte

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialisieren Sie FileStream, um die Projektdatei zu laden
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Erstellen Sie eine LoadOptions-Instanz
        var options = new LoadOptions
        {
            Password = "password" // Legen Sie das Passwort fest
        };

        // Laden Sie das Projekt mit den angegebenen Optionen
        var project = new Project(stream, options);

        // Projektname anzeigen
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## Schritt 2: Laden von Primavera-Projekten mit benutzerdefinierten Optionen

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Erstellen Sie eine LoadOptions-Instanz
    var loadOptions = new LoadOptions();

    // Konfigurieren Sie die Primavera-Leseoptionen
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Legen Sie die Projekt-UID fest
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Legen Sie die Primavera-Leseoptionen fest
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Laden Sie das Primavera-Projekt mit den angegebenen Optionen
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Projektname anzeigen
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Führen Sie weitere Vorgänge mit dem geladenen Projekt durch
}
```

## Schritt 3: Dateikodierung angeben

```csharp
public void SpecifyFileEncoding()
{
    // Erstellen Sie eine LoadOptions-Instanz
    LoadOptions lo = new LoadOptions();

    // Geben Sie die Kodierung an, wenn Sie ein Projekt aus einer Primavera-XER-Datei öffnen
    lo.Encoding = Encoding.GetEncoding(1251);

    // Laden Sie das Projekt mit der angegebenen Kodierung
    var project = new Project("encoding1251.xer", lo);

    // Führen Sie weitere Vorgänge mit dem geladenen Projekt durch
}
```

## Schritt 4: Laden von Primavera-Projekten mit Fehlerbehandlung

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Erstellen Sie eine LoadOptions-Instanz
    var loadOptions = new LoadOptions();

    // Konfigurieren Sie die Primavera-Leseoptionen
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Legen Sie die Projekt-UID fest
    };

    // Legen Sie die Primavera-Leseoptionen fest
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //Legen Sie eine benutzerdefinierte Fehlerbehandlung fest
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Laden Sie das Primavera-Projekt mit den angegebenen Optionen und Fehlerbehandlung
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Führen Sie weitere Vorgänge mit dem geladenen Projekt durch
}

// Benutzerdefinierte Fehlerbehandlungsmethode
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implementieren Sie eine benutzerdefinierte Fehlerbehandlungslogik
}
```

Wenn Sie diese Schritte befolgen, können Sie die Ladeoptionen in Aspose.Tasks für .NET effektiv nutzen, um Projektdokumente entsprechend Ihren Anforderungen zu bearbeiten.

## Abschluss

In diesem Tutorial haben wir die Grundlagen der Arbeit mit Ladeoptionen in Aspose.Tasks für .NET untersucht. Vom Laden kennwortgeschützter Projekte bis hin zur Festlegung einer benutzerdefinierten Fehlerbehandlung – die Beherrschung dieser Techniken ermöglicht Ihnen die effiziente Verwaltung von Projektdateien in Ihren .NET-Anwendungen.

## FAQs

### F1: Ist Aspose.Tasks für .NET mit allen Versionen von Microsoft Project kompatibel?

A1: Ja, Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.

### F2: Kann ich Aspose.Tasks für .NET in andere Bibliotheken von Drittanbietern integrieren?

A2: Absolut, Aspose.Tasks für .NET lässt sich nahtlos in andere .NET-Bibliotheken integrieren und bietet erweiterte Funktionalität und Flexibilität.

### F3: Bietet Aspose.Tasks für .NET Dokumentation und Supportressourcen?

 A3: Ja, Sie können sich auf die Gesamtübersicht beziehen[Dokumentation](https://reference.aspose.com/tasks/net/) und Zugriff auf Unterstützung über die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).

### F4: Gibt es Lizenzoptionen für Aspose.Tasks für .NET?

 A4: Ja, Sie können verschiedene Lizenzierungsoptionen erkunden, darunter kostenlose Testversionen und temporäre Lizenzen[Aspose.Tasks-Website](https://purchase.aspose.com/buy).

### F5: Wie häufig werden Updates und neue Funktionen für Aspose.Tasks für .NET veröffentlicht?

A5: Aspose.Tasks für .NET erhält regelmäßige Updates und Funktionserweiterungen, um optimale Leistung und Kompatibilität mit sich entwickelnden Technologien sicherzustellen.
---
title: Verwalten Sie Projektgliederungscodes in Aspose.Tasks für .NET
linktitle: Gliederungscodes in Aspose.Tasks verwalten
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Gliederungscodes mit Aspose.Tasks für .NET verwalten. Vereinfachen Sie die Projektorganisation mühelos.
type: docs
weight: 10
url: /de/net/outline-code-page-settings/outline-codes/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie Microsoft Project-Gliederungscodes mit Aspose.Tasks für .NET verwalten. Gliederungscodes sind benutzerdefinierte Felder in Microsoft Project, die es Benutzern ermöglichen, Aufgaben nach bestimmten Kriterien zu kategorisieren und zu organisieren. Aspose.Tasks vereinfacht das programmgesteuerte Lesen und Bearbeiten dieser Gliederungscodes.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Richten Sie eine geeignete Entwicklungsumgebung für die .NET-Programmierung ein, beispielsweise Visual Studio.
3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist für das Verständnis der Codebeispiele von Vorteil.

## Namensräume importieren
Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Dadurch können Sie auf die von der Aspose.Tasks-Bibliothek bereitgestellten Klassen und Methoden zugreifen.
1. Öffnen Sie Visual Studio: Starten Sie Ihre Visual Studio-IDE.
2. Erstellen Sie ein neues Projekt: Starten Sie ein neues C#-Projekt oder öffnen Sie ein vorhandenes, in dem Sie Aspose.Tasks verwenden möchten.
3. Aspose.Tasks-Referenz hinzufügen: Klicken Sie mit der rechten Maustaste auf Ihr Projekt im Projektmappen-Explorer, wählen Sie „NuGet-Pakete verwalten“, suchen Sie nach „Aspose.Tasks“ und installieren Sie die neueste Version.
4. Aspose.Tasks-Namespace importieren: Fügen Sie oben in Ihrer C#-Datei die folgende using-Anweisung hinzu:
```csharp
using Aspose.Tasks;
using System;

```
## Schritt 1: Dokumentenverzeichnis definieren
Legen Sie zunächst den Pfad zu dem Verzeichnis fest, das Ihre MS Project-Datei enthält.
```csharp
String DataDir = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrer Projektdatei.
## Schritt 2: Laden Sie die Projektdatei
 Instanziieren Sie eine neue`Project` Objekt durch Laden der MS Project-Datei.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Dadurch wird das Projektobjekt mit der angegebenen Datei initialisiert.
## Schritt 3: Gliederungscodes lesen
Durchlaufen Sie alle Aufgaben im Projekt und rufen Sie deren Gliederungscodes ab.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Dieses Code-Snippet durchläuft jede Aufgabe, prüft, ob Gliederungscodes vorhanden sind, und gibt Details wie Feld-ID, Wert-GuID und Wert-ID für jeden mit der Aufgabe verknüpften Gliederungscode aus.

## Abschluss
Zusammenfassend bietet Aspose.Tasks für .NET leistungsstarke Funktionen für die programmgesteuerte Verwaltung von Microsoft Project-Gliederungscodes. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Gliederungscodes in Ihren MS Project-Dateien mit C# effizient lesen und bearbeiten.
## FAQs
### F: Kann ich Gliederungscodes mit Aspose.Tasks ändern?
A: Ja, Sie können Gliederungscodes programmgesteuert mit Aspose.Tasks für .NET ändern. Greifen Sie einfach auf die Gliederungscodes der Aufgaben zu und aktualisieren Sie deren Werte nach Bedarf.
### F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?
A: Aspose.Tasks unterstützt eine Vielzahl von Microsoft Project-Versionen, einschließlich 2003, 2007, 2010, 2013, 2016 und 2019.
### F: Benötigt Aspose.Tasks eine Lizenz für die kommerzielle Nutzung?
A: Ja, für die kommerzielle Nutzung von Aspose.Tasks ist eine gültige Lizenz erforderlich. Eine Lizenz erhalten Sie auf der Aspose-Website.
### F: Kann ich Aspose.Tasks vor dem Kauf testen?
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks von der Website herunterladen, um die Funktionen und Fähigkeiten zu testen.
### F: Wo kann ich Unterstützung für Aspose.Tasks erhalten?
 A: Sie können Unterstützung für Aspose.Tasks erhalten, indem Sie das Forum unter besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).## Vollständiger Quellcode
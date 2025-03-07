---
title: Extrahieren wiederkehrender Aufgabeninformationen in Aspose.Tasks
linktitle: Extrahieren wiederkehrender Aufgabeninformationen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET wiederkehrende Aufgabeninformationen aus MS Project-Dateien extrahieren. Einfache Integration für .NET-Entwickler.
weight: 13
url: /de/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahieren wiederkehrender Aufgabeninformationen in Aspose.Tasks

## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, in ihren .NET-Anwendungen mit Microsoft Project-Dateien zu arbeiten. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks wiederkehrende Aufgabeninformationen aus MS Project-Dateien extrahieren.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundlegendes Verständnis der Programmiersprache C#.
2. Visual Studio ist auf Ihrem System installiert.
3.  Aspose.Tasks für .NET-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihren C#-Code:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen:
## Schritt 1: Richten Sie den Projektdateipfad ein
```csharp
String DataDir = "Your Document Directory";
```
 Ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrer MS Project-Datei.
## Schritt 2: Laden Sie die MS Project-Datei
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Diese Zeile initialisiert eine neue`Project` Objekt durch Laden der durch den Pfad angegebenen MS Project-Datei.
## Schritt 3: Lesen Sie wiederkehrende Informationen zu Aufgaben
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Auf wiederkehrende Aufgabeninformationen zugreifen und diese anzeigen
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Zeigen Sie bei Bedarf weiterhin Informationen zu wiederkehrenden Aufgaben an
}
```
Diese Schleife durchläuft alle Aufgaben im Projekt und prüft, ob mit jeder Aufgabe wiederkehrende Informationen verknüpft sind. Wenn dies der Fall ist, werden verschiedene Eigenschaften der wiederkehrenden Aufgabe abgerufen und angezeigt, z. B. Startdatum, Dauer, Enddatum usw.
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für .NET wiederkehrende Aufgabeninformationen aus MS Project-Dateien extrahiert. Mit diesem Wissen können Sie diese Funktionalität nun in Ihre .NET-Anwendungen integrieren, um wiederkehrende Aufgaben effizienter zu bearbeiten.
## FAQs
### F: Kann ich wiederkehrende Aufgabeninformationen mit Aspose.Tasks für .NET ändern?
A: Ja, Sie können Informationen zu wiederkehrenden Aufgaben mithilfe der bereitgestellten APIs programmgesteuert ändern.
### F: Unterstützt Aspose.Tasks neben MS Project auch andere Projektdateiformate?
A: Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate wie MPP, XML und CSV.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### F: Wo finde ich Dokumentation für Aspose.Tasks für .NET?
 A: Sie finden die Dokumentation[Hier](https://reference.aspose.com/tasks/net/).
### F: Wie erhalte ich technischen Support für Aspose.Tasks für .NET?
 A: Technischen Support erhalten Sie im Aspose.Tasks-Forum[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

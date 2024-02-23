---
title: Sammeln Sie MS Project von Split Parts in Aspose.Tasks
linktitle: Sammlung geteilter Teile in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie geteilte Teile in MS Project mit Aspose.Tasks für .NET sammeln. Dieses umfassende Tutorial führt Sie Schritt für Schritt durch den Prozess.
type: docs
weight: 19
url: /de/net/rate-recurring-tasks/split-part-collection/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie geteilte Teile in MS Project mit Aspose.Tasks für .NET sammeln. Das Aufteilen von Aufgaben in Teile kann ein entscheidender Aspekt des Projektmanagements sein, und Aspose.Tasks bietet praktische Methoden, um dies effizient zu erledigen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Installation von Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie Aspose.Tasks für .NET installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
2. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil, da wir Codefragmente in C# schreiben werden.

## Namespaces importieren
Fügen Sie in Ihr C#-Projekt die erforderlichen Namespaces ein:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues Projekt in Ihrer bevorzugten IDE und stellen Sie sicher, dass Aspose.Tasks für .NET korrekt referenziert wird.
## Schritt 2: Initialisieren Sie das Projektobjekt
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Initialisieren Sie ein neues Projektobjekt mit dem Pfad zu Ihrer MS Project-Datei.
## Schritt 3: Aufgabe abrufen und über geteilte Teile iterieren
```csharp
var task = project.RootTask.Children.GetById(1);
// Iterieren Sie über geteilte Teile
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Rufen Sie die Aufgabe aus dem Projekt ab, durchlaufen Sie ihre aufgeteilten Teile und drucken Sie deren Start- und Enddatum aus.
## Schritt 4: Teil nach Index aufteilen
```csharp
// Holen Sie sich das Teil nach Index
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Rufen Sie ein bestimmtes geteiltes Teil nach Index ab und drucken Sie dessen Startdatum aus.

## Abschluss
Die Verwaltung geteilter Teile in MS Project-Dateien kann die Effizienz des Projektmanagements erheblich steigern. Aspose.Tasks für .NET vereinfacht diesen Prozess durch die Bereitstellung intuitiver APIs zur nahtlosen Abwicklung aufgeteilter Aufgaben.
## FAQs
### F: Kann ich Aufgaben während der Laufzeit dynamisch aufteilen?
A: Ja, Sie können Aufgaben programmgesteuert mit Aspose.Tasks für .NET aufteilen.
### F: Unterstützt Aspose.Tasks alle Versionen von MS Project-Dateien?
A: Aspose.Tasks unterstützt verschiedene Versionen von MS Project-Dateien und gewährleistet so die Kompatibilität zwischen verschiedenen Plattformen.
### F: Gibt es zu Testzwecken eine Testversion?
 A: Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/) zur Auswertung.
### F: Wie kann ich temporäre Lizenzen für meine Projekte erhalten?
 A: Temporäre Lizenzen können bei erworben werden[Hier](https://purchase.aspose.com/temporary-license/) für den kurzfristigen Einsatz.
### F: Wo kann ich Hilfe oder Unterstützung zu Aspose.Tasks suchen?
 A: Sie können das Aspose.Tasks-Forum besuchen[Hier](https://forum.aspose.com/c/tasks/15) um Hilfe von der Community oder dem Aspose-Supportteam zu erhalten.
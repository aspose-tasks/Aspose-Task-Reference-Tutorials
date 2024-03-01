---
title: Sammlung von Gliederungscodes für MS Project in Aspose.Tasks
linktitle: Sammlung von Gliederungscodes in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Gliederungscodes mit Aspose.Tasks für .NET sammeln. Dieses umfassende Tutorial bietet Schritt-für-Schritt-Anleitungen.
type: docs
weight: 11
url: /de/net/outline-code-page-settings/outline-code-collection/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie Microsoft Project-Gliederungscodes mit Aspose.Tasks für .NET sammeln. Wir unterteilen den Prozess in Schritt-für-Schritt-Anleitungen, um Klarheit und Verständnis zu gewährleisten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Visual Studio: Installieren Sie Visual Studio auf Ihrem System.
2.  Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse der C#-Programmierung: Kenntnisse in C# sind von Vorteil.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces, um auf die Aspose.Tasks-Funktionalität in Ihrem C#-Projekt zuzugreifen.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Schritt 1: Laden Sie die Projektdatei
 Beginnen Sie mit dem Laden der Microsoft Project-Datei mithilfe von`Project` Klasse.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Schritt 2: Gliederungscodes sammeln
Erstellen Sie einen Collector, um die Gliederungscodes aus den Projektaufgaben zu sammeln.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Schritt 3: Durchlaufen Sie Aufgaben und Gliederungscodes
Durchlaufen Sie die gesammelten Aufgaben und Gliederungscodes und drucken Sie deren Details aus.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Schritt 4: Fügen Sie eine benutzerdefinierte Gliederungscodedefinition hinzu
Fügen Sie dem Projekt eine benutzerdefinierte Gliederungscodedefinition hinzu.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Schritt 5: Gliederungscode erstellen und einfügen
Erstellen Sie einen Gliederungscode und fügen Sie ihn in eine Aufgabe ein.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Schritt 6: Gliederungscodes bearbeiten
Bearbeiten Sie die Gliederungscodes nach Bedarf, z. B. Einfügen, Entfernen oder Löschen.
```csharp
// Beispiel einer Manipulation
// ...
// Geben Sie den Code mit 2 an der rechten Position ein
task.OutlineCodes.Insert(2, code2);
// Überprüfen Sie, ob der Code eingegeben wurde
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Microsoft Project-Gliederungscodes mit Aspose.Tasks für .NET sammelt. Wenn Sie diese Schritte befolgen, können Sie Gliederungscodes in Ihren Projekten effektiv verwalten und so die Organisation und Klarheit verbessern.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit anderen Programmiersprachen verwenden?
A: Ja, Aspose.Tasks für .NET zielt in erster Linie auf die .NET-Plattform ab, bietet aber über Aspose.Tasks für Cloud auch Unterstützung für andere Programmiersprachen.
### F: Gibt es Einschränkungen hinsichtlich der Größe der Projektdateien, die Aspose.Tasks für .NET verarbeiten kann?
A: Aspose.Tasks für .NET kann große Projektdateien effizient verarbeiten, die Leistung kann jedoch je nach Komplexität und Größe der Datei variieren.
### F: Ist Aspose.Tasks für .NET mit den neuesten Versionen von Microsoft Project kompatibel?
A: Ja, Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project, einschließlich der neuesten.
### F: Kann ich das Ausgabeformat anpassen, wenn ich mit Aspose.Tasks für .NET arbeite?
A: Absolut, Aspose.Tasks für .NET bietet umfangreiche Optionen zum Anpassen des Ausgabeformats an Ihre Anforderungen.
### F: Wo finde ich zusätzliche Unterstützung oder Ressourcen für Aspose.Tasks für .NET?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für jegliche Unterstützung oder Fragen zu Aspose.Tasks für .NET.
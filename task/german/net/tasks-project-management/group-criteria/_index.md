---
title: Manipulation von MS Project-Gruppenkriterien in Aspose.Tasks
linktitle: Gruppenkriterien in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Dateien mithilfe von Aspose.Tasks programmgesteuert in .NET bearbeiten. Schritt-für-Schritt-Beispiele zum Abrufen von Aufgabengruppen- und Kriteriumsinformationen.
type: docs
weight: 27
url: /de/net/tasks-project-management/group-criteria/
---
## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke API, die die Arbeit mit Microsoft Project-Dateien in Ihren .NET-Anwendungen erleichtert. Unabhängig davon, ob Sie Projektmanagementsoftware entwickeln oder Projektdaten programmgesteuert bearbeiten müssen, bietet Aspose.Tasks einen umfassenden Satz an Funktionen, die Ihren Anforderungen gerecht werden.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Kenntnisse in C# und .NET Framework
Um die in diesem Tutorial bereitgestellten Beispiele zu verstehen und umzusetzen, sind Kenntnisse der Programmiersprache C# und des .NET Frameworks unerlässlich.
### 2. Installation von Aspose.Tasks für .NET
 Stellen Sie sicher, dass Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/tasks/net/) und befolgen Sie die mitgelieferten Installationsanweisungen.
### 3. Integrierte Entwicklungsumgebung (IDE)
Installieren Sie auf Ihrem System eine IDE wie Visual Studio zum Schreiben und Ausführen von C#-Code.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihren C#-Code:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Schritt 1: Laden Sie eine Microsoft Project-Datei
Geben Sie zunächst den Pfad zu Ihrer Microsoft Project-Datei an:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrer Projektdatei.
## Schritt 2: Informationen zu Aufgabengruppen abrufen
Rufen Sie als Nächstes Informationen zu Aufgabengruppen im Projekt ab:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Dieser Codeausschnitt gibt die Gesamtzahl der Aufgabengruppen aus, ruft die zweite Aufgabengruppe, ihren Namen und die Anzahl der darin enthaltenen Kriterien ab.
## Schritt 3: Kriteriumsinformationen der Aufgabengruppe abrufen
Schauen wir uns nun die Details eines bestimmten Kriteriums innerhalb der Aufgabengruppe an:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
In diesem Segment werden verschiedene Eigenschaften des Kriteriums angezeigt, z. B. Index, Feld, Gruppierungsinformationen, Zellenfarbe, Schriftfarbe, Gruppenintervall und Startpunkt.
## Schritt 4: Rufen Sie die Schriftartinformationen von Criterion ab
Erhalten Sie abschließend schriftbezogene Details des Kriteriums:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
In diesem Schritt werden der Name, die Größe und der Stil der Schriftart sowie die Angabe, ob das Kriterium in aufsteigender oder absteigender Reihenfolge sortiert ist, ausgedruckt.

## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie Aspose.Tasks für .NET verwenden, um Informationen zu Aufgabengruppen und Kriterien aus einer Microsoft Project-Datei abzurufen. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie in Ihren .NET-Anwendungen effizient und programmgesteuert mit Projektdaten arbeiten.
## FAQs
### Kann Aspose.Tasks große Microsoft Project-Dateien verarbeiten?
Aspose.Tasks ist für die effiziente Verarbeitung großer Projektdateien optimiert und gewährleistet so eine hohe Leistung und Zuverlässigkeit.
### Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?
Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität zwischen verschiedenen Dateiformaten.
### Kann ich Projektdaten mit Aspose.Tasks manipulieren?
Aspose.Tasks bietet auf jeden Fall umfangreiche Funktionen zur Bearbeitung von Projektdaten, einschließlich Aufgaben, Ressourcen, Kalendern und mehr.
### Bietet Aspose.Tasks Unterstützung für verschiedene .NET-Plattformen?
Ja, Aspose.Tasks unterstützt mehrere .NET-Plattformen, einschließlich .NET Framework, .NET Core und .NET Standard.
### Gibt es ein Community-Forum für Aspose.Tasks, in dem ich Hilfe suchen kann?
 Ja, Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um Fragen zu stellen, Wissen auszutauschen und mit anderen Benutzern zusammenzuarbeiten.
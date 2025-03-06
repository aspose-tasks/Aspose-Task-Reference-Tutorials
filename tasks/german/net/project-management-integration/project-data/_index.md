---
title: Projektdaten mit Aspose.Tasks beherrschen
linktitle: Arbeiten mit Projektdaten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Daten mithilfe von Aspose.Tasks in .NET bearbeiten. Erstellen Sie ganz einfach Aufgaben, fügen Sie Ressourcen hinzu und speichern Sie Projekte.
weight: 16
url: /de/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektdaten mit Aspose.Tasks beherrschen

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Tasks-Bibliothek für .NET mit Microsoft Project-Daten arbeiten. Aspose.Tasks bietet leistungsstarke Funktionen zum Bearbeiten von Projektdateien, einschließlich der Erstellung von Aufgaben, dem Hinzufügen von Ressourcen, dem Festlegen von Eigenschaften und dem Speichern von Projekten in verschiedenen Formaten.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Installation der Aspose.Tasks-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie[Hier](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine .NET-Entwicklungsumgebung eingerichtet haben.
3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.

## Namespaces importieren
Bevor Sie mit Aspose.Tasks arbeiten, importieren Sie die erforderlichen Namespaces in Ihr Projekt:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt 1: Projektobjekt initialisieren
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Diese Zeile initialisiert eine neue Instanz von`Project` Klasse, die eine Microsoft Project-Datei darstellt.
## Schritt 2: Projekteigenschaften festlegen
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Diese Zeilen veranschaulichen, wie Eigenschaften des Projekts wie Arbeitsformat und Aufgabenerstellungsmodus festgelegt werden.
## Schritt 3: Aufgaben hinzufügen
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Hier wird eine neue Aufgabe mit dem Namen „Aufgabe 1“ zur Stammaufgabe des Projekts hinzugefügt.
## Schritt 4: Aufgabeneigenschaften festlegen
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Diese Zeilen legen das Startdatum, die Dauer und das Enddatum für „Aufgabe 1“ fest.
## Schritt 5: Ressourcen hinzufügen
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
In diesem Teil wird gezeigt, wie Sie dem Projekt eine Arbeitsressource hinzufügen.
## Schritt 6: Zuweisen von Ressourcen zu Aufgaben
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Diese Zeilen zeigen, wie Sie die zuvor hinzugefügte Arbeitsressource „Aufgabe 1“ mit bestimmten Start-, Arbeits- und Endterminen zuweisen.
## Schritt 7: Projekt speichern
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Abschließend wird das Projekt im Microsoft Project XML-Dateiformat gespeichert.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.Tasks-Bibliothek in .NET mit Microsoft Project-Daten arbeitet. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Projektdateien bearbeiten, Aufgaben und Ressourcen hinzufügen, Ressourcen Aufgaben zuweisen und Projekte in verschiedenen Formaten speichern.
## FAQs
### F: Kann Aspose.Tasks komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks bietet umfassende Unterstützung für komplexe Projektstrukturen und ermöglicht Ihnen die effiziente Verwaltung von Aufgaben, Ressourcen und Zuweisungen.
### F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?
A: Aspose.Tasks unterstützt eine Vielzahl von Microsoft Project-Versionen und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### F: Kann ich Aspose.Tasks in andere .NET-Bibliotheken integrieren?
A: Absolut, Aspose.Tasks lässt sich nahtlos in andere .NET-Bibliotheken integrieren und bietet so Flexibilität in Ihren Entwicklungsprojekten.
### F: Bietet Aspose.Tasks Unterstützung für Projektplanungsalgorithmen?
A: Ja, Aspose.Tasks enthält erweiterte Planungsalgorithmen, die Ihnen helfen, Projektzeitpläne und Ressourcennutzung zu optimieren.
### F: Gibt es ein Community-Forum für Aspose.Tasks-Benutzer?
 A: Ja, Sie können hilfreiche Ressourcen finden und sich mit anderen Aspose.Tasks-Benutzern austauschen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Umgang mit MS Project-Ressourcenzuweisungen in Aspose.Tasks
linktitle: Umgang mit Ressourcenzuweisungen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Ressourcenzuweisungen mit Aspose.Tasks für .NET effizient bearbeiten. Diese umfassende Anleitung bietet Entwicklern Schritt-für-Schritt-Anleitungen.
type: docs
weight: 11
url: /de/net/resource-risk-analysis/resource-assignments/
---
## Einführung
In diesem Tutorial befassen wir uns mit der effizienten Handhabung von Microsoft Project-Ressourcenzuweisungen mithilfe von Aspose.Tasks für .NET. Aspose.Tasks ist eine leistungsstarke API, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten. Wenn Sie diese Schritte befolgen, erfahren Sie, wie Sie Ressourcenzuweisungen in Ihren .NET-Anwendungen effektiv verwalten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um die Aspose.Tasks-Funktionen in Ihrem .NET-Projekt nutzen zu können. Das beinhaltet:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um ein umfassendes Verständnis für die Handhabung von MS Project-Ressourcenzuweisungen mithilfe von Aspose.Tasks zu erhalten.
## Schritt 1: Projekt- und Kalendereinstellungen einrichten
Erstellen Sie zunächst eine neue Projektinstanz und richten Sie die Kalendereinstellungen des Projekts ein:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Schritt 2: Fügen Sie dem Projekt eine Aufgabe hinzu
Fügen Sie als Nächstes eine neue Aufgabe zur Stammaufgabe des Projekts hinzu:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Schritt 3: Erstellen Sie eine Ressourcenzuweisung und generieren Sie Zeitphasendaten
Erstellen Sie nun eine neue Ressourcenzuweisung für die Aufgabe und generieren Sie Zeitphasendaten:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Schritt 4: Teilen Sie die Aufgabe auf
Teilen Sie die Aufgabe in mehrere Teile auf, indem Sie Start- und Endtermine angeben:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Schritt 5: Arbeitskontur festlegen
Legen Sie den Arbeitskonturtyp für die Aufgabe fest:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Schritt 6: Speichern Sie das Projekt
Speichern Sie abschließend die Projektdatei mit den vorgenommenen Änderungen:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Abschluss
Zusammenfassend lässt sich sagen, dass die Bearbeitung von Microsoft Project-Ressourcenzuweisungen mit Aspose.Tasks für .NET ein unkomplizierter Prozess ist. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Ressourcenzuweisungen innerhalb Ihrer .NET-Anwendungen effizient verwalten.
## FAQs
### Kann Aspose.Tasks mit komplexen Projektstrukturen umgehen?
Ja, Aspose.Tasks bietet umfassende Funktionalitäten, um komplexe Projektstrukturen effizient abzuwickeln.
### Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project kompatibel?
Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### Kann ich Ressourcenzuweisungen basierend auf spezifischen Anforderungen anpassen?
Absolut, Aspose.Tasks bietet umfangreiche Anpassungsmöglichkeiten für Ressourcenzuweisungen, um spezifische Projektanforderungen zu erfüllen.
### Unterstützt Aspose.Tasks den Export von Projektdaten in andere Formate?
Ja, Aspose.Tasks ermöglicht den Export von Projektdaten in verschiedene Formate wie unter anderem XML, PDF und HTML.
### Ist technischer Support für Aspose.Tasks-Benutzer verfügbar?
Ja, Aspose bietet über sein Forum und andere Kanäle dedizierten technischen Support, um Benutzern bei Fragen oder Problemen behilflich zu sein.
---
title: Dauerbehandlung in Aspose.Tasks
linktitle: Dauerbehandlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie anhand von Schritt-für-Schritt-Anleitungen, wie Sie Dauern in Aspose.Tasks für .NET effektiv handhaben.
type: docs
weight: 30
url: /de/net/calendar-scheduling/duration-handling/
---
## Einführung

Der effektive Umgang mit Dauer ist in Projektmanagementanwendungen von entscheidender Bedeutung. Aspose.Tasks für .NET bietet robuste Funktionen für die effiziente Verwaltung von Dauern. In diesem Tutorial untersuchen wir verschiedene Aspekte der Dauerbehandlung mit Aspose.Tasks für .NET.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Grundkenntnisse in C#: Um die Beispiele zu verstehen und umzusetzen, ist die Vertrautheit mit der Programmiersprache C# unerlässlich.
2. Visual Studio: Installieren Sie die Visual Studio-IDE, um .NET-Anwendungen zu erstellen und auszuführen.
3.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).

## Namespaces importieren

Importieren wir zunächst die notwendigen Namespaces, um die Aspose.Tasks-Funktionen zu nutzen:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Lassen Sie uns jedes Beispiel in einer Schritt-für-Schritt-Anleitung in mehrere Schritte unterteilen:

## Aktualisieren der Dauer von Aufgaben

### Schritt 1: Projektdatei laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Schritt 2: Holen Sie sich Aufgabe und Dauer

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Schritt 3: Dauer aktualisieren

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Schritt 4: Aktualisierte Dauer anzeigen

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Subtrahieren der Dauer von Aufgaben

### Schritt 1: Projektdatei laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Schritt 2: Holen Sie sich Aufgabe und Dauer

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Schritt 3: Dauer abziehen

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Schritt 4: Aktualisierte Dauer anzeigen

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Konvertieren der Dauer in TimeSpan

### Schritt 1: Projektdatei laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Schritt 2: Holen Sie sich Aufgabe und Dauer

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Schritt 3: Konvertieren Sie die Dauer in die Zeitspanne

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Konvertieren der Dauer in einen String

### Schritt 1: Projektdatei laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Schritt 2: Holen Sie sich Aufgabe und Dauer

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Schritt 3: Konvertieren Sie die Dauer in einen String

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Abschluss

In diesem Tutorial haben wir verschiedene Aspekte der Dauerbehandlung in Aspose.Tasks für .NET behandelt. Für ein erfolgreiches Projektmanagement ist es von entscheidender Bedeutung, die Dauer zu verstehen und effektiv zu verwalten. Aspose.Tasks bietet umfassende Funktionalitäten zur Vereinfachung von Dauerverwaltungsaufgaben in Ihren .NET-Anwendungen.

## FAQs

### F1: Was ist Aspose.Tasks für .NET?

A1: Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek für die Arbeit mit Microsoft Project-Dateien in .NET-Anwendungen.

### F2: Kann Aspose.Tasks mit komplexen Projektstrukturen umgehen?

A2: Ja, Aspose.Tasks kann problemlos mit komplexen Projektstrukturen umgehen und bietet umfangreiche APIs zur Bearbeitung.

### F3: Ist Aspose.Tasks für .NET mit .NET Core kompatibel?

A3: Ja, Aspose.Tasks für .NET ist mit .NET Core kompatibel, sodass Sie es in plattformübergreifenden Anwendungen verwenden können.

### F4: Unterstützt Aspose.Tasks das Lesen und Schreiben von Microsoft Project-Dateien?

A4: Ja, Aspose.Tasks unterstützt das Lesen und Schreiben von Microsoft Project-Dateien in verschiedenen Formaten, einschließlich MPP, XML und MPX.

### F5: Gibt es eine Testversion für Aspose.Tasks für .NET?

 A5: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET unter erhalten[Hier](https://releases.aspose.com/).
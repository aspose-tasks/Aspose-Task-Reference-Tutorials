---
title: Berechnungsmodus in Aspose.Tasks
linktitle: Berechnungsmodus in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Berechnungsmodi in Aspose.Tasks für .NET effektiv verwalten, um die Projektplanung und Aufgabenabhängigkeiten zu optimieren.
weight: 29
url: /de/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Berechnungsmodus in Aspose.Tasks

## Einführung

Aspose.Tasks für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien in ihren .NET-Anwendungen zu arbeiten. Ein entscheidender Aspekt bei der Arbeit mit Projektdateien ist die Verwaltung der Berechnungsmodi, die bestimmen, wie Aufgaben und Projektzeitpläne berechnet und aktualisiert werden. In diesem Tutorial befassen wir uns mit den verschiedenen Berechnungsmodi, die von Aspose.Tasks für .NET unterstützt werden, und zeigen, wie man sie effektiv nutzt.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis der C#-Programmierung: Machen Sie sich mit den C#-Programmierkonzepten vertraut.

## Namespaces importieren

Bevor wir mit Aspose.Tasks für .NET arbeiten, importieren wir die erforderlichen Namespaces:

```csharp
using Aspose.Tasks;
using System;


```

## Anwenden des automatischen Berechnungsmodus

### Schritt 1: Erstellen Sie eine neue Projektinstanz

 Initialisieren Sie eine neue`Project` Objekt und legen Sie es fest`CalculationMode` Eigentum zu`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Schritt 2: Projektstartdatum festlegen und Aufgaben hinzufügen

Definieren Sie das Startdatum des Projekts und fügen Sie Aufgaben hinzu.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Schritt 3: Aufgaben verknüpfen

Stellen Sie Abhängigkeiten zwischen Aufgaben her.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Schritt 4: Überprüfen Sie die neu berechneten Daten

Überprüfen Sie, ob die Daten automatisch neu berechnet wurden.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Fügen Sie nach Bedarf weitere Überprüfungen hinzu
```

## Anwenden des manuellen Berechnungsmodus

### Schritt 1: Erstellen Sie eine neue Projektinstanz

 Initialisieren Sie eine neue`Project` Objekt und legen Sie es fest`CalculationMode` Eigentum zu`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Schritt 2: Projektstartdatum festlegen und Aufgaben hinzufügen

Definieren Sie das Startdatum des Projekts und fügen Sie Aufgaben hinzu.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Schritt 3: Überprüfen Sie die Aufgabeneigenschaften

Überprüfen Sie, ob die Aufgabeneigenschaften im manuellen Modus korrekt eingestellt sind.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Fügen Sie nach Bedarf weitere Überprüfungen hinzu
```

### Schritt 4: Aufgaben verknüpfen und Termine überprüfen

Verknüpfen Sie Aufgaben miteinander und prüfen Sie, ob ihre Termine nicht neu berechnet werden.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Anwenden des Berechnungsmodus „Keine“.

### Schritt 1: Erstellen Sie eine neue Projektinstanz

 Initialisieren Sie eine neue`Project` Objekt und legen Sie es fest`CalculationMode` Eigentum zu`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Schritt 2: Fügen Sie eine neue Aufgabe hinzu

Fügen Sie dem Projekt eine neue Aufgabe hinzu.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Schritt 3: Überprüfen Sie die Aufgabeneigenschaften

Überprüfen Sie, ob Aufgabeneigenschaften nicht automatisch berechnet werden.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Fügen Sie nach Bedarf weitere Überprüfungen hinzu
```

## Abschluss

In diesem Tutorial haben wir die in Aspose.Tasks für .NET verfügbaren Berechnungsmodi untersucht und gelernt, wie man sie in praktischen Szenarien anwendet. Unabhängig davon, ob Sie einen automatischen, manuellen oder keinen Berechnungsmodus benötigen, bietet Aspose.Tasks die Flexibilität, die den Anforderungen Ihres Projekts entspricht.

## FAQs

### F1: Kann ich den Berechnungsmodus während der Laufzeit dynamisch ändern?

A1: Ja, Sie können den Berechnungsmodus eines Projekts jederzeit während der Laufzeit ändern, indem Sie die ändern`CalculationMode` Eigentum.

### F2: Unterstützt Aspose.Tasks neben Microsoft Project auch andere Projektmanagement-Dateiformate?

A2: Aspose.Tasks konzentriert sich hauptsächlich auf Microsoft Project-Dateiformate, unterstützt aber auch andere Formate wie Primavera P6 XML, Primavera DB und Asta Powerproject XML.

### F3: Ist Aspose.Tasks sowohl für kleine als auch für Unternehmensprojekte geeignet?

A3: Auf jeden Fall! Aspose.Tasks ist mit seinen umfassenden Funktionen und robusten APIs so konzipiert, dass es den Anforderungen sowohl kleinerer als auch großer Projekte gerecht wird.

### F4: Kann ich Aspose.Tasks in andere .NET-Bibliotheken und Frameworks integrieren?

A4: Ja, Sie können Aspose.Tasks nahtlos in andere .NET-Bibliotheken und Frameworks integrieren, um die Funktionalität Ihrer Anwendungen zu verbessern.

### F5: Gibt es ein Community-Forum oder einen Support-Kanal für Aspose.Tasks-Benutzer?

 A5: Ja, Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und Diskussionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

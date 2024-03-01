---
title: Arbeiten mit Verfügbarkeitszeiträumen in Aspose.Tasks
linktitle: Arbeiten mit Verfügbarkeitszeiträumen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Ressourcenverfügbarkeitszeiten mit Aspose.Tasks für .NET effizient verwalten. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung für die Arbeit mit Verfügbarkeitszeiträumen in Ihren .NET-Projekten.
type: docs
weight: 17
url: /de/net/advanced-features/working-with-availability-periods/
---
## Einführung

In diesem Tutorial erfahren Sie, wie Sie mit Verfügbarkeitszeiträumen in Aspose.Tasks für .NET arbeiten. Verfügbarkeitszeiträume sind entscheidend für die effiziente Verwaltung von Ressourcen in Projektmanagementszenarien. Wir führen Sie Schritt für Schritt durch den Prozess.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Visual Studio: Installieren Sie Visual Studio oder eine andere bevorzugte IDE für die .NET-Entwicklung.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis der C#-Programmierung: Vertrautheit mit den Grundlagen der C#-Programmiersprache ist hilfreich.

## Namespaces importieren

Stellen Sie vor dem Eintauchen in den Code sicher, dass Sie die erforderlichen Namespaces importieren:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Lassen Sie uns den Beispielcode in mehrere Schritte unterteilen:

## Schritt 1: Erstellen Sie eine neue Projektinstanz

```csharp
var project = new Project();
```

Diese Zeile initialisiert eine neue Instanz der Project-Klasse, die ein Projekt in Aspose.Tasks darstellt.

## Schritt 2: Fügen Sie eine Ressource hinzu

```csharp
var resource = project.Resources.Add("Work Resource");
```

Hier fügen wir dem Projekt eine neue Ressource mit dem Namen „Arbeitsressource“ hinzu.

## Schritt 3: Verfügbarkeitszeiträume definieren

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Wir nennen das`GetPeriods()` Methode zum Abrufen einer Sammlung von Verfügbarkeitszeiträumen.

## Schritt 4: Fügen Sie der Ressource Verfügbarkeitszeiträume hinzu

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Wir durchlaufen die Sammlung der im vorherigen Schritt erhaltenen Verfügbarkeitszeiträume und fügen sie der Ressource hinzu.

## Schritt 5: Details zum Verfügbarkeitszeitraum anzeigen

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Schließlich durchlaufen wir die mit der Ressource verknüpften Verfügbarkeitszeiträume und drucken deren Details aus, einschließlich Startdatum, Enddatum und verfügbare Einheiten.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Verfügbarkeitszeiträumen in Aspose.Tasks für .NET arbeitet. Indem Sie der Schritt-für-Schritt-Anleitung folgen, können Sie die Ressourcenverfügbarkeit in Ihren Projektmanagementanwendungen effizient verwalten.

## FAQs

### F1: Kann ich Aspose.Tasks für .NET in kommerziellen Projekten verwenden?

 A1: Ja, Aspose.Tasks für .NET kann in kommerziellen Projekten verwendet werden. Sie können eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy).

### F2: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?

A2: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET erhalten[Hier](https://releases.aspose.com/).

### F3: Wo finde ich Dokumentation für Aspose.Tasks für .NET?

 A3: Sie finden die Dokumentation[Hier](https://reference.aspose.com/tasks/net/).

### F4: Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?

 A4: Sie können Unterstützung vom Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).

### F5: Bieten Sie temporäre Lizenzen für Aspose.Tasks für .NET an?

 A5: Ja, temporäre Lizenzen sind verfügbar[Hier](https://purchase.aspose.com/temporary-license/).
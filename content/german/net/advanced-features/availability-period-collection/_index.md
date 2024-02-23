---
title: Sammlung von Verfügbarkeitszeiträumen in Aspose.Tasks
linktitle: Sammlung von Verfügbarkeitszeiträumen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Verfügbarkeitszeiträume für Ressourcen in Aspose.Tasks für .NET verwalten. Dieses Schritt-für-Schritt-Tutorial führt Sie durch das Hinzufügen, Aktualisieren und Entfernen von Verfügbarkeitszeiträumen und gewährleistet so eine effektive Projektressourcenplanung.
type: docs
weight: 18
url: /de/net/advanced-features/availability-period-collection/
---
## Einführung

In diesem Tutorial erfahren Sie, wie Sie mit der Sammlung des Verfügbarkeitszeitraums einer Ressource in Aspose.Tasks für .NET arbeiten. Die Verwaltung von Verfügbarkeitsperioden ist für das Projektmanagement von entscheidender Bedeutung, da sie es uns ermöglicht, zu definieren, wann Ressourcen für Aufgaben innerhalb eines Projekts verfügbar sind.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundverständnis: Vertrautheit mit C# und .NET Framework.

## Namespaces importieren

Zuerst müssen wir die notwendigen Namespaces in unser Projekt importieren:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Lassen Sie uns den Beispielcode in mehrere Schritte aufteilen und jeden Teil verstehen:

## Schritt 1: Initialisieren Sie das Projekt und die Ressource

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Hier laden wir eine Projektdatei und rufen eine bestimmte Ressource anhand ihrer ID ab.

## Schritt 2: Vorhandene Verfügbarkeitszeiträume löschen

```csharp
resource.AvailabilityPeriods.Clear();
```

Wir löschen alle vorhandenen Verfügbarkeitszeiträume, die mit der Ressource verknüpft sind.

## Schritt 3: Verfügbarkeitszeiträume hinzufügen

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Wir durchlaufen eine Sammlung von Verfügbarkeitszeiträumen und fügen sie der Ressource hinzu.

## Schritt 4: Geben Sie einen neuen Verfügbarkeitszeitraum ein

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Wir erstellen einen neuen Verfügbarkeitszeitraum für das Jahr 2013 und fügen ihn in die Sammlung ein.

## Schritt 5: Verfügbarkeitszeiträume anzeigen

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Wir drucken die Anzahl und Details jedes mit der Ressource verbundenen Verfügbarkeitszeitraums aus.

## Schritt 6: Verfügbarkeitszeiträume auf eine andere Ressource kopieren

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Wir kopieren die Verfügbarkeitszeiträume von einer Ressource auf eine andere.

## Schritt 7: Verfügbarkeitszeiträume aktualisieren und entfernen

```csharp
// Aktualisieren Sie verfügbare Einheiten für einen bestimmten Zeitraum
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Entfernen Sie einen bestimmten Zeitraum
otherResource.AvailabilityPeriods.Remove(period2013);
```

Wir aktualisieren die verfügbaren Einheiten für einen Zeitraum und entfernen bestimmte Zeiträume aus der Sammlung.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Verfügbarkeitszeitraumsammlungen in Aspose.Tasks für .NET arbeitet. Die Verwaltung der Ressourcenverfügbarkeit ist für eine effektive Projektplanung und -durchführung von entscheidender Bedeutung.

## FAQs

### F1: Kann ich benutzerdefinierte Felder zu Verfügbarkeitszeiträumen hinzufügen?

A1: Nein, Verfügbarkeitszeiträume in Aspose.Tasks für .NET unterstützen keine benutzerdefinierten Felder.

### F2: Sind Verfügbarkeitszeiträume mit bestimmten Aufgaben verknüpft?

A2: Nein, Verfügbarkeitszeiträume sind mit Ressourcen verknüpft und definieren, wann sie allgemein für Aufgaben verfügbar sind.

### F3: Kann ich Verfügbarkeitszeiträume aus externen Quellen importieren?

A3: Ja, Sie können Verfügbarkeitszeiträume aus verschiedenen Datenquellen mit Aspose.Tasks für .NET-APIs importieren.

### F4: Wie gehe ich mit sich überschneidenden Verfügbarkeitszeiträumen um?

A4: Aspose.Tasks für .NET bietet keine integrierten Mechanismen zum Umgang mit überlappenden Zeiträumen. Möglicherweise müssen Sie benutzerdefinierte Logik implementieren, um solche Szenarien zu verwalten.

### F5: Gibt es eine Grenze für die Anzahl der Verfügbarkeitszeiträume, die eine Ressource haben kann?

A5: Es gibt keine vordefinierte Grenze für die Anzahl der Verfügbarkeitszeiträume, die eine Ressource haben kann, aber bei einer großen Anzahl von Zeiträumen kann sich die Leistung verschlechtern.
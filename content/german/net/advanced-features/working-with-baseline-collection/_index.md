---
title: Arbeiten mit der Baseline-Sammlung in Aspose.Tasks
linktitle: Arbeiten mit der Baseline-Sammlung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Baselines in Aspose.Tasks für .NET effizient verwalten. Folgen Sie unserem umfassenden Tutorial für eine Schritt-für-Schritt-Anleitung.
type: docs
weight: 20
url: /de/net/advanced-features/working-with-baseline-collection/
---
## Einführung

Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, nahtlos mit Microsoft Project-Dateien in ihren .NET-Anwendungen zu arbeiten. Zu seinen zahlreichen Funktionen gehört die robuste Unterstützung für die Verwaltung von Baselines innerhalb von Projekten. Baselines sind für das Projektmanagement unerlässlich, da Sie damit den ursprünglichen Projektplan mit dem aktuellen Status vergleichen und so den Projektfortschritt besser verfolgen und analysieren können.

## Voraussetzungen

Bevor wir uns mit der Arbeit mit Basissammlungen in Aspose.Tasks befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio: Installieren Sie die Visual Studio-IDE auf Ihrem System.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Download-Link](https://releases.aspose.com/tasks/net/).
3. Grundverständnis von C#: Machen Sie sich mit der Programmiersprache C# vertraut.
4. Microsoft Project-Datei: Halten Sie zu Testzwecken eine Microsoft Project-Datei (.mpp) bereit.

## Namespaces importieren

Um mit Baseline-Sammlungen in Aspose.Tasks arbeiten zu können, müssen Sie die folgenden Namespaces importieren:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Lassen Sie uns nun jedes Beispiel in mehrere Schritte unterteilen:

## Schritt 1: Projektdatei laden

Laden Sie zunächst die Microsoft Project-Datei mit Aspose.Tasks:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Schritt 2: Ressource abrufen

Rufen Sie als Nächstes die gewünschte Ressource aus dem Projekt ab:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Schritt 3: Basisinformationen anzeigen

Zeigen Sie nun Informationen zu den mit der Ressource verknüpften Baselines an:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Schritt 4: Durch Baselines iterieren

Durchlaufen Sie jede mit der Ressource verknüpfte Baseline und drucken Sie relevante Informationen aus:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Schritt 5: Basislinien entfernen

Löschen Sie alle mit der Ressource verknüpften Baselines:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit Basissammlungen in Aspose.Tasks für .NET arbeitet. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Baselines in Ihren .NET-Anwendungen einfach verwalten und so eine effektive Projektverfolgung und -analyse ermöglichen.

## FAQs

### F1: Kann Aspose.Tasks große Projektdateien verarbeiten?

A1: Ja, Aspose.Tasks ist für die effiziente Verarbeitung großer Projektdateien optimiert und sorgt so für eine reibungslose Leistung.

### F2: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?

A2: Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.

### F3: Kann ich Baselines in Aspose.Tasks anpassen?

A3: Ja, Sie können Baselines mit Aspose.Tasks für .NET entsprechend Ihren Projektanforderungen anpassen.

### F4: Bietet Aspose.Tasks Unterstützung für Cloud-Plattformen?

A4: Ja, Aspose.Tasks bietet Unterstützung für die Integration mit gängigen Cloud-Plattformen und bietet so Flexibilität bei der Bereitstellung.

### F5: Gibt es ein Community-Forum für Aspose.Tasks-Benutzer, in dem sie Hilfe suchen und Wissen austauschen können?

 A5: Ja, Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um mit der Community in Kontakt zu treten und Unterstützung von Experten zu erhalten.
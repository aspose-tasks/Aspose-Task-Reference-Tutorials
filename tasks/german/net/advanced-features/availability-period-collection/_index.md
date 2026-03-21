---
date: 2026-03-21
description: Erfahren Sie, wie Sie Verfügbarkeitszeiträume für Ressourcen verwalten
  und eine effektive Projektressourcenverfügbarkeit mit Aspose.Tasks für .NET erreichen.
  Dieser Schritt‑für‑Schritt‑Leitfaden zeigt, wie man Verfügbarkeitszeiträume hinzufügt,
  aktualisiert und entfernt.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projektressourcenverfügbarkeit – Verwaltung von Verfügbarkeitsperioden in Aspose.Tasks
url: /de/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektressourcenverfügbarkeit: Sammlung von Verfügbarkeitszeiträumen in Aspose.Tasks

Die Verwaltung **von Projektressourcenverfügbarkeit** ist ein zentraler Bestandteil erfolgreicher Projektplanung. In diesem Tutorial lernen Sie **wie man Verfügbarkeit** für Ressourcen mit der Aspose.Tasks für .NET API Schritt für Schritt verwaltet, vom Laden eines Projekts bis zum Kopieren von Zeiträumen zwischen Ressourcen.

## Schnelle Antworten
- **Was ist die Hauptklasse für Verfügbarkeitszeiträume?** `AvailabilityPeriod` im `Aspose.Tasks` Namespace.  
- **Kann ich vorhandene Zeiträume löschen?** Ja, rufen Sie `resource.AvailabilityPeriods.Clear()` auf.  
- **Wie füge ich einen neuen Zeitraum hinzu?** Erstellen Sie ein `AvailabilityPeriod` Objekt und verwenden Sie `Add` oder `Insert`.  
- **Ist es möglich, Zeiträume zu einer anderen Ressource zu kopieren?** Absolut – verwenden Sie `CopyTo` und fügen Sie dann jedes Element zur Zielressource hinzu.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Ja, eine kommerzielle Aspose.Tasks Lizenz ist für Nicht‑Trial Deployments erforderlich.

## Was ist Projektressourcenverfügbarkeit?
Projektressourcenverfügbarkeit definiert die Daten und Einheiten (Prozentsatz der Kapazität), zu denen eine Ressource Aufgaben zugewiesen werden kann. Durch die Steuerung dieser Zeiträume verhindern Sie Überbelegungen und verbessern die Genauigkeit des Zeitplans.

## Warum Aspose.Tasks zur Verwaltung von Verfügbarkeitszeiträumen verwenden?
- **Vollständige .NET-Integration** – kein COM-Interop, reiner verwalteter Code.  
- **Feinkörnige Steuerung** – genaue Start-/Enddaten und Bruchteileinheiten festlegen.  
- **Einfaches Kopieren** – Verfügbarkeitsdaten zwischen Ressourcen verschieben, ohne manuelles Parsen.  
- **Leistungsoptimiert** – arbeitet effizient mit großen MPP-Dateien.

## Voraussetzungen
1. **Visual Studio** – jede aktuelle Version (2019, 2022 oder neuer).  
2. **Aspose.Tasks for .NET** – Download von [hier](https://releases.aspose.com/tasks/net/).  
3. **Grundlegende C#‑Kenntnisse** – Sie sollten mit Klassen, Sammlungen und LINQ vertraut sein.

## Namespaces importieren

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Wir importieren das Kern‑Namespace `Aspose.Tasks` zusammen mit den Standard‑.NET‑Sammlungen, die wir später benötigen.

## Schritt 1: Projekt und Ressource initialisieren

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Hier laden wir eine vorhandene MPP‑Datei und holen die Ressource, deren Verfügbarkeit wir bearbeiten möchten (ID = 1).

## Schritt 2: Vorhandene Verfügbarkeitszeiträume löschen

```csharp
resource.AvailabilityPeriods.Clear();
```

Das Löschen entfernt alle zuvor definierten Zeiträume und gibt uns ein sauberes Blatt.

## Schritt 3: Verfügbarkeitszeiträume hinzufügen

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

Wir rufen eine Sammlung von `AvailabilityPeriod` Objekten ab (die Hilfsfunktion `GetPeriods` wird angenommen, dass sie anderswo definiert ist) und fügen jedes hinzu, wobei wir prüfen, dass die Sammlung beschreibbar ist.

## Schritt 4: Einen neuen Verfügbarkeitszeitraum einfügen

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Dies erstellt einen benutzerdefinierten Zeitraum für das Jahr 2013 und fügt ihn an Position 1 (zweiter Slot) ein, falls er noch nicht vorhanden ist.

## Schritt 5: Verfügbarkeitszeiträume anzeigen

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

Ein kurzer Konsolenauszug zeigt die Gesamtzahl und die Details jedes Zeitraums – praktisch zum Debuggen oder zur Verifizierung.

## Schritt 6: Verfügbarkeitszeiträume zu einer anderen Ressource kopieren

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

Wir kopieren die gesamte Sammlung in ein Array, löschen die Zeiträume der Zielressource und füllen sie anschließend wieder. Das demonstriert, wie Verfügbarkeitsdaten zwischen Ressourcen dupliziert werden können.

## Schritt 7: Verfügbarkeitszeiträume aktualisieren und entfernen

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Hier passen wir die `AvailableUnits` für den vorletzten Zeitraum an und entfernen anschließend den 2013‑Zeitraum, den wir zuvor hinzugefügt haben.

## Häufige Probleme und Lösungen
- **Fehler bei schreibgeschützter Sammlung** – Stellen Sie sicher, dass das Projekt nicht im schreibgeschützten Modus geöffnet ist oder dass Sie `resource.AvailabilityPeriods.Clear()` aufgerufen haben, bevor Sie neue Elemente hinzufügen.  
- **Überlappende Zeiträume** – Aspose.Tasks führt keine automatische Zusammenführung von Überlappungen durch; Sie müssen ggf. eigene Logik schreiben, um diese zu erkennen und zu beheben.  
- **Ungültiges Datumsformat** – Verwenden Sie stets `DateTime` Objekte; das Parsen von Zeichenketten kann zu lokalspezifischen Fehlern führen.

## Häufig gestellte Fragen

**Q: Kann ich benutzerdefinierte Felder zu Verfügbarkeitszeiträumen hinzufügen?**  
A: Nein, Verfügbarkeitszeiträume in Aspose.Tasks für .NET unterstützen keine benutzerdefinierten Felder.

**Q: Sind Verfügbarkeitszeiträume mit bestimmten Aufgaben verknüpft?**  
A: Nein, sie sind mit Ressourcen verknüpft und definieren, wann die Ressource allgemein für Aufgaben verfügbar ist.

**Q: Kann ich Verfügbarkeitszeiträume aus externen Quellen importieren?**  
A: Ja, Sie können Zeiträume aus CSV, XML oder einer Datenbank importieren, indem Sie `AvailabilityPeriod` Objekte erstellen und zur Sammlung hinzufügen.

**Q: Wie gehe ich mit überlappenden Verfügbarkeitszeiträumen um?**  
A: Überlappungen werden nicht automatisch aufgelöst; Sie müssen eine benutzerdefinierte Validierung implementieren, um Konflikte zusammenzuführen oder abzulehnen.

**Q: Gibt es ein Limit für die Anzahl der Verfügbarkeitszeiträume, die eine Ressource haben kann?**  
A: Es gibt kein fest codiertes Limit, aber sehr große Sammlungen können die Leistung beeinträchtigen; konsolidieren Sie nach Möglichkeit die Zeiträume.

## Fazit

In diesem Leitfaden haben wir alles behandelt, was Sie wissen müssen, um **Projektressourcenverfügbarkeit** mit Aspose.Tasks für .NET zu verwalten – vom Initialisieren eines Projekts und Löschen alter Daten bis zum Hinzufügen, Einfügen, Kopieren, Aktualisieren und Entfernen von Verfügbarkeitszeiträumen. Das Beherrschen dieser Schritte hilft Ihnen, Ressourcenkalender genau zu halten und Ihre Projektzeitpläne realistisch zu gestalten.

---

**Zuletzt aktualisiert:** 2026-03-21  
**Getestet mit:** Aspose.Tasks for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
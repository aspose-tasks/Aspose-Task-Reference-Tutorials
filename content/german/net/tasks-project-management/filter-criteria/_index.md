---
title: Beherrschen Sie die Filterkriterien von MS Project mit Aspose.Tasks
linktitle: Filterkriterien in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Filterkriterien in MS Project mithilfe von Aspose.Tasks für .NET implementieren. Steigern Sie die Effizienz des Projektmanagements durch gezielte Datenanalyse.
type: docs
weight: 18
url: /de/net/tasks-project-management/filter-criteria/
---
## Einführung
Im Bereich des Projektmanagements gilt Microsoft Project als bewährtes Tool und bietet eine Fülle von Funktionen zur Unterstützung von Projektplanern und -managern. Zu den zahlreichen Funktionen gehört die Möglichkeit, Projektdaten zu filtern, sodass sich Benutzer auf bestimmte Aspekte ihrer Projektaufgaben konzentrieren können. Allerdings kann die Beherrschung dieser Filterfunktionen ohne die richtige Anleitung eine entmutigende Aufgabe sein. Ziel dieses Tutorials ist es, den Prozess zu entmystifizieren, indem es eine Schritt-für-Schritt-Anleitung zur Implementierung von Kriterienfiltern in MS Project mit Aspose.Tasks für .NET bereitstellt.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Grundlegendes Verständnis von C#: Um die in diesem Tutorial behandelten Konzepte zu verstehen, sind Kenntnisse der Programmiersprache C# erforderlich.
2.  Installation von Aspose.Tasks für .NET: Stellen Sie sicher, dass Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
3. Microsoft Project-Datei: Halten Sie eine Microsoft Project-Datei (z. B. Project2003.mpp) bereit, die Sie zur Umsetzung der Filterkriterien verwenden.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.Tasks für .NET arbeiten zu können. Folge diesen Schritten:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Schritt 1: Projektdatei laden
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Erläuterung: Diese Codezeile initialisiert eine neue Instanz von`Project` Klasse und lädt die durch ihren Pfad angegebene Microsoft Project-Datei.
## Schritt 2: Aufgabenfilter abrufen
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Erläuterung: Hier rufen wir einen Aufgabenfilter aus dem Projekt ab. Passen Sie den Index an (`[1]`) entsprechend Ihrer Anforderung, um den gewünschten Filter auszuwählen.
## Schritt 3: Kriterienzeilen anzeigen
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Erläuterung: Dieser Abschnitt durchläuft jede Kriterienzeile des Filters und zeigt deren Feld, Operation, Test und Werte (falls vorhanden) an.
## Schritt 4: Filterkriterien drucken
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Erläuterung: Druckt die Operation der Filterkriterien.
## Schritt 5: Kriteriendetails anzeigen
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Erläuterung: Dieser Teil ruft detaillierte Informationen zu jeder Kriterienzeile ab und zeigt sie an und bietet Einblicke in die Konfiguration des Filters.

## Abschluss
Das Beherrschen von Filterkriterien in MS Project mit Aspose.Tasks für .NET ist eine wertvolle Fähigkeit, die die Effizienz des Projektmanagements erheblich steigern kann. Durch die Befolgung dieses Tutorials haben Sie gelernt, wie Sie Filterkriterien programmgesteuert bearbeiten und so Projektansichten an Ihre spezifischen Anforderungen anpassen können.
## FAQs
### F: Kann ich in MS Project mehrere Filter gleichzeitig anwenden?
A: Ja, Sie können mehrere Filter kombinieren, um Ihre Projektdaten weiter zu verfeinern.
### F: Unterstützt Aspose.Tasks ältere Versionen von Microsoft Project-Dateien?
A: Ja, Aspose.Tasks bietet Abwärtskompatibilität, sodass Sie mit verschiedenen Versionen von Microsoft Project-Dateien arbeiten können.
### F: Ist Aspose.Tasks mit anderen .NET-Frameworks kompatibel?
A: Aspose.Tasks unterstützt .NET Framework, .NET Core und .NET Standard und gewährleistet so Flexibilität in verschiedenen Entwicklungsumgebungen.
### F: Kann ich Filterkriterien basierend auf dynamischen Bedingungen anpassen?
A: Auf jeden Fall können Sie Filterkriterien basierend auf dynamischen Parametern programmgesteuert anpassen und so eine adaptive Projektdatenanalyse ermöglichen.
### F: Wo kann ich Hilfe suchen, wenn ich Probleme mit Aspose.Tasks habe?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um Unterstützung von der Community zu erhalten oder sich direkt an den Aspose.Tasks-Support zu wenden, um individuelle Unterstützung zu erhalten.
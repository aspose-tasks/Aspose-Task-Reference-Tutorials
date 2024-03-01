---
title: Beherrschen der zeitphasengesteuerten Datenerfassung in Aspose.Tasks
linktitle: Sammlung zeitphasenbezogener Daten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die zeitphasengesteuerte Datenerfassung in Aspose.Tasks für .NET. Schritt-für-Schritt-Anleitung, FAQs und mehr. Erweitern Sie noch heute Ihre Projektmanagementfähigkeiten!
type: docs
weight: 15
url: /de/net/text-view-configuration/timephased-data-collection/
---
## Einführung
Möchten Sie die Leistungsfähigkeit von Zeitphasendaten in Ihren .NET-Anwendungen mithilfe von Aspose.Tasks nutzen? Suchen Sie nicht weiter! Dieser umfassende Leitfaden führt Sie durch den Prozess der Erfassung von Zeitphasendaten mit Aspose.Tasks für .NET und stellt sicher, dass Sie diese leistungsstarke Bibliothek optimal nutzen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Tasks für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Aspose.Tasks .NET-Dokumentation](https://reference.aspose.com/tasks/net/).
2. .NET-Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine funktionierende .NET-Entwicklungsumgebung eingerichtet haben.
3. Ihr Dokumentenverzeichnis: Ersetzen Sie den Platzhalter „Ihr Dokumentenverzeichnis“ in den Codefragmenten durch den Pfad zu Ihrem Dokumentenverzeichnis.
## Namespaces importieren
Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces, um die Funktionen von Aspose.Tasks zu nutzen:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Erstellen Sie ein Projekt und Ressourcen
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Fügen Sie dem Projekt Aufgaben hinzu
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Aufgabeneigenschaften festlegen...
var task2 = project.RootTask.Children.Add("Task 2");
// Task2-Eigenschaften festlegen...
```
## 3. Weisen Sie Aufgaben Ressourcen zu
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Aufgabeneigenschaften festlegen...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//Eigenschaften für Zuweisung2 festlegen...
```
## 4. Arbeiten Sie mit Zeitphasendaten
```csharp
// Konturierte Arbeitskontur festlegen
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Überprüfen Sie, ob die zeitphasengesteuerte Datenerfassung schreibgeschützt ist
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Löschen Sie generierte Zeitphasendaten
assignment.TimephasedData.Clear();
// Erstellen und fügen Sie Zeitphasendaten hinzu
var td = new TimephasedData
{
    // Zeitphasendateneigenschaften festlegen...
};
assignment.TimephasedData.Add(td);
// Fügen Sie eine Liste mit Zeitphasendaten hinzu
var list = new List<TimephasedData>();
// Fügen Sie der Liste weitere Zeitphasendatenelemente hinzu...
assignment.TimephasedData.AddRange(list);
// Filtern Sie Zeitphasendaten nach Typ und Datumsbereich
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Gefilterte Zeitphasendaten drucken...
```
## 5. Manipulieren Sie Zeitphasendaten
```csharp
// Fügen Sie ein falsches Zeitphasendatenelement hinzu und löschen Sie es dann
var td4 = new TimephasedData
{
    // Stellen Sie falsche Zeitphasendateneigenschaften ein...
};
assignment.TimephasedData.Add(td4);
// Löschen Sie das falsche Zeitphasendatenelement
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Durchlaufen Sie alle Zeitphasenelemente
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Zeitphasenbezogene Artikeldetails drucken...
}
```
## 6. Kopieren Sie Zeitphasendaten in eine andere Zuweisung
```csharp
// Zeitphasendaten in eine andere Zuweisung kopieren
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Konvertieren Sie die Sammlung in eine einfache Liste
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Entfernen Sie zeitphasenbezogene Datenelemente nacheinander
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Abschluss
Abschließend bietet dieses Tutorial eine detaillierte Anleitung zum Sammeln von Zeitphasendaten mit Aspose.Tasks für .NET. Wenn Sie diese Schritte befolgen, können Sie diese Funktionalität nahtlos in Ihre Projekte integrieren und so eine effektive Zeiterfassung und Ressourcenverwaltung ermöglichen.
## Häufig gestellte Fragen
### Kann ich Aspose.Tasks für .NET mit anderen Projektmanagement-Tools verwenden?
Ja, Aspose.Tasks für .NET ist für die Zusammenarbeit mit gängigen Projektmanagement-Tools konzipiert und unterstützt verschiedene Dateiformate.
### Gibt es eine Grenze für die Anzahl der Ressourcen und Aufgaben, die ich mit Aspose.Tasks verwalten kann?
Aspose.Tasks verwaltet Projekte unterschiedlicher Größe und es gibt keine strenge Begrenzung für die Anzahl der Ressourcen und Aufgaben.
### Wie kann ich Unterstützung bei Problemen oder Fragen im Zusammenhang mit Aspose.Tasks für .NET erhalten?
 Für Unterstützung besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) um mit der Community in Kontakt zu treten und Hilfe zu erhalten.
### Kann ich Aspose.Tasks für .NET testen, bevor ich es kaufe?
 Ja, Sie können die Funktionen von Aspose.Tasks für .NET erkunden, indem Sie auf zugreifen[Kostenlose Testphase](https://releases.aspose.com/).
### Wo kann ich eine Lizenz für Aspose.Tasks für .NET erwerben?
Sie können eine Lizenz für Aspose.Tasks für .NET erwerben[Hier](https://purchase.aspose.com/buy).
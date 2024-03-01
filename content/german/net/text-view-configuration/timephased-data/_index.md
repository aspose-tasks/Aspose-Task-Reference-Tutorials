---
title: Beherrschen Sie die zeitphasengesteuerte Datenverarbeitung mit Aspose.Tasks für .NET
linktitle: Umgang mit Zeitphasendaten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie Aspose.Tasks für .NET, um Zeitphasendaten mühelos zu verarbeiten, die Projektplanung zu verbessern und das Ressourcenmanagement zu optimieren. #Aufgaben #Aufgaben #MS-Projekt
type: docs
weight: 14
url: /de/net/text-view-configuration/timephased-data/
---
## Einführung
In der Welt des Projektmanagements ist der effektive Umgang mit Zeitphasendaten von entscheidender Bedeutung für die Ressourcenzuweisung, Kostenschätzung und die gesamte Projektplanung. Aspose.Tasks für .NET bietet eine leistungsstarke Lösung für die nahtlose Arbeit mit benutzerdefinierten Zeitphasendaten. Dieses Tutorial führt Sie durch den Prozess der Verarbeitung von Zeitphasendaten mit Aspose.Tasks und ermöglicht Ihnen so die Optimierung des Ressourcenmanagements in Ihren Projekten.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Ein grundlegendes Verständnis von Projektmanagementkonzepten.
-  Installierte Aspose.Tasks für .NET. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
- Ein Code-Editor wie Visual Studio zur Implementierung der bereitgestellten Beispiele.
## Namespaces importieren
Stellen Sie in Ihrem .NET-Projekt sicher, dass Sie die erforderlichen Namespaces importieren, um die Aspose.Tasks-Funktionen nutzen zu können. Fügen Sie am Anfang Ihrer Codedatei die folgenden Zeilen hinzu:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um Sie durch den Umgang mit Zeitphasendaten mit Aspose.Tasks zu führen:
## Schritt 1: Richten Sie das Projekt ein
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Hier initialisieren wir ein neues Projekt und legen seinen Berechnungsmodus fest.
## Schritt 2: Ressourcen und Aufgaben definieren
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Erstellen Sie Arbeits- und Kostenressourcen sowie eine Aufgabe, um eine Projektstruktur zu simulieren.
## Schritt 3: Ressourcen der Aufgabe zuweisen
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Weisen Sie der Aufgabe Arbeits- und Kostenressourcen zu.
## Schritt 4: Benutzerdefinierte Zeitphasendaten hinzufügen
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Ähnliche Schritte für costAssignment
costAssignment.TimephasedData.Clear();
```
Fügen Sie benutzerdefinierte Zeitphasendaten für Arbeits- und Kostenzuweisungen hinzu.
## Schritt 5: Zeitphasendaten anzeigen
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Zeigen Sie relevante Informationen zu jedem Zeitphasen-Dateneintrag an
    }
}
```
Zeigen Sie abschließend die Zeitphasendaten für jede Aufgabe an.
#
## Abschluss
Der effektive Umgang mit Zeitphasendaten in Aspose.Tasks eröffnet neue Möglichkeiten für die detaillierte Projektplanung und das Ressourcenmanagement. Durch Befolgen dieser Schritt-für-Schritt-Anleitung haben Sie gelernt, wie Sie Zeitphasendaten bearbeiten, um den spezifischen Anforderungen Ihrer Projekte gerecht zu werden.
## Häufig gestellte Fragen
### Kann ich Aspose.Tasks für .NET mit anderen Projektmanagement-Tools verwenden?
Aspose.Tasks ist in erster Linie für die .NET-Entwicklung konzipiert. Seine Funktionalitäten können jedoch verschiedene Projektmanagement-Tools ergänzen.
### Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?
 Ja, Sie können eine kostenlose Testversion ausprobieren[Hier](https://releases.aspose.com/).
### Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?
 Besuche den[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für die Unterstützung der Gemeinschaft.
### Was ist eine temporäre Lizenz und wie kann ich eine erhalten?
 Erfahren Sie mehr über temporäre Lizenzen[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich die Dokumentation für Aspose.Tasks für .NET?
 Weitere Informationen finden Sie in der umfassenden[Dokumentation](https://reference.aspose.com/tasks/net/) für detaillierte Informationen.
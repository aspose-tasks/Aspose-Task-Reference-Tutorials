---
title: Master-MS-Projektraten mit Aspose.Tasks
linktitle: Sammlung von Tarifen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Tarife in MS Project-Dateien mit Aspose.Tasks für .NET verwalten. Schritt-für-Schritt-Anleitung für effektives Ressourcenmanagement.
type: docs
weight: 11
url: /de/net/rate-recurring-tasks/rate-collection/
---
## Einführung
Willkommen zu unserem Tutorial zum Verwalten von Tarifen in MS Project mit Aspose.Tasks für .NET! In diesem Leitfaden führen wir Sie durch den Prozess der Arbeit mit Tarifen in Ihren MS Project-Dateien mithilfe von Aspose.Tasks. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst mit der .NET-Entwicklung beginnen, erhalten Sie in diesem Tutorial Schritt-für-Schritt-Anleitungen für den effektiven Umgang mit Raten in Ihren Projekten.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Visual Studio installiert
Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. Sie können es von der Website herunterladen, falls Sie es noch nicht getan haben.
### 2. Aspose.Tasks für .NET
 Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.aspose.com/tasks/net/).
### 3. Grundkenntnisse in C# und .NET
Machen Sie sich mit der Programmiersprache C# und den Grundlagen des .NET Frameworks vertraut, um die in diesem Tutorial bereitgestellten Codebeispiele besser zu verstehen.
## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um die Aspose.Tasks-Funktionen zu nutzen:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Lassen Sie uns nun jedes Beispiel in mehrere Schritte unterteilen:
## Schritt 1: Laden Sie eine MS Project-Datei
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Hier erstellen wir ein neues`Project` Objekt durch Laden einer vorhandenen MS Project-Datei.
## Schritt 2: Fügen Sie eine Ressource hinzu und legen Sie Arbeit und Tarife fest
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Wir fügen dem Projekt eine neue Ressource hinzu und legen als Typ Arbeit, Arbeitsmenge und Standardsatz fest.
## Schritt 3: Tarife zur Ressource hinzufügen
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Wir fügen der Ressource Tarife hinzu und geben dabei das Start- und Enddatum, den Standardtarif und das Tarifformat an.
## Schritt 4: Preisinformationen drucken
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
In diesem Schritt werden Informationen zu den mit der Ressource verknüpften Tarifen gedruckt.
## Schritt 5: Aktualisieren Sie einen Preis
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Wir aktualisieren das Enddatum eines bestimmten Tarifs.
## Schritt 6: Tarife entfernen
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Dieser Schritt entfernt alle Tarife eines bestimmten Typs.
## Schritt 7: Iterieren Sie die verbleibenden Raten
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Schließlich iterieren wir über die verbleibenden Raten nach dem Entfernen.
## Abschluss
Zusammenfassend stellt Ihnen dieses Tutorial eine umfassende Anleitung zur Verwaltung von Raten in MS Project-Dateien mit Aspose.Tasks für .NET zur Verfügung. Indem Sie die Schritt-für-Schritt-Anleitungen in diesem Tutorial befolgen, können Sie die Tarife in Ihren Projekten effizient verwalten und so ein genaues Ressourcenmanagement gewährleisten.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit anderer Projektmanagementsoftware verwenden?
A: Ja, Aspose.Tasks für .NET unterstützt die Integration mit verschiedenen Projektmanagementsoftware, einschließlich MS Project, Primavera und mehr.
### F: Ist Aspose.Tasks für .NET mit verschiedenen Versionen von MS Project-Dateien kompatibel?
A: Absolut, Aspose.Tasks für .NET unterstützt die Arbeit mit MS Project-Dateien verschiedener Versionen und gewährleistet so Flexibilität und Kompatibilität.
### F: Bietet Aspose.Tasks für .NET Dokumentation und Support?
 A: Ja, auf Aspose.Tasks finden Sie eine umfassende Dokumentation und Zugriff auf Support-Foren[Webseite](https://reference.aspose.com/tasks/net/).
### F: Kann ich Aspose.Tasks für .NET vor dem Kauf testen?
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für .NET nutzen, um dessen Funktionen und Kompatibilität mit Ihren Anforderungen zu testen.
### F: Wie kann ich eine Lizenz für Aspose.Tasks für .NET erwerben?
 A: Sie können eine Lizenz für Aspose.Tasks für .NET erwerben[Webseite](https://purchase.aspose.com/temporary-license/)das flexible Lizenzierungsoptionen bietet, die Ihren Anforderungen entsprechen.
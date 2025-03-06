---
title: Umgang mit MS Project-Raten mit Aspose.Tasks für .NET
linktitle: Umgang mit Tarifen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Meistern Sie die einfache Verwaltung von MS Project-Raten mit Aspose.Tasks für .NET. Automatisieren Sie Aufgaben effizient für reibungslosere Projektabläufe.
weight: 10
url: /de/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Umgang mit MS Project-Raten mit Aspose.Tasks für .NET

## Einführung
Willkommen zu unserem Tutorial zum Umgang mit MS Project Rates mit Aspose.Tasks für .NET! In diesem Leitfaden führen wir Sie Schritt für Schritt durch den Prozess und stellen sicher, dass Sie Tarife in Ihren MS Project-Dokumenten effizient verwalten können. Aspose.Tasks für .NET bietet leistungsstarke Funktionen zur programmgesteuerten Bearbeitung von MS Project-Dateien, sodass Sie Ihre Projektmanagementaufgaben mühelos optimieren können.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Visual Studio installiert: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist.
2.  Aspose.Tasks for .NET-Bibliothek: Laden Sie die Aspose.Tasks for .NET-Bibliothek herunter und installieren Sie sie. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/tasks/net/).
3. Grundlegendes Verständnis von C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die für die Verarbeitung von MS Project Rates erforderlich sind.
## Schritt 1: Importieren Sie den Aspose.Tasks-Namespace
```csharp
using Aspose.Tasks;
using System;

```
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen und jeden Schritt gründlich verstehen.
## Schritt 1: Projektdatei laden
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 In diesem Schritt laden wir eine vorhandene MS Project-Datei mit dem Namen „Project1.mpp“ mithilfe von`Project` Klasse, bereitgestellt von Aspose.Tasks.
## Schritt 2: Ressource hinzufügen und Arbeit festlegen
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Hier fügen wir dem Projekt eine neue Ressource mit dem Namen „Ressource 1“ hinzu und legen ihren Typ auf „Arbeit“ fest. Wir definieren auch die Arbeitsdauer für diese Ressource.
## Schritt 3: Standardtarif festlegen
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
In diesem Schritt legen wir den Standardpreis für die Ressource auf 20 $ pro Stunde fest.
## Schritt 4: Tarifzeiträume definieren
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Hier definieren wir die Tarifzeiträume für die Ressource. Tarif 1 wird vom 1. Januar 2019 bis zum 11. November 2019 festgelegt, wobei Standard- und Überstundentarife festgelegt sind.
## Schritt 5: Fügen Sie einen weiteren Tarifzeitraum hinzu
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
In diesem letzten Schritt fügen wir einen weiteren Tarifzeitraum vom 12. November 2019 bis zum 31. Dezember 2019 hinzu, wobei ein anderer Standardtarif und andere Kosten pro Nutzung definiert sind.
Glückwunsch! Sie haben MS Project Rates mit Aspose.Tasks für .NET erfolgreich bearbeitet.
## Abschluss
Die programmgesteuerte Verwaltung von MS Project Rates kann Ihren Projektmanagement-Workflow erheblich verbessern. Mit Aspose.Tasks für .NET haben Sie die Möglichkeit, Tarifverwaltungsaufgaben effizient zu automatisieren und so Zeit und Ressourcen zu sparen.
## FAQs
### F: Kann Aspose.Tasks komplexe Projektstrukturen verarbeiten?
A: Ja, Aspose.Tasks bietet robuste Funktionen zur einfachen Handhabung komplexer Projektstrukturen.
### F: Ist Aspose.Tasks mit allen Versionen von MS Project-Dateien kompatibel?
A: Aspose.Tasks unterstützt verschiedene Versionen von MS Project-Dateien und gewährleistet so die Kompatibilität zwischen verschiedenen Plattformen.
### F: Kann ich vorhandene Tarife in einer MS Project-Datei mit Aspose.Tasks ändern?
A: Auf jeden Fall! Mit Aspose.Tasks können Sie bestehende Tarife ändern, neue Tarife hinzufügen und diese dynamisch verwalten.
### F: Bietet Aspose.Tasks Unterstützung für benutzerdefinierte Tarifberechnungen?
A: Ja, Sie können mit Aspose.Tasks benutzerdefinierte Tarifberechnungen implementieren, um bestimmte Projektanforderungen zu erfüllen.
### F: Gibt es ein Community-Forum oder Support für Aspose.Tasks-Benutzer?
 A: Ja, Sie können das besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15)um Hilfe zu suchen und mit anderen Benutzern zu interagieren.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

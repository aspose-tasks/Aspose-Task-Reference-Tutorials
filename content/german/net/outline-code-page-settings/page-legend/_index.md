---
title: Konfigurieren Sie MS Project-Legenden in Aspose.Tasks
linktitle: Konfigurieren Sie die Seitenlegende in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Seitenlegenden in .NET mithilfe von Aspose.Tasks für eine effiziente Projektverwaltung konfigurieren. Schritt-für-Schritt-Anleitung bereitgestellt.
type: docs
weight: 18
url: /de/net/outline-code-page-settings/page-legend/
---
## Einführung
Im Bereich der .NET-Entwicklung ist die effiziente Verwaltung von Aufgaben von entscheidender Bedeutung, insbesondere im Projektmanagement. Aspose.Tasks für .NET erweist sich als leistungsstarkes Tool, das eine Fülle von Funktionen zur Optimierung von Aufgabenverwaltungsprozessen bietet. Eine dieser Funktionen ist die Möglichkeit, MS Project-Seitenlegenden zu konfigurieren, wodurch Benutzer wertvolle Einblicke in die Präsentation von Projektdaten erhalten.
## Voraussetzungen
Bevor Sie sich mit der Konfiguration von MS Project-Seitenlegenden mithilfe von Aspose.Tasks für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Installation: Installieren Sie Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
2. Grundkenntnisse von .NET: Machen Sie sich mit den Grundlagen der .NET-Entwicklung vertraut, einschließlich der Einrichtung von Projekten und der Arbeit mit Namespaces.
3. Entwicklungsumgebung: Verwenden Sie eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio für ein nahtloses Codierungserlebnis.
4. Projektdatei: Halten Sie eine Microsoft Project-Datei (MPP) zum Experimentieren bereit.

## Namespaces importieren
Importieren Sie in Ihr .NET-Projekt die erforderlichen Namespaces, um auf die von Aspose.Tasks für .NET bereitgestellten Funktionen zuzugreifen.
1. Öffnen Sie Ihr Projekt: Starten Sie Ihr .NET-Projekt in Ihrer bevorzugten IDE.
2. Namespaces importieren: Importieren Sie am Anfang Ihrer Codedatei die erforderlichen Namespaces:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Lassen Sie uns das bereitgestellte Beispiel in eine Schritt-für-Schritt-Anleitung aufteilen, um die Konfiguration von MS Project-Seitenlegenden mit Aspose.Tasks für .NET umfassend zu verstehen.

## Schritt 1: Dokumentverzeichnis angeben
Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest, in dem sich Ihre Microsoft Project-Datei befindet.

```csharp
String DataDir = "Your Document Directory";
```
## Schritt 2: Projekt laden
 Initialisieren Sie eine neue Instanz von`Project` Klasse, indem Sie Ihre Microsoft Project-Datei laden.

```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
## Schritt 3: Lesen Sie die Informationen zur Seitenlegende
Greifen Sie über die Standardansicht des Projekts auf die Informationen zur Seitenlegende zu.

```csharp
var legend = project.DefaultView.PageInfo.Legend;
```
## Schritt 4: Legendeninformationen anzeigen
Geben Sie die Legendendetails wie linken Text, linkes Bild, zentrierter Text, zentriertes Bild, rechter Text, rechtes Bild, Legendenstatus und Breite aus.

```csharp
Console.WriteLine("Legend left text: {0} ", legend.LeftText);
Console.WriteLine("Legend left image: {0} ", legend.LeftImage);
Console.WriteLine("Legend center text: {0} ", legend.CenteredText);
Console.WriteLine("Legend center image: {0} ", legend.CenteredImage);
Console.WriteLine("Legend right text: {0} ", legend.RightText);
Console.WriteLine("Legend right image: {0} ", legend.RightImage);
Console.WriteLine("Legend On: {0} ", legend.LegendOn);
Console.WriteLine("Legend Width: {0} ", legend.Width);
```
## Schritt 5: Legende ändern
Ändern Sie optional die Legende nach Bedarf. In diesem Beispiel ändern wir den linken Text.

```csharp
legend.LeftText = "New Left Text";
```
## Schritt 6: Änderungen speichern
Speichern Sie die an der Projektdatei vorgenommenen Änderungen.

```csharp
project.Save(DataDir + "WorkWithPageLegend_out.mpp", SaveFileFormat.Mpp);
```

## Abschluss
Zusammenfassend lässt sich sagen, dass die Beherrschung der Konfiguration von MS Project-Seitenlegenden mit Aspose.Tasks für .NET die Projektmanagementfunktionen innerhalb des .NET-Ökosystems erheblich verbessern kann. Durch Befolgen der beschriebenen Schritte und Voraussetzungen können Entwickler diese Funktionalität nahtlos in ihre Projekte integrieren und so eine bessere Visualisierung und Interpretation der Projektdaten gewährleisten.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit anderen .NET-Frameworks verwenden?
A: Ja, Aspose.Tasks für .NET ist mit verschiedenen .NET-Frameworks kompatibel und gewährleistet so Flexibilität und Anpassungsfähigkeit an verschiedene Projektanforderungen.
### F: Gibt es eine Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/), sodass Sie die Funktionen vor dem Kauf erkunden können.
### F: Gibt es Einschränkungen bei der Verwendung temporärer Lizenzen für Aspose.Tasks für .NET?
A: Temporäre Lizenzen bieten vollen Zugriff auf Aspose.Tasks für .NET-Funktionen, sind jedoch zeitlich begrenzt. Sie eignen sich für kurzfristige Projekte oder Evaluierungszwecke.
### F: Kann ich Seitenlegenden über das bereitgestellte Beispiel hinaus weiter anpassen?
A: Absolut, Aspose.Tasks für .NET bietet umfangreiche Anpassungsoptionen, mit denen Sie Seitenlegenden an Ihre spezifischen Projektanforderungen anpassen können.
### F: Wo finde ich Support oder Community-Foren für Aspose.Tasks für .NET?
 A: Sie können Unterstützung suchen und sich in der Community engagieren[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15), wo Sie Antworten auf Fragen finden und mit anderen Entwicklern interagieren können.
---
title: Speichern Sie MS Project-Dateien als Vorlagen mit Aspose.Tasks
linktitle: Vorlagenoptionen für Aspose.Tasks speichern
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Dateien mit Aspose.Tasks für .NET als Vorlagen speichern. Passen Sie die Vorlageneinstellungen für ein optimiertes Projektmanagement an.
weight: 18
url: /de/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Speichern Sie MS Project-Dateien als Vorlagen mit Aspose.Tasks

## Einführung
In diesem Tutorial werden wir den Prozess des Speicherns einer Vorlage mit Aspose.Tasks für .NET Schritt für Schritt durchgehen. Vorlagen sind nützlich, um Projektstrukturen und -einstellungen für die zukünftige Verwendung zu standardisieren. Wir zeigen Ihnen, wie Sie ein Projekt als Vorlage speichern und dabei seine Eigenschaften anpassen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Aspose.Tasks for .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Tasks for .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
2. Kenntnisse der C#-Programmierung: Um die bereitgestellten Codeausschnitte zu verstehen und umzusetzen, sind Grundkenntnisse der C#-Programmierung erforderlich.
3. Microsoft Project-Datei: Halten Sie eine Microsoft Project-Datei (MPP-Format) bereit, die Sie als Vorlage speichern möchten.

## Namespaces importieren
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Schritt 1: Projekt laden
Zuerst müssen wir die Microsoft Project-Datei (.mpp) laden, die wir als Vorlage speichern möchten.
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Schritt 2: Informationen zur Projektdatei abrufen
Rufen Sie Informationen zur geladenen Projektdatei ab, z. B. deren Format.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Schritt 3: Konfigurieren Sie die Optionen zum Speichern von Vorlagen
Erstellen Sie Optionen zum Speichern von Vorlagen und konfigurieren Sie deren Eigenschaften entsprechend Ihren Anforderungen. Mit diesen Optionen können Sie anpassen, welche Daten aus der Vorlage entfernt werden sollen.
```csharp
var options = new SaveTemplateOptions
{
	// Entfernen Sie alle Fixkosten aus der Projektvorlage
	RemoveFixedCosts = true,
	// Entfernen Sie alle tatsächlichen Werte aus der Projektvorlage
	RemoveActualValues = true,
	// Entfernen Sie Ressourcentarife aus der Projektvorlage
	RemoveResourceRates = true,
	// Entfernen Sie alle Basiswerte aus der Projektvorlage
	RemoveBaselineValues = true
};
```
## Schritt 4: Projekt als Vorlage speichern
Speichern Sie das Projekt als Vorlage mit den angegebenen Optionen.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Schritt 5: Informationen zur Vorlagendatei abrufen
Rufen Sie Informationen über die gespeicherte Vorlagendatei ab, z. B. deren Format.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Glückwunsch! Sie haben eine Vorlage erfolgreich mit Aspose.Tasks für .NET gespeichert und ihre Eigenschaften nach Bedarf angepasst.

## Abschluss
In diesem Tutorial haben wir untersucht, wie man eine Microsoft Project-Datei mit Aspose.Tasks für .NET als Vorlage speichert. Vorlagen sind wertvoll, um Projektstrukturen und -einstellungen zu standardisieren und zukünftige Projekterstellungen zu optimieren.
## FAQs
### F: Kann ich anpassen, welche Daten aus der Vorlage entfernt werden sollen?
A: Ja, Sie können die Optionen zum Speichern von Vorlagen konfigurieren, um bestimmte Daten wie Fixkosten, Istwerte, Ressourcensätze und Basiswerte zu entfernen.
### F: Ist Aspose.Tasks für .NET mit allen Versionen von Microsoft Project kompatibel?
A: Aspose.Tasks für .NET bietet umfassende Kompatibilität mit verschiedenen Versionen von Microsoft Project und gewährleistet so eine nahtlose Integration und Funktionalität.
### F: Kann ich Vorlagen auf bestehende Projekte anwenden?
A: Ja, Sie können Vorlagen auf bestehende Projekte anwenden, indem Sie die Vorlagendatei laden und sie bei Bedarf mit Ihrem aktuellen Projekt zusammenführen.
### F: Unterstützt Aspose.Tasks für .NET die plattformübergreifende Entwicklung?
A: Aspose.Tasks für .NET ist in erster Linie für .NET Framework-Anwendungen konzipiert, die auf Windows-Plattformen ausgeführt werden.
### F: Ist technischer Support für Aspose.Tasks für .NET verfügbar?
 A: Ja, Sie können technische Unterstützung und Anleitung von der Aspose.Tasks-Community anfordern[Foren](https://forum.aspose.com/c/tasks/15)oder wenden Sie sich direkt an das Support-Team.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

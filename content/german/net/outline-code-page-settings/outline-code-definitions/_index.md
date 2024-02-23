---
title: Definitionen für die Behandlung von MS Project Outline-Code in Aspose.Tasks
linktitle: Umgang mit Gliederungscodedefinitionen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET mit MS Project-Gliederungscodedefinitionen umgehen und so Ihre Projektmanagementanwendungen stärken.
type: docs
weight: 12
url: /de/net/outline-code-page-settings/outline-code-definitions/
---
## Einführung
Microsoft Project ist ein leistungsstarkes Tool zum Verwalten von Projekten, und Aspose.Tasks für .NET bietet umfassende Unterstützung für die programmgesteuerte Bearbeitung von Projektdateien. Ein wesentlicher Aspekt des Projektmanagements ist die Organisation von Aufgaben mithilfe von Gliederungscodes. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für .NET mit MS Project-Gliederungscodedefinitionen umgehen.
## Voraussetzungen
Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Installation von Aspose.Tasks für .NET
 Stellen Sie sicher, dass Sie Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
### 2. Grundlegendes Verständnis von C# und .NET Framework
Machen Sie sich mit der Programmiersprache C# und dem .NET Framework vertraut, da für dieses Tutorial C#-Kenntnisse auf mittlerem Niveau erforderlich sind.
### 3. Integrierte Entwicklungsumgebung (IDE)
Installieren Sie auf Ihrem System eine IDE wie Visual Studio zum Codieren und Debuggen.
## Namespaces importieren
Bevor wir mit dem Codieren beginnen, importieren wir die notwendigen Namespaces, um mit Aspose.Tasks für .NET zu arbeiten.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Lassen Sie uns nun das bereitgestellte Beispiel zum besseren Verständnis in mehrere Schritte aufteilen.
## Schritt 1: Laden Sie die Projektdatei
Zuerst müssen wir die MS Project-Datei in unsere Anwendung laden.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Schritt 2: Erstellen Sie eine Gliederungscodedefinition
Lassen Sie uns nun eine neue Gliederungscodedefinition erstellen.
```csharp
var outline = new OutlineCodeDefinition();
```
## Schritt 3: Feldnummer und -namen festlegen
Legen Sie die Feldnummer und den Namen für den Gliederungscode fest.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Schritt 4: Legen Sie die GUID und andere Eigenschaften fest
Legen Sie die GUID und andere Eigenschaften des Gliederungscodes fest.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Schritt 5: Umrissmaske hinzufügen
Fügen Sie dem Gliederungscode eine Gliederungsmaske hinzu.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Schritt 6: Legen Sie weitere Eigenschaften fest
Legen Sie zusätzliche Eigenschaften des Gliederungscodes fest.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Schritt 7: Gliederungswert hinzufügen
Zum Schluss fügen wir dem Gliederungscode einen Gliederungswert hinzu.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für .NET mit MS Project-Gliederungscodedefinitionen umgeht. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie Gliederungscodes in Ihren Projektdateien effizient programmgesteuert bearbeiten.
## FAQs
### F1: Kann ich Aspose.Tasks für .NET mit verschiedenen Versionen von MS Project-Dateien verwenden?
A: Ja, Aspose.Tasks für .NET unterstützt verschiedene Versionen von MS Project-Dateien, einschließlich MPP- und XML-Formate.
### F2: Ist Aspose.Tasks für .NET mit .NET Core kompatibel?
A: Ja, Aspose.Tasks für .NET ist mit .NET Core kompatibel, sodass Sie plattformübergreifende Anwendungen entwickeln können.
### F3: Kann ich Ressourcenzuweisungen mit Aspose.Tasks für .NET manipulieren?
A: Ja, Aspose.Tasks für .NET bietet umfangreiche Funktionen zum Bearbeiten von Ressourcenzuweisungen, einschließlich des Hinzufügens, Aktualisierens und Entfernens von Zuweisungen.
### F4: Unterstützt Aspose.Tasks für .NET das Lesen benutzerdefinierter Felder aus MS Project-Dateien?
A: Absolut, Aspose.Tasks für .NET unterstützt das Lesen und Schreiben benutzerdefinierter Felder, einschließlich Gliederungscodes, aus MS Project-Dateien.
### F5: Gibt es ein Community-Forum für Aspose.Tasks für .NET?
 A: Ja, Sie können dem Community-Forum für Aspose.Tasks für .NET beitreten[Hier](https://forum.aspose.com/c/tasks/15) um Fragen zu stellen, Wissen auszutauschen und mit anderen Entwicklern zusammenzuarbeiten.
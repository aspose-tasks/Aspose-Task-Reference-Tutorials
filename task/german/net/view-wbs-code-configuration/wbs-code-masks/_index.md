---
title: Schritt-für-Schritt-PSP-Codekonfiguration in Aspose.Tasks .NET
linktitle: Konfigurieren von WBS-Codemasken in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die Schritt-für-Schritt-Konfiguration von WBS-Codemasken in .NET-Projekten mit Aspose.Tasks. Erweitern Sie mühelos Ihre Projektmanagementfunktionen.
type: docs
weight: 14
url: /de/net/view-wbs-code-configuration/wbs-code-masks/
---
## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die effiziente Bearbeitung von Projektmanagementdaten in .NET-Anwendungen ermöglicht. In diesem Tutorial untersuchen wir den Prozess der Konfiguration von WBS-Codemasken (Work Breakdown Structure) mithilfe von Aspose.Tasks.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Tasks für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Aspose.Tasks für die .NET-Dokumentation](https://reference.aspose.com/tasks/net/).
- Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine funktionierende .NET-Entwicklungsumgebung eingerichtet haben.
- Dokumentverzeichnis: Wählen Sie ein Verzeichnis auf Ihrem System zum Speichern der Projektdateien.
## Namespaces importieren
Fügen Sie in Ihr .NET-Projekt die erforderlichen Namespaces für die Arbeit mit Aspose.Tasks ein:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Schritt 1: Erstellen Sie eine Projektinstanz
Beginnen Sie mit der Erstellung einer neuen Projektinstanz:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Schritt 2: Definieren Sie die WBS-Codedefinition
Richten Sie die WBS-Codedefinition für Ihr Projekt ein:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Schritt 3: WBS-Codemasken hinzufügen
Definieren Sie WBS-Codemasken und fügen Sie sie dem Projekt hinzu:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Schritt 4: Aufgaben erstellen
Aufgaben zum Projekt hinzufügen:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Schritt 5: Neu berechnen
Berechnen Sie das Projekt neu, um sicherzustellen, dass die PSP-Codes korrekt angewendet werden:
```csharp
project.Recalculate();
```
## Schritt 6: WBS-Maskeninformationen anzeigen
Informationen zu WBS-Masken an die Konsole ausgeben:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Schritt 7: Speichern Sie das Projekt
Speichern Sie das Projekt mit den hinzugefügten WBS-Codes:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Glückwunsch! Sie haben WBS-Codemasken in Ihrem Aspose.Tasks-Projekt erfolgreich konfiguriert.
## Abschluss
In diesem Tutorial haben wir den schrittweisen Prozess der Konfiguration von WBS-Codemasken mit Aspose.Tasks für .NET untersucht. Diese leistungsstarke Bibliothek bietet Entwicklern eine nahtlose Möglichkeit, die Projektmanagementfunktionen in ihren .NET-Anwendungen zu verbessern.

## FAQs
### Kann ich Aspose.Tasks kostenlos nutzen?
 Aspose.Tasks bietet eine kostenlose Testversion, die Sie herunterladen können[Hier](https://releases.aspose.com/).
### Wo finde ich zusätzliche Unterstützung?
 Besuche den[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für die Unterstützung der Gemeinschaft.
### Wie kann ich eine temporäre Lizenz erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Gibt es eine ausführliche Dokumentation?
 Ja, die umfassende Dokumentation ist vorhanden[Hier](https://reference.aspose.com/tasks/net/).
### Wo kann ich Aspose.Tasks kaufen?
 Kaufen Sie Aspose.Tasks[Hier](https://purchase.aspose.com/buy).
---
title: Bild Speichern Sie MS Project-Optionen für Aspose.Tasks
linktitle: Bildspeicheroptionen für Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Optionen mit Aspose.Tasks für .NET als Bilder speichern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 11
url: /de/net/saving-options/image-save-options/
---

## Einführung
In der Welt der Softwareentwicklung ist die effiziente Bearbeitung von Projektaufgaben entscheidend für ein erfolgreiches Projektmanagement. Aspose.Tasks für .NET bietet eine leistungsstarke Lösung für Entwickler, die mit Microsoft Project-Dateien arbeiten und es ihnen ermöglicht, Projektaufgaben nahtlos in ihren .NET-Anwendungen zu bearbeiten, zu konvertieren und zu verwalten.
## Voraussetzungen
Bevor Sie Aspose.Tasks für .NET verwenden, um MS Project-Optionen als Bilder zu speichern, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installieren Sie Aspose.Tasks für .NET
 Zunächst muss Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert sein. Sie können die Bibliothek unter herunterladen[Webseite](https://releases.aspose.com/tasks/net/) und befolgen Sie die mitgelieferten Installationsanweisungen.
### 2. Erwerben Sie eine Lizenz (optional)
 Während Aspose.Tasks für .NET im Evaluierungsmodus ohne Lizenz verwendet werden kann, wird der Erwerb einer Lizenz für den vollen Funktionsumfang und zur Beseitigung von Evaluierungseinschränkungen empfohlen. Eine Lizenz können Sie bei erwerben[Kaufseite](https://purchase.aspose.com/buy) oder entscheiden Sie sich für a[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) zu Testzwecken.
### 3. Grundkenntnisse der C#- und .NET-Entwicklung
Um den Beispielen folgen und die Funktionalitäten von Aspose.Tasks effektiv in Ihre Anwendungen integrieren zu können, sind grundlegende Kenntnisse der Programmiersprache C# und des .NET-Frameworks erforderlich.
## Namespaces importieren
Bevor wir mit dem Speichern von MS Project-Optionen als Bilder mit Aspose.Tasks für .NET beginnen, stellen wir sicher, dass wir die erforderlichen Namespaces in unser C#-Projekt importieren:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Schritt 1: Dokumentverzeichnispfad einrichten
Stellen Sie sicher, dass Sie ein bestimmtes Verzeichnis für Ihre Dokumente haben und legen Sie den Pfad entsprechend fest:
```csharp
String DataDir = "Your Document Directory";
```
## Schritt 2: Laden Sie die MS Project-Datei
 Initialisieren Sie eine neue`Project` Objekt durch Laden der MS Project-Datei:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Schritt 3: Definieren Sie die Optionen zum Speichern von Bildern
 Erstellen Sie eine Instanz von`ImageSaveOptions` und legen Sie die gewünschten Einstellungen fest:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Schritt 4: Geben Sie die zu speichernden Seiten an
Geben Sie bei Bedarf die zu speichernden Seiten an. In diesem Beispiel fügen wir Seite 2 hinzu:
```csharp
options.Pages.Add(2);
```
## Schritt 5: Speichern Sie das Bild
Abschließend speichern Sie die ausgewählten Seiten als Bild mit den angegebenen Optionen:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Abschluss
Aspose.Tasks für .NET vereinfacht die Arbeit mit MS Project-Dateien und ermöglicht Entwicklern die mühelose Bearbeitung von Projektaufgaben. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie MS Project-Optionen effizient als Bilder in Ihren .NET-Anwendungen speichern.
## FAQs
### F1: Kann ich Aspose.Tasks für .NET ohne Lizenz verwenden?
A: Ja, Sie können Aspose.Tasks für .NET ohne Lizenz im Testmodus verwenden. Es wird jedoch empfohlen, eine Lizenz für den vollen Funktionsumfang zu erwerben und Evaluierungsbeschränkungen aufzuheben.
### F2: Wie kann ich eine temporäre Lizenz zum Testen erhalten?
 A: Sie können eine temporäre Lizenz zu Testzwecken bei der erhalten[temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).
### F3: Ist Aspose.Tasks für .NET mit anderen .NET-Frameworks kompatibel?
A: Ja, Aspose.Tasks für .NET ist mit verschiedenen .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Standard.
### F4: Kann ich die Optionen zum Speichern von Bildern weiter anpassen?
A: Ja, Sie können die Bildspeicheroptionen entsprechend Ihren spezifischen Anforderungen anpassen, z. B. durch Anpassen der Seitengröße, Auflösung oder des Ausgabeformats.
### F5: Wo finde ich Unterstützung für Aspose.Tasks für .NET?
 A: Support und Unterstützung für Aspose.Tasks für .NET finden Sie auf der[Forum](https://forum.aspose.com/c/tasks/15).
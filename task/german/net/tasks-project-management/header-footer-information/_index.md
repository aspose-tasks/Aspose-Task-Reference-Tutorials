---
title: Extrahieren Sie Kopf- und Fußzeileninformationen mit Aspose.Tasks
linktitle: Kopf- und Fußzeileninformationen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET Kopf- und Fußzeileninformationen aus MS Project-Dateien extrahieren. Einfache, effiziente und entwicklerfreundliche Lösung.
type: docs
weight: 29
url: /de/net/tasks-project-management/header-footer-information/
---
## Einführung
Aspose.Tasks für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die einfache Bearbeitung von Microsoft Project-Dateien ermöglicht. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks Kopf- und Fußzeileninformationen aus MS Project-Dateien abrufen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Visual Studio: Installieren Sie Visual Studio auf Ihrem System.
2.  Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/net/).
3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C#.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Dadurch können Sie auf die Klassen und Methoden zugreifen, die von der Aspose.Tasks-Bibliothek bereitgestellt werden.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Schritt 1: Projektobjekt initialisieren
 Zunächst müssen Sie a initialisieren`Project` Objekt durch Laden einer vorhandenen MS Project-Datei.
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Schritt 2: Kopf- und Fußzeileninformationen abrufen
 Sobald Sie die Projektdatei geladen haben, können Sie die Kopf- und Fußzeileninformationen mithilfe von abrufen`PageInfo` Eigentum.
```csharp
var info = project.DefaultView.PageInfo;
// Header-Informationen
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Fußzeileninformationen
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Wenn Sie diese einfachen Schritte befolgen, können Sie mit Aspose.Tasks für .NET ganz einfach Kopf- und Fußzeileninformationen aus MS Project-Dateien abrufen.

## Abschluss
In diesem Tutorial haben wir untersucht, wie man mit Aspose.Tasks für .NET Kopf- und Fußzeileninformationen aus MS Project-Dateien extrahiert. Diese leistungsstarke Bibliothek vereinfacht die Arbeit mit Projektdateien in C#-Anwendungen und stellt Entwicklern robuste Werkzeuge zur Bearbeitung zur Verfügung.
### FAQs
### Kann ich die Kopf- und Fußzeileninformationen mit Aspose.Tasks ändern?
Ja, Sie können die Kopf- und Fußzeileninformationen programmgesteuert mit Aspose.Tasks für .NET ändern.
### Unterstützt Aspose.Tasks neben MS Project auch andere Projektdateiformate?
Ja, Aspose.Tasks unterstützt verschiedene Projektdateiformate, einschließlich MPP, XML und MPX.
### Gibt es eine kostenlose Testversion für Aspose.Tasks?
 Ja, Sie können eine kostenlose Testversion von Aspose.Tasks herunterladen unter[Hier](https://releases.aspose.com/).
### Wo finde ich Dokumentation für Aspose.Tasks?
 Sie finden die Dokumentation für Aspose.Tasks[Hier](https://reference.aspose.com/tasks/net/).
### Wie kann ich Unterstützung für Aspose.Tasks erhalten?
 Sie können Unterstützung für Aspose.Tasks erhalten, indem Sie die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
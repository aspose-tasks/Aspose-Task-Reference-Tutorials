---
title: Extrahieren Sie MS Project-Informationen in Aspose.Tasks
linktitle: Extrahieren von Projektinformationen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Informationen mühelos mit Aspose.Tasks für .NET extrahieren. Tauchen Sie ein in unser umfassendes Tutorial.
type: docs
weight: 20
url: /de/net/project-management-integration/project-information/
---
## Einführung
Möchten Sie mithilfe von Aspose.Tasks für .NET effizient Informationen aus Microsoft Project-Dateien extrahieren? In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess. Bevor wir uns jedoch mit den Implementierungsdetails befassen, stellen wir zunächst sicher, dass Sie über alles verfügen, was Sie benötigen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
### 1. Aspose.Tasks für .NET
 Stellen Sie sicher, dass Sie die Aspose.Tasks für .NET-Bibliothek installiert haben. Wenn Sie dies noch nicht getan haben, können Sie es hier herunterladen[Aspose.Tasks für .NET-Website](https://releases.aspose.com/tasks/net/).
### 2. Anmeldeinformationen für SharePoint
Sie benötigen die Anmeldeinformationen, um auf SharePoint zuzugreifen, wo Ihre MS Project-Dateien gespeichert sind. Stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:
- SharePoint-Domänenadresse
- Nutzername
- Passwort
## Namensräume importieren
Sobald Sie alle Voraussetzungen geklärt haben, ist es an der Zeit, die erforderlichen Namespaces in Ihr Projekt zu importieren.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Lassen Sie uns nun den Prozess des Extrahierens von MS Project-Informationen in mehrere Schritte unterteilen.
## Schritt 1: Anmeldeinformationen bereitstellen
Zunächst müssen Sie Ihre SharePoint-Anmeldeinformationen angeben, um auf den Project Server zuzugreifen.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Schritt 2: Initialisieren Sie den Project Server Manager
 Als nächstes initialisieren Sie a`ProjectServerManager` Instanz mit den bereitgestellten Anmeldeinformationen.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Schritt 3: Projektliste abrufen
Jetzt können Sie die Liste der Projekte vom Project Server abrufen.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Schritt 4: Projektinformationen drucken
Gehen Sie abschließend die Liste der Projekte durch und drucken Sie deren Informationen aus.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie MS Project-Informationen mit Aspose.Tasks für .NET extrahieren. Mit diesem Wissen können Sie diese Funktionalität nun nahtlos in Ihre .NET-Anwendungen integrieren.
## FAQs
### F1: Kann ich Aspose.Tasks für .NET mit jeder Version von Microsoft Project verwenden?
A: Ja, Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project, einschließlich 2003, 2007, 2010, 2013, 2016 und 2019.
### F2: Ist Aspose.Tasks für .NET sowohl mit Windows- als auch mit Linux-Plattformen kompatibel?
A: Ja, Aspose.Tasks für .NET ist sowohl mit Windows- als auch mit Linux-Plattformen kompatibel und somit vielseitig für verschiedene Entwicklungsumgebungen geeignet.
### F3: Kann ich Aufgabenabhängigkeiten mit Aspose.Tasks für .NET extrahieren?
A: Auf jeden Fall! Aspose.Tasks für .NET bietet robuste Funktionen zum Extrahieren nicht nur grundlegender Projektinformationen, sondern auch Aufgabenabhängigkeiten und anderer komplexer Details.
### F4: Bietet Aspose.Tasks für .NET technischen Support?
 A: Ja, Sie können technischen Support für Aspose.Tasks für .NET über das erhalten[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15), wo Sie Fragen stellen und Hilfe von Experten erhalten können.
### F5: Kann ich Aspose.Tasks für .NET testen, bevor ich es kaufe?
 A: Auf jeden Fall! Sie können eine kostenlose Testversion von Aspose.Tasks für .NET unter erhalten[Veröffentlichungsseite](https://releases.aspose.com/)So können Sie die Funktionen erkunden, bevor Sie eine Kaufentscheidung treffen.
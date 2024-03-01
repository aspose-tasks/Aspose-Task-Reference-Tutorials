---
title: Optionen zum Speichern von MS Project auf dem Server für Aspose.Tasks
linktitle: Project Server-Speicheroptionen für Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Microsoft Project-Optionen für Aspose.Tasks mithilfe der Project Server-Integration speichern. Verbessern Sie Ihre Projektmanagement-Workflows.
type: docs
weight: 16
url: /de/net/saving-options/project-server-save-options/
---
## Einführung
In diesem Tutorial befassen wir uns mit dem Speichern von Microsoft Project-Optionen für Aspose.Tasks mithilfe von Project Server. Aspose.Tasks ist eine leistungsstarke .NET-API, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten. Durch die Nutzung der Project Server-Funktionen können wir Aspose.Tasks nahtlos in unsere Projektmanagement-Workflows integrieren. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Aspose.Tasks für .NET: Installieren Sie Aspose.Tasks für .NET von[Download-Link](https://releases.aspose.com/tasks/net/).
   
2. Zugriff auf Project Server: Sie benötigen Zugangsdaten und die URL Ihrer Project Server-Instanz. Wenn Sie noch keins haben, können Sie eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).
3. Microsoft Project-Datei: Bereiten Sie die Microsoft Project-Datei (.mpp) vor, die Sie mit Aspose.Tasks speichern möchten.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Schritt 1: Projekt und Anmeldeinformationen initialisieren
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Stellen Sie sicher, dass Sie ersetzen`"Your Document Directory"`, `URL`, `Domain`, `UserName` , Und`Password` mit Ihren tatsächlichen Werten.
## Schritt 2: Erstellen Sie den Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Schritt 3: Speicheroptionen definieren
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Verstelle die`ProjectGuid`, `ProjectName`, `Timeout` , Und`PollingInterval` nach Ihren Anforderungen.
## Schritt 4: Projekt auf dem Server speichern
```csharp
manager.CreateNewProject(project, options);
```
Dadurch wird das Projekt mit den angegebenen Optionen auf dem Project Server gespeichert.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Microsoft Project-Optionen für Aspose.Tasks mithilfe der Project Server-Integration speichert. Wenn Sie diese Schritte befolgen, können Sie Aspose.Tasks nahtlos in Ihre Projektmanagement-Workflows integrieren und so die Effizienz und Produktivität steigern.
## FAQs
### F: Kann ich Aspose.Tasks mit verschiedenen Versionen von Microsoft Project verwenden?
A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### F: Gibt es eine Testversion für Aspose.Tasks?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks erhalten von[Hier](https://releases.aspose.com/).
### F: Unterstützt Aspose.Tasks Multithreading?
A: Ja, Aspose.Tasks ist threadsicher und ermöglicht den gleichzeitigen Zugriff auf Projektdaten.
### F: Kann ich Speicheroptionen anpassen, wenn ich die Project Server-Integration verwende?
A: Ja, Sie können Speicheroptionen wie Projektname, Timeout und Abfrageintervall an Ihre Anforderungen anpassen.
### F: Wo finde ich Unterstützung für Aspose.Tasks?
 A: Unterstützung und Hilfe finden Sie auf der[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
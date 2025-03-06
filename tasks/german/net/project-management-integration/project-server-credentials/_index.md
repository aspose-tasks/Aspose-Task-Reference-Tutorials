---
title: Verwalten von MS Project Server-Anmeldeinformationen in Aspose.Tasks
linktitle: Verwalten von Project Server-Anmeldeinformationen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project Server-Anmeldeinformationen nahtlos mit Aspose.Tasks für .NET verwalten. Verbessern Sie die Effizienz des Projektmanagements.
weight: 22
url: /de/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten von MS Project Server-Anmeldeinformationen in Aspose.Tasks

## Einführung
Im Bereich Projektmanagement sind effektive Koordination und reibungslose Kommunikation entscheidend für eine erfolgreiche Projektabwicklung. Aspose.Tasks für .NET bietet eine umfassende Lösung für die Verwaltung von Microsoft Project Server-Anmeldeinformationen, die es Benutzern ermöglicht, sicher auf Projektdaten zuzugreifen und diese zu bearbeiten. Dieses Tutorial befasst sich mit dem Prozess der Verwaltung von MS Project Server-Anmeldeinformationen mithilfe von Aspose.Tasks für .NET und führt Benutzer durch jeden Schritt, um ein reibungsloses Erlebnis zu gewährleisten.
## Voraussetzungen
Bevor Sie mit der Verwaltung von MS Project Server-Anmeldeinformationen mit Aspose.Tasks für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Aspose.Tasks für .NET installieren
 Laden Sie zunächst Aspose.Tasks für .NET von der bereitgestellten Website herunter und installieren Sie es[Download-Link](https://releases.aspose.com/tasks/net/). Befolgen Sie die Installationsanweisungen, um die Bibliothek nahtlos in Ihre .NET-Umgebung zu integrieren.
### 2. Zugangsdaten
Sammeln Sie die erforderlichen Anmeldeinformationen für den Zugriff auf den MS Project Server. Dazu gehören die SharePoint-Domänenadresse, der Benutzername und das Kennwort, die dem Project Server zugeordnet sind.

## Namespaces importieren
Importieren Sie in Ihr .NET-Projekt die erforderlichen Namespaces, um die von Aspose.Tasks für .NET bereitgestellten Funktionen effizient zu nutzen.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Schritt 1: Definieren Sie den Dokumentverzeichnispfad
```csharp
String DataDir = "Your Document Directory";
```
## Schritt 2: Legen Sie die SharePoint-Domänenadresse, den Benutzernamen und das Passwort fest
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Schritt 3: Erstellen Sie Project Server-Anmeldeinformationen
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Schritt 4: Projektdatei laden
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Schritt 5: Initialisieren Sie den Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Schritt 6: Neues Projekt erstellen
```csharp
manager.CreateNewProject(newProject);
```
## Schritt 7: Projektliste abrufen
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Schritt 8: Durchlaufen Sie die Projektliste
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Abschluss
Die effektive Verwaltung der MS Project Server-Anmeldeinformationen ist für ein optimiertes Projektmanagement von größter Bedeutung. Aspose.Tasks für .NET vereinfacht diesen Prozess, indem es eine Reihe robuster Funktionen bereitstellt. Durch Befolgen der Schritt-für-Schritt-Anleitung in diesem Tutorial können Benutzer Aspose.Tasks für .NET nahtlos in ihre Projekte integrieren und so einen sicheren Zugriff und eine sichere Bearbeitung der Projektdaten gewährleisten.
## FAQs
### F: Ist Aspose.Tasks für .NET mit allen Versionen von Microsoft Project Server kompatibel?
A: Aspose.Tasks für .NET ist so konzipiert, dass es mit verschiedenen Versionen von Microsoft Project Server kompatibel ist und den Benutzern Vielseitigkeit und Flexibilität gewährleistet.
### F: Kann ich Aspose.Tasks für .NET in mein bestehendes .NET-Projekt integrieren?
A: Ja, Aspose.Tasks für .NET kann nahtlos in bestehende .NET-Projekte integriert werden und ermöglicht so effiziente Projektmanagementfunktionen.
### F: Bietet Aspose.Tasks für .NET Unterstützung für den Zugriff auf Projektressourcen?
A: Absolut, Aspose.Tasks für .NET bietet umfassende Unterstützung für den Zugriff auf und die Bearbeitung von Projektressourcen und steigert so die Effizienz des Projektmanagements.
### F: Gibt es Lizenzoptionen für Aspose.Tasks für .NET?
A: Ja, Aspose.Tasks für .NET bietet flexible Lizenzoptionen, einschließlich temporärer Lizenzen für Testzwecke und Volllizenzen für die kommerzielle Nutzung.
### F: Wo kann ich Hilfe oder Support für Aspose.Tasks für .NET suchen?
 A: Bei Fragen oder Hilfe zu Aspose.Tasks für .NET können Sie das Support-Forum unter besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).## Vollständiger Quellcode
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

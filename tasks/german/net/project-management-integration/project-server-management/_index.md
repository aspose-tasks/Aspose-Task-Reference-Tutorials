---
title: Verwalten von MS Project Server mit Aspose.Tasks
linktitle: Verwalten von Project Server mit Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Nutzen Sie die nahtlose Verwaltung von MS Project Server mit Aspose.Tasks für .NET. Automatisieren Sie Projektaufgaben mühelos.
weight: 23
url: /de/net/project-management-integration/project-server-management/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verwalten von MS Project Server mit Aspose.Tasks

## Einführung
In diesem Tutorial befassen wir uns mit der Verwaltung von MS Project Server mithilfe von Aspose.Tasks für .NET. Aspose.Tasks ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft Project-Dateien zu arbeiten und so eine nahtlose Integration und Bearbeitung von Projektdaten zu ermöglichen.
## Voraussetzungen
Bevor wir uns mit der Verwaltung von MS Project Server mit Aspose.Tasks befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen eingerichtet haben:
1. Microsoft Project Server: Sie benötigen Zugriff auf eine Microsoft Project Server-Instanz, auf der Sie über Administratorrechte oder zumindest Berechtigungen zum Erstellen und Verwalten von Projekten verfügen.
2.  Aspose.Tasks for .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Tasks for .NET-Bibliothek heruntergeladen und installiert haben. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/tasks/net/).
3. Anmeldeinformationen: Besorgen Sie sich die erforderlichen Anmeldeinformationen für die Authentifizierung bei Ihrer MS Project Server-Instanz. Dazu gehören in der Regel ein Benutzername und ein Passwort.
## Namespaces importieren
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihren C#-Code importiert haben:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Schritt 1: Authentifizierungsdaten einrichten
Zunächst müssen Sie Authentifizierungsdaten einrichten, um eine Verbindung zu Ihrer MS Project Server-Instanz herzustellen. Dazu gehören die Domänenadresse, der Benutzername und das Passwort.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Schritt 2: Laden Sie das Projekt
Laden Sie als Nächstes die MS Project-Datei, die Sie mit Aspose.Tasks verwalten möchten.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Schritt 3: Erstellen Sie den Project Server Manager
 Instanziieren Sie a`ProjectServerManager` Objekt mithilfe der zuvor definierten Anmeldeinformationen.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Schritt 4: Speicheroptionen definieren
Definieren Sie spezifische Speicheroptionen für Ihr Projekt. Sie können beispielsweise ein Timeout für den Vorgang festlegen.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Schritt 5: Projekt erstellen oder aktualisieren
Erstellen oder aktualisieren Sie abschließend das Projekt auf dem MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Glückwunsch! Sie haben MS Project Server erfolgreich mit Aspose.Tasks für .NET verwaltet.

## Abschluss
In diesem Tutorial haben wir untersucht, wie man MS Project Server programmgesteuert mit Aspose.Tasks für .NET verwaltet. Mit den bereitgestellten Schritten können Sie Aspose.Tasks nahtlos in Ihre .NET-Anwendungen integrieren, um Projektmanagementaufgaben auf MS Project Server zu automatisieren.
## FAQs
### F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project Server kompatibel?
A: Aspose.Tasks unterstützt die Integration mit verschiedenen Versionen von Microsoft Project Server und gewährleistet so die Kompatibilität zwischen verschiedenen Umgebungen.
### F: Kann ich mit Aspose.Tasks Massenvorgänge für Projekte durchführen?
A: Ja, mit Aspose.Tasks können Sie Massenvorgänge wie das Erstellen, Aktualisieren und Löschen von Projekten auf MS Project Server durchführen.
### F: Bietet Aspose.Tasks Unterstützung für die Projektplanung und das Ressourcenmanagement?
A: Absolut, Aspose.Tasks bietet umfassende Unterstützung für Projektplanung, Ressourcenzuweisung und Aufgabenverwaltungsfunktionen.
### F: Ist es möglich, Berichtsaufgaben mit Aspose.Tasks zu automatisieren?
A: Ja, Aspose.Tasks ermöglicht Ihnen die Automatisierung der Erstellung benutzerdefinierter Berichte auf der Grundlage von Projektdaten und erleichtert so eine effiziente Projektüberwachung und -analyse.
### F: Kann ich Aspose.Tasks testen, bevor ich es kaufe?
 A: Ja, Sie können die Funktionen von Aspose.Tasks erkunden, indem Sie auf eine kostenlose Testversion zugreifen[Webseite](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

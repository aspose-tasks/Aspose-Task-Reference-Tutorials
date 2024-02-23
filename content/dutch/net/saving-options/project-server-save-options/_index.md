---
title: Server Bewaar MS-projectopties voor Aspose.Tasks
linktitle: Project Server-opslagopties voor Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Microsoft Project-opties voor Aspose.Tasks kunt opslaan met behulp van Project Server-integratie. Verbeter uw projectmanagementworkflows.
type: docs
weight: 16
url: /nl/net/saving-options/project-server-save-options/
---
## Invoering
In deze zelfstudie gaan we dieper in op het opslaan van Microsoft Project-opties voor Aspose.Tasks met behulp van Project Server. Aspose.Tasks is een krachtige .NET API waarmee ontwikkelaars programmatisch met Microsoft Project-bestanden kunnen werken. Door gebruik te maken van de mogelijkheden van Project Server kunnen we Aspose.Tasks naadloos integreren in onze projectmanagementworkflows. Deze tutorial begeleidt u stap voor stap door het proces.
## Vereisten
Voordat u aan de slag gaat, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET: Installeer Aspose.Tasks voor .NET vanaf de[download link](https://releases.aspose.com/tasks/net/).
   
2. Toegang tot Project Server: u hebt toegangsreferenties en de URL van uw Project Server-exemplaar nodig. Als u er nog geen heeft, kunt u een gratis proefversie verkrijgen via[hier](https://releases.aspose.com/).
3. Microsoft Project-bestand: Bereid het Microsoft Project-bestand (.mpp) voor dat u wilt opslaan met Aspose.Tasks.

## Naamruimten importeren
Eerst moet u de benodigde naamruimten in uw project importeren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Stap 1: Initialiseer het project en de referenties
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
 Zorg ervoor dat u vervangt`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,En`Password` met uw werkelijke waarden.
## Stap 2: Maak Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Stap 3: Definieer de opslagopties
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Pas de .... aan`ProjectGuid`, `ProjectName`, `Timeout` ,En`PollingInterval` volgens uw vereisten.
## Stap 4: Project opslaan op server
```csharp
manager.CreateNewProject(project, options);
```
Hierdoor wordt het project met de opgegeven opties op de Project Server opgeslagen.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u Microsoft Project-opties voor Aspose.Tasks kunt opslaan met behulp van Project Server-integratie. Door deze stappen te volgen, kunt u Aspose.Tasks naadloos integreren in uw projectbeheerworkflows, waardoor de efficiëntie en productiviteit worden verbeterd.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks gebruiken met verschillende versies van Microsoft Project?
A: Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks?
 A: Ja, u kunt een gratis proefversie van Aspose.Tasks verkrijgen via[hier](https://releases.aspose.com/).
### Vraag: Ondersteunt Aspose.Tasks multi-threading?
A: Ja, Aspose.Tasks is ontworpen om thread-safe te zijn, waardoor gelijktijdige toegang tot projectgegevens mogelijk is.
### V: Kan ik de opslagopties aanpassen wanneer ik Project Server-integratie gebruik?
A: Ja, u kunt opslagopties zoals projectnaam, time-out en polling-interval aanpassen aan uw vereisten.
### Vraag: Waar kan ik ondersteuning vinden voor Aspose.Tasks?
 A: U kunt ondersteuning en hulp vinden op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).
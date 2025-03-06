---
title: Extraheer MS-projectinformatie in Aspose.Tasks
linktitle: Projectinformatie extraheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u moeiteloos MS Project-informatie kunt extraheren met Aspose.Tasks voor .NET. Duik in onze uitgebreide tutorial.
type: docs
weight: 20
url: /nl/net/project-management-integration/project-information/
---
## Invoering
Wilt u efficiënt informatie uit Microsoft Project-bestanden extraheren met Aspose.Tasks voor .NET? In deze tutorial begeleiden we u stap voor stap door het proces. Maar voordat we ingaan op de implementatiedetails, moeten we er eerst voor zorgen dat u over alles beschikt wat u nodig heeft.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
### 1. Aspose.Tasks voor .NET
 Zorg ervoor dat u de Aspose.Tasks voor .NET-bibliotheek hebt geïnstalleerd. Als u dit nog niet heeft gedaan, kunt u het downloaden via de[Aspose.Tasks voor .NET-website](https://releases.aspose.com/tasks/net/).
### 2. Referenties voor SharePoint
U hebt de inloggegevens nodig om toegang te krijgen tot SharePoint waar uw MS Project-bestanden zijn opgeslagen. Zorg ervoor dat u over de volgende informatie beschikt:
- SharePoint-domeinadres
- Gebruikersnaam
- Wachtwoord
## Naamruimten importeren
Zodra u uw vereisten heeft geregeld, is het tijd om de benodigde naamruimten in uw project te importeren.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Laten we nu het proces van het extraheren van MS Project-informatie in meerdere stappen opsplitsen.
## Stap 1: Geef referenties op
Eerst moet u uw SharePoint-referenties opgeven om toegang te krijgen tot de Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Stap 2: Initialiseer Project Server Manager
 Initialiseer vervolgens a`ProjectServerManager` exemplaar met de opgegeven inloggegevens.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Stap 3: Projectlijst ophalen
Nu kunt u de lijst met projecten ophalen van de Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Stap 4: Projectinformatie afdrukken
Blader ten slotte door de lijst met projecten en druk de informatie ervan af.
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
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u MS Project-informatie kunt extraheren met Aspose.Tasks voor .NET. Met deze kennis kunt u deze functionaliteit nu naadloos integreren in uw .NET-applicaties.
## Veelgestelde vragen
### V1: Kan ik Aspose.Tasks voor .NET gebruiken met elke versie van Microsoft Project?
A: Ja, Aspose.Tasks voor .NET ondersteunt verschillende versies van Microsoft Project, waaronder 2003, 2007, 2010, 2013, 2016 en 2019.
### V2: Is Aspose.Tasks voor .NET compatibel met zowel Windows- als Linux-platforms?
A: Ja, Aspose.Tasks voor .NET is compatibel met zowel Windows- als Linux-platforms, waardoor het veelzijdig is voor verschillende ontwikkelomgevingen.
### V3: Kan ik taakafhankelijkheden extraheren met Aspose.Tasks voor .NET?
EEN: Absoluut! Aspose.Tasks voor .NET biedt robuuste functionaliteit om niet alleen basisprojectinformatie te extraheren, maar ook taakafhankelijkheden en andere ingewikkelde details.
### V4: Biedt Aspose.Tasks voor .NET technische ondersteuning?
 A: Ja, u kunt technische ondersteuning krijgen voor Aspose.Tasks voor .NET via de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15), waar u vragen kunt stellen en hulp kunt inroepen van deskundigen.
### V5: Kan ik Aspose.Tasks voor .NET uitproberen voordat ik het aanschaf?
 EEN: Zeker! U kunt gebruikmaken van een gratis proefversie van Aspose.Tasks voor .NET via de[releases pagina](https://releases.aspose.com/), zodat u de functies ervan kunt verkennen voordat u een aankoopbeslissing neemt.
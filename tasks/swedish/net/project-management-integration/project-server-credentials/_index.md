---
title: Hantera MS Project Server-referenser i Aspose.Tasks
linktitle: Hantera inloggningsuppgifter för projektserver i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar MS Project Server-uppgifter sömlöst med Aspose.Tasks för .NET. Förbättra projektledningseffektiviteten.
weight: 22
url: /sv/net/project-management-integration/project-server-credentials/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera MS Project Server-referenser i Aspose.Tasks

## Introduktion
När det gäller projektledning är effektiv samordning och sömlös kommunikation avgörande för ett framgångsrikt projektgenomförande. Aspose.Tasks för .NET tillhandahåller en omfattande lösning för hantering av Microsoft Project Server-referenser, vilket gör det möjligt för användare att säkert komma åt och manipulera projektdata. Denna handledning fördjupar sig i processen att hantera MS Project Server-referenser med Aspose.Tasks för .NET, och guidar användare genom varje steg för att säkerställa en smidig upplevelse.
## Förutsättningar
Innan du ger dig ut på resan med att hantera MS Project Server-referenser med Aspose.Tasks för .NET, se till att följande förutsättningar är uppfyllda:
### 1. Installera Aspose.Tasks för .NET
 För att börja, ladda ner och installera Aspose.Tasks för .NET från den medföljande[nedladdningslänk](https://releases.aspose.com/tasks/net/). Följ installationsinstruktionerna för att sömlöst integrera biblioteket i din .NET-miljö.
### 2. Åtkomstuppgifter
Samla in de nödvändiga referenserna som krävs för att komma åt MS Project Server. Detta inkluderar SharePoint-domänadressen, användarnamnet och lösenordet som är kopplat till Project Server.

## Importera namnområden
Importera de nödvändiga namnområdena i ditt .NET-projekt för att effektivt använda funktionerna som tillhandahålls av Aspose.Tasks för .NET.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Steg 1: Definiera sökväg för dokumentkatalog
```csharp
String DataDir = "Your Document Directory";
```
## Steg 2: Ställ in SharePoint-domänadress, användarnamn och lösenord
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Steg 3: Skapa inloggningsuppgifter för projektserver
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Steg 4: Ladda projektfilen
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Steg 5: Initiera Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Steg 6: Skapa nytt projekt
```csharp
manager.CreateNewProject(newProject);
```
## Steg 7: Hämta projektlista
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Steg 8: Iterera genom projektlistan
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Slutsats
Att effektivt hantera MS Project Server-referenser är avgörande för strömlinjeformad projektledning. Aspose.Tasks för .NET förenklar denna process genom att tillhandahålla en robust uppsättning funktioner. Genom att följa den steg-för-steg-guide som beskrivs i denna handledning kan användare sömlöst integrera Aspose.Tasks för .NET i sina projekt, vilket säkerställer säker åtkomst och manipulering av projektdata.
## FAQ's
### F: Är Aspose.Tasks för .NET kompatibelt med alla versioner av Microsoft Project Server?
S: Aspose.Tasks för .NET är utformad för att vara kompatibel med olika versioner av Microsoft Project Server, vilket säkerställer mångsidighet och flexibilitet för användarna.
### F: Kan jag integrera Aspose.Tasks för .NET i mitt befintliga .NET-projekt?
S: Ja, Aspose.Tasks för .NET kan sömlöst integreras i befintliga .NET-projekt, vilket underlättar effektiv projektledning.
### F: Ger Aspose.Tasks för .NET stöd för åtkomst till projektresurser?
S: Absolut, Aspose.Tasks för .NET erbjuder omfattande stöd för att komma åt och manipulera projektresurser, vilket förbättrar projektledningseffektiviteten.
### F: Finns det några licensalternativ tillgängliga för Aspose.Tasks för .NET?
S: Ja, Aspose.Tasks för .NET erbjuder flexibla licensalternativ, inklusive tillfälliga licenser för teständamål och fullständiga licenser för kommersiellt bruk.
### F: Var kan jag söka hjälp eller support för Aspose.Tasks för .NET?
 S: För eventuella frågor eller hjälp angående Aspose.Tasks för .NET kan du besöka supportforumet på[Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15).## Komplett källkod
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

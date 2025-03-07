---
title: Extrahera MS Project Information i Aspose.Tasks
linktitle: Extrahera projektinformation i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du extraherar MS Project-information utan ansträngning med Aspose.Tasks för .NET. Dyk in i vår omfattande handledning.
weight: 20
url: /sv/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera MS Project Information i Aspose.Tasks

## Introduktion
Vill du effektivt extrahera information från Microsoft Project-filer med Aspose.Tasks för .NET? I den här handledningen guidar vi dig genom processen steg för steg. Men innan vi dyker in i implementeringsdetaljerna, låt oss först se till att du har allt du behöver.
## Förutsättningar
Innan du börjar, se till att du har följande:
### 1. Aspose.Tasks för .NET
 Se till att du har installerat Aspose.Tasks för .NET-biblioteket. Om du inte redan har gjort det kan du ladda ner det från[Aspose.Tasks för .NET-webbplats](https://releases.aspose.com/tasks/net/).
### 2. Inloggningsuppgifter för SharePoint
Du behöver autentiseringsuppgifterna för att komma åt SharePoint där dina MS Project-filer lagras. Se till att du har följande information:
- SharePoint-domänadress
- Användarnamn
- Lösenord
## Importera namnområden
När du har fått ordning på dina förutsättningar är det dags att importera de nödvändiga namnrymden till ditt projekt.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Låt oss nu dela upp processen att extrahera MS Project-information i flera steg.
## Steg 1: Ange inloggningsuppgifter
Först måste du ange dina SharePoint-uppgifter för att få åtkomst till projektservern.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Steg 2: Initiera Project Server Manager
 Initiera sedan a`ProjectServerManager` instans med de angivna referenserna.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Steg 3: Hämta projektlista
Nu kan du hämta listan över projekt från projektservern.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Steg 4: Skriv ut projektinformation
Slutligen, iterera genom listan över projekt och skriv ut deras information.
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
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du extraherar MS Project-information med Aspose.Tasks för .NET. Med denna kunskap kan du nu integrera den här funktionen i dina .NET-applikationer sömlöst.
## FAQ's
### F1: Kan jag använda Aspose.Tasks för .NET med någon version av Microsoft Project?
S: Ja, Aspose.Tasks för .NET stöder olika versioner av Microsoft Project, inklusive 2003, 2007, 2010, 2013, 2016 och 2019.
### F2: Är Aspose.Tasks för .NET kompatibelt med både Windows- och Linux-plattformar?
S: Ja, Aspose.Tasks för .NET är kompatibel med både Windows- och Linux-plattformar, vilket gör den mångsidig för olika utvecklingsmiljöer.
### F3: Kan jag extrahera uppgiftsberoende med Aspose.Tasks för .NET?
A: Absolut! Aspose.Tasks för .NET ger robust funktionalitet för att extrahera inte bara grundläggande projektinformation utan även uppgiftsberoenden och andra intrikata detaljer.
### F4: Erbjuder Aspose.Tasks för .NET teknisk support?
 S: Ja, du kan få teknisk support för Aspose.Tasks för .NET genom[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), där du kan ställa frågor och söka hjälp från experter.
### F5: Kan jag prova Aspose.Tasks för .NET innan jag köper det?
 A: Visst! Du kan utnyttja en gratis provversion av Aspose.Tasks för .NET från[släpper sida](https://releases.aspose.com/), så att du kan utforska dess funktioner innan du fattar ett köpbeslut.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

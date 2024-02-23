---
title: Server Spara MS Project Alternativ för Aspose.Tasks
linktitle: Project Server Spara alternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du sparar Microsoft Project-alternativ för Aspose.Tasks med Project Server-integrering. Förbättra dina arbetsflöden för projektledning.
type: docs
weight: 16
url: /sv/net/saving-options/project-server-save-options/
---
## Introduktion
I den här handledningen kommer vi att fördjupa oss i att spara Microsoft Project-alternativ för Aspose.Tasks med Project Server. Aspose.Tasks är ett kraftfullt .NET API som låter utvecklare arbeta med Microsoft Project-filer programmatiskt. Med hjälp av Project Server-kapacitet kan vi sömlöst integrera Aspose.Tasks i våra projektledningsarbetsflöden. Denna handledning guidar dig genom processen steg för steg.
## Förutsättningar
Innan du börjar, se till att du har följande förutsättningar:
1.  Aspose.Tasks for .NET: Installera Aspose.Tasks for .NET från[nedladdningslänk](https://releases.aspose.com/tasks/net/).
   
2. Åtkomst till Project Server: Du behöver åtkomstuppgifter och URL:en till din Project Server-instans. Om du inte har en kan du få en gratis provperiod från[här](https://releases.aspose.com/).
3. Microsoft Project File: Förbered Microsoft Project-filen (.mpp) som du vill spara med Aspose.Tasks.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden i ditt projekt:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Steg 1: Initiera projekt och inloggningsuppgifter
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
 Se till att du byter ut`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,och`Password` med dina faktiska värden.
## Steg 2: Skapa Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Steg 3: Definiera sparalternativ
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Justera`ProjectGuid`, `ProjectName`, `Timeout` ,och`PollingInterval` enligt dina krav.
## Steg 4: Spara projektet på servern
```csharp
manager.CreateNewProject(project, options);
```
Detta kommer att spara projektet till projektservern med de angivna alternativen.

## Slutsats
I den här handledningen lärde vi oss hur man sparar Microsoft Project-alternativ för Aspose.Tasks med hjälp av Project Server-integration. Genom att följa dessa steg kan du sömlöst integrera Aspose.Tasks i dina projektledningsarbetsflöden, vilket ökar effektiviteten och produktiviteten.
## FAQ's
### F: Kan jag använda Aspose.Tasks med olika versioner av Microsoft Project?
S: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project, vilket säkerställer kompatibilitet mellan olika miljöer.
### F: Finns det en testversion tillgänglig för Aspose.Tasks?
 S: Ja, du kan få en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### F: Stöder Aspose.Tasks multi-threading?
S: Ja, Aspose.Tasks är designat för att vara trådsäkert, vilket tillåter samtidig åtkomst till projektdata.
### F: Kan jag anpassa sparalternativ när jag använder Project Server-integration?
S: Ja, du kan skräddarsy sparalternativ som projektnamn, timeout och pollingintervall för att passa dina krav.
### F: Var kan jag hitta support för Aspose.Tasks?
 S: Du kan hitta stöd och hjälp på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
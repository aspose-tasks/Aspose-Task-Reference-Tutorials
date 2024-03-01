---
title: Spara MS Project-filer som mallar med Aspose.Tasks
linktitle: Spara mallalternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du sparar Microsoft Project-filer som mallar med Aspose.Tasks för .NET. Anpassa mallinställningar för strömlinjeformad projekthantering.
type: docs
weight: 18
url: /sv/net/saving-options/save-template-options/
---
## Introduktion
den här handledningen kommer vi att gå igenom processen att spara en mall med Aspose.Tasks för .NET. Mallar är användbara för att standardisera projektstrukturer och inställningar för framtida användning. Vi kommer att visa hur man sparar ett projekt som en mall, och justerar dess egenskaper längs vägen.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Aspose.Tasks for .NET Library: Se till att du har Aspose.Tasks for .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
2. Kunskaper om C#-programmering: Grundläggande kunskaper i C#-programmering krävs för att förstå och implementera de medföljande kodavsnitten.
3. Microsoft Project File: Ha en Microsoft Project-fil (MPP-format) redo som du vill spara som en mall.

## Importera namnområden
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Steg 1: Ladda projekt
Först måste vi ladda Microsoft Project-filen (.mpp) som vi vill spara som en mall.
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Steg 2: Få information om projektfilen
Hämta information om den laddade projektfilen, till exempel dess format.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Steg 3: Konfigurera alternativ för Spara mall
Skapa mallsparalternativ och konfigurera dess egenskaper enligt dina krav. Dessa alternativ låter dig anpassa vilken data som ska tas bort från mallen.
```csharp
var options = new SaveTemplateOptions
{
	// Ta bort alla fasta kostnader från projektmallen
	RemoveFixedCosts = true,
	// Ta bort alla faktiska värden från projektmallen
	RemoveActualValues = true,
	// Ta bort resurssatser från projektmallen
	RemoveResourceRates = true,
	// Ta bort alla baslinjevärden från projektmallen
	RemoveBaselineValues = true
};
```
## Steg 4: Spara projekt som mall
Spara projektet som en mall med de angivna alternativen.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Steg 5: Få information om mallfil
Hämta information om den sparade mallfilen, till exempel dess format.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Grattis! Du har lyckats spara en mall med Aspose.Tasks för .NET, och anpassa dess egenskaper efter behov.

## Slutsats
I den här handledningen undersökte vi hur man sparar en Microsoft Project-fil som en mall med Aspose.Tasks för .NET. Mallar är värdefulla för att standardisera projektstrukturer och inställningar, för att effektivisera framtida projektskapelser.
## FAQ's
### F: Kan jag anpassa vilken data som ska tas bort från mallen?
S: Ja, du kan konfigurera Spara mallalternativ för att ta bort specifik data som fasta kostnader, faktiska värden, resurshastigheter och basvärden.
### F: Är Aspose.Tasks för .NET kompatibelt med alla versioner av Microsoft Project?
S: Aspose.Tasks för .NET ger omfattande kompatibilitet med olika versioner av Microsoft Project, vilket säkerställer sömlös integration och funktionalitet.
### F: Kan jag använda mallar på befintliga projekt?
S: Ja, du kan tillämpa mallar på befintliga projekt genom att ladda mallfilen och slå samman den med ditt nuvarande projekt efter behov.
### F: Stöder Aspose.Tasks för .NET utveckling över plattformar?
S: Aspose.Tasks för .NET är i första hand utformad för .NET framework-applikationer som körs på Windows-plattformar.
### F: Finns teknisk support tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan söka teknisk hjälp och vägledning från Aspose.Tasks-communityt[forum](https://forum.aspose.com/c/tasks/15)eller kontakta deras supportteam direkt.
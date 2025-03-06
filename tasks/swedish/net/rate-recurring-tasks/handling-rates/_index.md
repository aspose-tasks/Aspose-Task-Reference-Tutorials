---
title: Hantera MS-projektpriser med Aspose.Tasks för .NET
linktitle: Hantera priser i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master hantering av MS Project Rates med lätthet med Aspose.Tasks för .NET. Automatisera uppgifter effektivt för smidigare projektarbetsflöden.
type: docs
weight: 10
url: /sv/net/rate-recurring-tasks/handling-rates/
---
## Introduktion
Välkommen till vår handledning om hantering av MS Project Rates med Aspose.Tasks för .NET! I den här guiden går vi igenom processen steg för steg, och säkerställer att du effektivt kan hantera priser i dina MS Project-dokument. Aspose.Tasks för .NET tillhandahåller kraftfulla funktioner för att manipulera MS Project-filer programmatiskt, så att du enkelt kan effektivisera dina projektledningsuppgifter.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
1. Visual Studio installerad: Se till att du har Visual Studio installerat på ditt system.
2.  Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket. Du hittar nedladdningslänken[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#: Bekanta dig med C#-programmeringsspråkets grunder.
## Importera namnområden
Först måste du importera de nödvändiga namnrymden till ditt C#-projekt. Dessa namnrymder ger tillgång till de klasser och metoder som krävs för att hantera MS Project Rates.
## Steg 1: Importera Aspose.Tasks-namnutrymmet
```csharp
using Aspose.Tasks;
using System;

```
Låt oss nu dela upp exemplet i flera steg och förstå varje steg grundligt.
## Steg 1: Ladda projektfilen
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 I det här steget laddar vi en befintlig MS Project-fil med namnet "Project1.mpp" med hjälp av`Project` klass som tillhandahålls av Aspose.Tasks.
## Steg 2: Lägg till resurs och ställ in arbete
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Här lägger vi till en ny resurs som heter "Resurs 1" till projektet och ställer in dess typ som "Arbete". Vi definierar också arbetstiden för denna resurs.
## Steg 3: Ställ in standardpris
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
I det här steget ställer vi in standardpriset för resursen till 20 USD per timme.
## Steg 4: Definiera kursperioder
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Här definierar vi taxeperioderna för resursen. Rate1 är satt från 1 januari 2019 till 11 november 2019, med standard- och övertidstaxor specificerade.
## Steg 5: Lägg till ytterligare en prisperiod
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
I det här sista steget lägger vi till ytterligare en prisperiod från 12 november 2019 till 31 december 2019, med en annan standardpris och kostnad per användning definierad.
Grattis! Du har framgångsrikt hanterat MS Project Rates med Aspose.Tasks för .NET.
## Slutsats
Att hantera MS Project Rates programmatiskt kan avsevärt förbättra ditt projektledningsarbetsflöde. Med Aspose.Tasks för .NET har du kraften att automatisera uppgifterna för hastighetshantering effektivt, vilket sparar tid och resurser.
## FAQ's
### F: Kan Aspose.Tasks hantera komplexa projektstrukturer?
S: Ja, Aspose.Tasks tillhandahåller robusta funktioner för att enkelt hantera komplexa projektstrukturer.
### F: Är Aspose.Tasks kompatibel med alla versioner av MS Project-filer?
S: Aspose.Tasks stöder olika versioner av MS Project-filer, vilket säkerställer kompatibilitet mellan olika plattformar.
### F: Kan jag ändra befintliga priser i en MS Project-fil med Aspose.Tasks?
A: Absolut! Aspose.Tasks låter dig ändra befintliga priser, lägga till nya priser och hantera dem dynamiskt.
### F: Erbjuder Aspose.Tasks stöd för anpassade prisberäkningar?
S: Ja, du kan implementera anpassade prisberäkningar med Aspose.Tasks för att uppfylla specifika projektkrav.
### F: Finns det ett communityforum eller support tillgängligt för Aspose.Tasks-användare?
 A: Ja, du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)att söka hjälp och interagera med andra användare.
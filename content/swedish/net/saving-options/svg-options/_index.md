---
title: Enkel SVG-generering för Aspose.Tasks
linktitle: SVG-alternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du använder Aspose.Tasks för .NET för att generera SVG-representationer av Microsoft Project-filer utan ansträngning för förbättrad projektvisualisering.
type: docs
weight: 20
url: /sv/net/saving-options/svg-options/
---
## Introduktion
När det gäller projektledning och uppgiftsorganisation är förmågan att visualisera data effektivt av största vikt. Aspose.Tasks för .NET erbjuder en heltäckande lösning för att generera SVG-representationer av Microsoft Project-filer, vilket underlättar tydliga och engagerande projektinsikter. Denna handledning fördjupar sig i användningen av SVG MS Project-alternativ som tillhandahålls av Aspose.Tasks för .NET, vilket gör det möjligt för användare att utnyttja dess kraft för förbättrad projektvisualisering.
## Förutsättningar
Innan du börjar med denna handledning, se till att du har följande förutsättningar på plats:
1.  Installation av Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Ha en Microsoft Project-fil (MPP) redo för konvertering till SVG-format.
3. Utvecklingsmiljö: Skapa en utvecklingsmiljö med .NET-funktioner.

## Importera namnområden
Innan du dyker in i kodimplementeringen, se till att importera de nödvändiga namnrymden:
```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg 1: Definiera dokumentkatalogen
 Se till att du har en utsedd katalog för dina dokument. Byta ut`"Your Document Directory"` med sökvägen till din önskade katalog.
```csharp
String DataDir = "Your Document Directory";
```
## Steg 2: Ladda projektfilen
Ladda Microsoft Project-filen (.mpp) med hjälp av`Project` klass.
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Steg 3: Ange SVG-sparalternativ
Definiera SVG-sparalternativen inklusive presentationsformat, innehållsanpassning och tidsskala.
```csharp
SaveOptions options = new SvgOptions
{
    PresentationFormat = PresentationFormat.GanttChart,
    FitContent = true,
    Timescale = Timescale.ThirdsOfMonths
};
```
## Steg 4: Spara projektet som SVG
Spara projektet som en SVG-fil med de angivna alternativen.
```csharp
project.Save(DataDir + "UseSvgOptions_out.svg", options);
```

## Slutsats
Att bemästra SVG MS-projektalternativ med Aspose.Tasks för .NET ger projektledare och utvecklare möjlighet att skapa visuellt tilltalande representationer av sina projekt utan ansträngning. Genom att följa de skisserade stegen kan användare sömlöst integrera SVG-generering i sina projektledningsarbetsflöden, vilket förbättrar tydlighet och förståelse.
## FAQ's
### F: Kan Aspose.Tasks hantera stora Microsoft Project-filer?
S: Ja, Aspose.Tasks är designat för att hantera stora Microsoft Project-filer effektivt, vilket säkerställer optimal prestanda.

### F: Är Aspose.Tasks kompatibel med olika versioner av .NET?
S: Absolut, Aspose.Tasks stöder olika versioner av .NET, vilket ger flexibilitet och kompatibilitet över olika miljöer.

### F: Finns det några begränsningar för SVG-utmatningsalternativen?
S: Även om Aspose.Tasks erbjuder robusta SVG-utdataalternativ, kan vissa funktioner som gradientpenslar ha begränsningar. Se dokumentationen för detaljerad information.

### F: Kan jag anpassa utseendet på den genererade SVG?
S: Ja, Aspose.Tasks erbjuder omfattande anpassningsalternativ för att skräddarsy utseendet på SVG-utdata enligt dina preferenser och krav.

### F: Finns teknisk support tillgänglig för Aspose.Tasks-användare?
S: Ja, användare kan få tillgång till teknisk support via Aspose.Tasks-forumet eller genom att kontakta supportteamet direkt för hjälp med eventuella frågor eller problem.
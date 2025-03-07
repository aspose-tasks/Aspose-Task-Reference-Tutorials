---
title: Master MS Project Outline Masker med Aspose.Tasks
linktitle: Samling av konturmasker i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du manipulerar MS Projects samlingskonturmasker med Aspose.Tasks för .NET. Förbättra produktiviteten med denna omfattande handledning.
weight: 15
url: /sv/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master MS Project Outline Masker med Aspose.Tasks

## Introduktion
Vill du utnyttja kraften i Microsoft Projects konturmasker med Aspose.Tasks för .NET? Du har kommit till rätt ställe! I den här omfattande handledningen guidar vi dig genom processen steg för steg, så att du får en gedigen förståelse för hur du effektivt manipulerar konturmasker i dina projekt. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här guiden att utrusta dig med de kunskaper och färdigheter som behövs för att optimera ditt arbetsflöde.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande förutsättningar på plats:
### 1. Installation av Aspose.Tasks för .NET
Se till att du har Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Du kan ladda ner biblioteket från Asposes webbplats[här](https://releases.aspose.com/tasks/net/).
### 2. Grundläggande kunskaper i C# och .NET Framework
Bekanta dig med programmeringsspråket C# och .NET Framework, eftersom den här handledningen kommer att använda båda.
### 3. Microsoft Project File
Ha en Microsoft Project-fil (MPP) redo för teständamål. Du kan använda en befintlig fil eller skapa en ny för experiment.
## Importera namnområden
Låt oss börja med att importera de nödvändiga namnrymden till ditt C#-projekt. Detta steg säkerställer att du har tillgång till de obligatoriska klasserna och funktionerna som tillhandahålls av Aspose.Tasks för .NET.

Lägg till följande namnområden i början av din kodfil:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Låt oss nu dela upp exemplet i flera steg och förklara varje steg i detalj:
## Steg 1: Initiera projektobjektet
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Här skapar vi en ny instans av`Project` klass och ladda en befintlig Microsoft Project-fil med namnet "OutlineValues2010.mpp".
## Steg 2: Få åtkomst till dispositionskoder
```csharp
var outline = project.OutlineCodes[0];
```
Vi kommer åt dispositionskoderna från projektet. Dispositionskoder är anpassade fält i Microsoft Project som låter dig kategorisera och organisera uppgifter.
## Steg 3: Rensa konturmasker
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Detta steg säkerställer att alla befintliga konturmasker rensas innan du fortsätter.
## Steg 4: Skapa konturmasker
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Vi skapar nya konturmasker och specificerar deras typer. I det här exemplet skapar vi en giltig konturmask och en felaktig.
## Steg 5: Infoga och redigera masker
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Här infogar vi en fel mask i samlingen och redigerar längden på en mask med hjälp av dess index.
## Steg 6: Ta bort masker
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Vi tar bort fel mask från samlingen baserat på dess index.
## Steg 7: Iterera över masker
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Denna loop itererar över varje konturmask i samlingen och skriver ut dess egenskaper som längd, nivå, separator och typ.
## Steg 8: Kopiera masker till ett annat projekt
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Slutligen kopierar vi konturmaskerna från ett projekt till ett annat, vilket säkerställer konsistens mellan olika projekt.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man manipulerar MS Projects samlingskonturmasker med Aspose.Tasks för .NET. Genom att följa den här handledningen är du nu utrustad med färdigheter för att effektivt hantera konturmasker i dina projekt, vilket i slutändan förbättrar din produktivitet och arbetsflöde.
## FAQ's
### F1: Kan jag använda Aspose.Tasks för .NET med olika versioner av Microsoft Project-filer?
S: Ja, Aspose.Tasks för .NET stöder olika versioner av Microsoft Project-filer, inklusive MPP-, MPT- och XML-format.
### F2: Är Aspose.Tasks för .NET kompatibelt med .NET Core?
S: Ja, Aspose.Tasks för .NET är kompatibelt med .NET Core, vilket gör att du kan använda det i plattformsoberoende applikationer.
### F3: Kan jag anpassa egenskaperna för konturmasker enligt mina projektkrav?
A: Absolut! Du kan anpassa konturmasker genom att justera deras längd, nivå, avgränsare och typ för att passa dina specifika projektbehov.
### F4: Tillhandahåller Aspose.Tasks för .NET dokumentation och support?
S: Ja, Aspose.Tasks för .NET erbjuder omfattande dokumentation och dedikerad support via deras webbplats och[forum](https://forum.aspose.com/c/tasks/15).
### F5: Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan få tillgång till en gratis testversion av Aspose.Tasks för .NET från deras[hemsida](https://releases.aspose.com/tasks/net/). att utforska dess funktioner och funktioner innan du gör ett köp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

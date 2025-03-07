---
title: Bemästra MS Project Outline Values med Aspose.Tasks
linktitle: Hantera dispositionsvärden i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar MS Projects dispositionsvärden effektivt med Aspose.Tasks för .NET. Anpassa projektkonturer med lätthet.
weight: 16
url: /sv/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra MS Project Outline Values med Aspose.Tasks

## Introduktion
I den här självstudien kommer vi att utforska hur man hanterar Microsoft Project-konturvärden med Aspose.Tasks-biblioteket för .NET. Med Aspose.Tasks kan du enkelt manipulera dispositionskoder, skapa nya dispositionsvärden och anpassa projektkonturer efter dina krav.
## Förutsättningar
Innan du börjar, se till att du har följande:
1.  Installation av Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Se till att du har en utvecklingsmiljö inställd, som Visual Studio, med .NET framework-kompatibilitet.
3. Grundläggande förståelse för C#-programmering: Bekanta dig med C#-programmeringsspråkets grunder, eftersom vi kommer att använda C# för att arbeta med Aspose.Tasks-biblioteket.

## Importera namnområden
Börja med att importera de nödvändiga namnrymden till din C#-kod:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Steg 1: Ladda projektfilen
```csharp
// Sökvägen till dokumentkatalogen.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Det här steget initierar ett nytt projektobjekt och laddar Microsoft Project-filen från den angivna katalogen.
## Steg 2: Definiera dispositionskoddefinitioner
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Här definierar vi två OutlineCodeDefinition-objekt och lägger till dem i projektets OutlineCodes-samling.
## Steg 3: Definiera konturmask
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Detta steg skapar en OutlineMask för dispositionskoddefinitionen.
## Steg 4: Skapa dispositionsvärden
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
I det här steget skapar vi två OutlineValue-objekt och ställer in deras egenskaper som värde, värde-ID, typ, beskrivning och kollapsstatus.

## Slutsats
Att hantera MS Project-konturvärden med Aspose.Tasks för .NET är enkelt med de medföljande funktionerna. Genom att följa stegen som beskrivs i denna handledning kan du effektivt manipulera dispositionskoder och värden för att anpassa projektkonturer efter dina behov.
## FAQ's
### F: Kan jag använda Aspose.Tasks med andra .NET-ramverk?
S: Ja, Aspose.Tasks är kompatibelt med olika .NET-ramverk, vilket säkerställer flexibilitet i din utvecklingsmiljö.
### F: Finns det en testversion tillgänglig för Aspose.Tasks?
 S: Ja, du kan få tillgång till en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### F: Hur kan jag få support för Aspose.Tasks?
 S: För support och hjälp kan du besöka Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).
### F: Kan jag köpa en tillfällig licens för Aspose.Tasks?
S: Ja, du kan köpa en tillfällig licens för Aspose.Tasks från[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?
 S: Du kan hänvisa till den omfattande dokumentationen som finns tillgänglig[här](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

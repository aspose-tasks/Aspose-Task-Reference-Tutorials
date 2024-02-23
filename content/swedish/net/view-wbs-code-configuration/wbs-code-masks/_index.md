---
title: Steg-för-steg WBS-kodkonfiguration i Aspose.Tasks .NET
linktitle: Konfigurera WBS-kodmasker i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska steg-för-steg WBS Code Masks-konfiguration i .NET-projekt med Aspose.Tasks. Förbättra projektledningskapaciteten utan ansträngning.
type: docs
weight: 14
url: /sv/net/view-wbs-code-configuration/wbs-code-masks/
---
## Introduktion
Aspose.Tasks för .NET är ett kraftfullt bibliotek som ger utvecklare möjlighet att effektivt manipulera projektledningsdata i .NET-applikationer. I den här handledningen kommer vi att utforska processen att konfigurera Work Breakdown Structure (WBS) Code Masks med Aspose.Tasks.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Tasks för .NET Library: Ladda ner och installera biblioteket från[Aspose.Tasks för .NET-dokumentation](https://reference.aspose.com/tasks/net/).
- Utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö inställd.
- Dokumentkatalog: Välj en katalog på ditt system för att lagra projektfilerna.
## Importera namnområden
I ditt .NET-projekt, inkludera de nödvändiga namnrymden för att arbeta med Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Steg 1: Skapa en projektinstans
Börja med att skapa en ny projektinstans:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Steg 2: Definiera WBS-koddefinition
Ställ in WBS Code Definition för ditt projekt:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Steg 3: Lägg till WBS-kodmasker
Definiera WBS-kodmasker och lägg till dem i projektet:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Steg 4: Skapa uppgifter
Lägg till uppgifter till projektet:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Steg 5: Beräkna om
Beräkna om projektet för att säkerställa att WBS-koder tillämpas korrekt:
```csharp
project.Recalculate();
```
## Steg 6: Visa WBS-maskinformation
Mata ut information om WBS-masker till konsolen:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Steg 7: Spara projektet
Spara projektet med de tillagda WBS-koderna:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Grattis! Du har framgångsrikt konfigurerat WBS Code Masks i ditt Aspose.Tasks-projekt.
## Slutsats
I den här handledningen har vi utforskat processen steg-för-steg för att konfigurera WBS-kodmasker med Aspose.Tasks för .NET. Detta kraftfulla bibliotek ger utvecklare ett sömlöst sätt att förbättra projektledningskapaciteten i sina .NET-applikationer.

## FAQ's
### Kan jag använda Aspose.Tasks gratis?
 Aspose.Tasks erbjuder en gratis testversion som du kan ladda ner[här](https://releases.aspose.com/).
### Var kan jag hitta ytterligare support?
 besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)för samhällsstöd.
### Hur kan jag få en tillfällig licens?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Finns det detaljerad dokumentation tillgänglig?
 Ja, den omfattande dokumentationen finns tillgänglig[här](https://reference.aspose.com/tasks/net/).
### Var kan jag köpa Aspose.Tasks?
 Köp Aspose.Tasks[här](https://purchase.aspose.com/buy).
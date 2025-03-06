---
title: Samla MS Project of Split Parts i Aspose.Tasks
linktitle: Samling av delade delar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du samlar delade delar i MS Project med Aspose.Tasks för .NET. Denna omfattande handledning guidar dig genom processen steg för steg.
weight: 19
url: /sv/net/rate-recurring-tasks/split-part-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Samla MS Project of Split Parts i Aspose.Tasks

## Introduktion
I den här handledningen kommer vi att fördjupa oss i hur man samlar in delade delar i MS Project med Aspose.Tasks för .NET. Att dela upp uppgifter i delar kan vara en avgörande aspekt av projektledning, och Aspose.Tasks tillhandahåller praktiska metoder för att hantera detta effektivt.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Installation av Aspose.Tasks för .NET: Se till att du har installerat Aspose.Tasks för .NET. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
2. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt eftersom vi kommer att skriva kodavsnitt i C#.

## Importera namnområden
Inkludera de nödvändiga namnrymden i ditt C#-projekt:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Steg 1: Konfigurera ditt projekt
Skapa först ett nytt projekt i din föredragna IDE och se till att Aspose.Tasks för .NET refereras korrekt.
## Steg 2: Initiera projektobjektet
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Initiera ett nytt projektobjekt med sökvägen till din MS Project-fil.
## Steg 3: Hämta uppgift och iterera över delade delar
```csharp
var task = project.RootTask.Children.GetById(1);
// Iterera över delade delar
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Hämta uppgiften från projektet och iterera över dess delade delar, skriv ut deras start- och slutdatum.
## Steg 4: Få delad del efter index
```csharp
// Få delen efter index
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Hämta en specifik delad del efter index och skriv ut dess startdatum.

## Slutsats
Att hantera delade delar i MS Project-filer kan avsevärt förbättra effektiviteten i projekthanteringen. Aspose.Tasks för .NET förenklar denna process genom att tillhandahålla intuitiva API:er för att hantera delade uppgifter sömlöst.
## FAQ's
### F: Kan jag dela uppgifter dynamiskt under körning?
S: Ja, du kan dela uppgifter programmatiskt med Aspose.Tasks för .NET.
### F: Stöder Aspose.Tasks alla versioner av MS Project-filer?
S: Aspose.Tasks stöder olika versioner av MS Project-filer, vilket säkerställer kompatibilitet mellan olika plattformar.
### F: Finns det en testversion tillgänglig för teständamål?
 S: Ja, du kan få en gratis testversion från[här](https://releases.aspose.com/) för utvärdering.
### F: Hur kan jag få tillfälliga licenser för mina projekt?
 S: Tillfälliga licenser kan förvärvas från[här](https://purchase.aspose.com/temporary-license/) för kortvarig användning.
### F: Var kan jag söka hjälp eller stöd angående Aspose.Tasks?
 S: Du kan besöka Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15)att söka hjälp från samhället eller Asposes supportteam.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

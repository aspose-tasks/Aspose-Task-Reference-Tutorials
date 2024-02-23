---
title: Extrahera sidhuvuds- och sidfotsinformation med Aspose.Tasks
linktitle: Information om sidhuvud och sidfot i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig att extrahera sidhuvuds- och sidfotsinformation från MS Project-filer med Aspose.Tasks för .NET. Enkel, effektiv och utvecklarvänlig lösning.
type: docs
weight: 29
url: /sv/net/tasks-project-management/header-footer-information/
---
## Introduktion
Aspose.Tasks för .NET är ett kraftfullt bibliotek som tillåter utvecklare att manipulera Microsoft Project-filer med lätthet. I den här handledningen kommer vi att lära oss hur du hämtar sidhuvuds- och sidfotsinformation från MS Project-filer med Aspose.Tasks.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Visual Studio: Installera Visual Studio på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C#.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden till ditt C#-projekt. Detta ger dig tillgång till klasserna och metoderna som tillhandahålls av Aspose.Tasks-biblioteket.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Steg 1: Initiera projektobjekt
 För att börja måste du initiera a`Project` objekt genom att ladda en befintlig MS Project-fil.
```csharp
// Sökvägen till dokumentkatalogen.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Steg 2: Hämta sidhuvuds- och sidfotsinformation
 När du har laddat projektfilen kan du hämta sidhuvuds- och sidfotsinformationen med hjälp av`PageInfo` fast egendom.
```csharp
var info = project.DefaultView.PageInfo;
// Header Information
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Sidfotsinformation
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Genom att följa dessa enkla steg kan du enkelt hämta sidhuvuds- och sidfotsinformation från MS Project-filer med Aspose.Tasks för .NET.

## Slutsats
den här handledningen undersökte vi hur man extraherar sidhuvuds- och sidfotsinformation från MS Project-filer med Aspose.Tasks för .NET. Detta kraftfulla bibliotek förenklar uppgiften att arbeta med projektfiler i C#-applikationer, vilket ger utvecklare robusta verktyg för manipulation.
### Vanliga frågor
### Kan jag ändra sidhuvud och sidfotsinformation med Aspose.Tasks?
Ja, du kan ändra sidhuvuds- och sidfotsinformationen programmatiskt med Aspose.Tasks för .NET.
### Stöder Aspose.Tasks andra projektfilformat förutom MS Project?
Ja, Aspose.Tasks stöder olika projektfilformat, inklusive MPP, XML och MPX.
### Finns det en gratis testversion tillgänglig för Aspose.Tasks?
 Ja, du kan ladda ner en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentation för Aspose.Tasks?
 Du hittar dokumentationen för Aspose.Tasks[här](https://reference.aspose.com/tasks/net/).
### Hur kan jag få support för Aspose.Tasks?
 Du kan få support för Aspose.Tasks genom att besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
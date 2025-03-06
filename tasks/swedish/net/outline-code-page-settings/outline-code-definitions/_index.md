---
title: MS Project Outline Kodhantering Definitioner i Aspose.Tasks
linktitle: Hantera dispositionskoddefinitioner i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar MS Project-konturkoddefinitioner med Aspose.Tasks för .NET, vilket ger dina projektledningsapplikationer kraft.
type: docs
weight: 12
url: /sv/net/outline-code-page-settings/outline-code-definitions/
---
## Introduktion
Microsoft Project är ett kraftfullt verktyg för att hantera projekt, och Aspose.Tasks för .NET ger omfattande stöd för att manipulera projektfiler programmatiskt. En viktig aspekt av projektledning är att organisera uppgifter med hjälp av dispositionskoder. I den här handledningen kommer vi att undersöka hur man hanterar MS Project-konturkoddefinitioner med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi dyker in i implementeringen, se till att du har följande förutsättningar:
### 1. Installation av Aspose.Tasks för .NET
 Se till att du har installerat Aspose.Tasks för .NET i din utvecklingsmiljö. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
### 2. Grundläggande förståelse för C# och .NET Framework
Bekanta dig med programmeringsspråket C# och .NET-ramverket eftersom denna handledning kräver C#-kunskaper på medelnivå.
### 3. Integrated Development Environment (IDE)
Ha en IDE som Visual Studio installerad på ditt system för kodning och felsökning.
## Importera namnområden
Innan vi börjar koda, låt oss importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks för .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Låt oss nu dela upp exemplet i flera steg för en tydlig förståelse.
## Steg 1: Ladda projektfilen
Först måste vi ladda MS Project-filen i vår applikation.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Steg 2: Skapa dispositionskoddefinition
Låt oss nu skapa en ny dispositionskoddefinition.
```csharp
var outline = new OutlineCodeDefinition();
```
## Steg 3: Ställ in fältnummer och namn
Ställ in fältnummer och namn för dispositionskoden.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Steg 4: Ställ in GUID och andra egenskaper
Ställ in GUID och andra egenskaper för dispositionskoden.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Steg 5: Lägg till konturmask
Lägg till en dispositionsmask till dispositionskoden.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Steg 6: Ställ in andra egenskaper
Ställ in ytterligare egenskaper för dispositionskoden.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Steg 7: Lägg till dispositionsvärde
Slutligen, låt oss lägga till ett dispositionsvärde till dispositionskoden.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Slutsats
I den här handledningen har vi lärt oss hur man hanterar MS Project-konturkoddefinitioner med Aspose.Tasks för .NET. Genom att följa den steg-för-steg-guiden kan du effektivt manipulera dispositionskoder i dina projektfiler programmatiskt.
## FAQ's
### F1: Kan jag använda Aspose.Tasks för .NET med olika versioner av MS Project-filer?
S: Ja, Aspose.Tasks för .NET stöder olika versioner av MS Project-filer, inklusive MPP- och XML-format.
### F2: Är Aspose.Tasks för .NET kompatibelt med .NET Core?
S: Ja, Aspose.Tasks för .NET är kompatibelt med .NET Core, vilket gör att du kan utveckla plattformsoberoende applikationer.
### F3: Kan jag manipulera resurstilldelningar med Aspose.Tasks för .NET?
S: Ja, Aspose.Tasks för .NET tillhandahåller omfattande funktioner för att manipulera resurstilldelningar, inklusive att lägga till, uppdatera och ta bort tilldelningar.
### F4: Stöder Aspose.Tasks för .NET läsning av anpassade fält från MS Project-filer?
S: Absolut, Aspose.Tasks för .NET stöder läsning och skrivning av anpassade fält, inklusive dispositionskoder, från MS Project-filer.
### F5: Finns det ett communityforum för Aspose.Tasks för .NET?
 S: Ja, du kan gå med i communityforumet för Aspose.Tasks för .NET[här](https://forum.aspose.com/c/tasks/15) att ställa frågor, dela kunskap och samarbeta med andra utvecklare.
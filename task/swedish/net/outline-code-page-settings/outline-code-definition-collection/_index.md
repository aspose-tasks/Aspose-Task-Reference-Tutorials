---
title: Samling av dispositionskoddefinitioner i Aspose.Tasks .NET
linktitle: Samling av dispositionskoddefinitioner i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du manipulerar dispositionskoddefinitioner i Microsoft Project-dokument med Aspose.Tasks för .NET. Kategorisering av dina projektdata utan ansträngning.
type: docs
weight: 13
url: /sv/net/outline-code-page-settings/outline-code-definition-collection/
---
## Introduktion
Aspose.Tasks är ett kraftfullt .NET-bibliotek utformat för att manipulera Microsoft Project-dokument med lätthet och effektivitet. En av dess nyckelfunktioner är förmågan att arbeta med konturkoddefinitioner, vilket gör det möjligt för användare att organisera och kategorisera projektdata effektivt. I den här självstudien kommer vi att utforska hur man arbetar med konturkoddefinitioner med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande:
1. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.
2. Visual Studio: Installera Visual Studio eller någon annan föredragen C#-utvecklingsmiljö.
3.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).

## Importera namnområden
För att börja, se till att importera de nödvändiga namnrymden:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Steg 1: Ladda ett Microsoft Project Document
Ladda först ett Microsoft Project-dokument för att börja arbeta med dispositionskoddefinitioner:
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Steg 2: Åtkomst till dispositionskoddefinitioner
Låt oss nu komma åt dispositionskoddefinitionerna inom projektet:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Steg 3: Lägg till anpassade dispositionskoddefinitioner
Du kan lägga till anpassade dispositionskoddefinitioner enligt följande:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Steg 4: Ändra dispositionskoddefinitioner
Ändra befintliga dispositionskoddefinitioner enkelt:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Steg 5: Ta bort dispositionskoddefinitioner
Ta bort dispositionskoddefinitioner när de inte längre behövs:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Steg 6: Spara ändringar
Slutligen, spara dina ändringar i projektdokumentet:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Slutsats
Sammanfattningsvis ger Aspose.Tasks för .NET omfattande funktionalitet för att hantera dispositionskoddefinitioner i Microsoft Project-dokument. Genom att följa stegen som beskrivs i denna handledning kan du effektivt manipulera dispositionskoddefinitioner för att organisera och kategorisera dina projektdata effektivt.
## FAQ's
### F: Kan jag lägga till flera dispositionskoddefinitioner till ett enda projekt?
 S: Ja, du kan lägga till flera dispositionskoddefinitioner till ett projekt baserat på dina krav. Använd helt enkelt`Add` metod för varje definition du vill inkludera.
### F: Är det möjligt att ta bort alla dispositionskoddefinitioner från ett projekt på en gång?
 S: Ja, du kan rensa alla dispositionskoddefinitioner från ett projekt med hjälp av`Clear` metod.
### F: Vad händer om jag försöker ändra en skrivskyddad dispositionskoddefinition?
S: Om en dispositionskoddefinition är skrivskyddad kommer du inte att kunna ändra den direkt. Du måste kontrollera dess skrivskyddade status innan du försöker göra några ändringar.
### F: Finns det några begränsningar för antalet dispositionskoddefinitioner jag kan lägga till i ett projekt?
S: Aspose.Tasks för .NET lägger inga specifika begränsningar på antalet dispositionskoddefinitioner som du kan lägga till i ett projekt. Tänk dock på prestationskonsekvenserna när du arbetar med ett stort antal definitioner.
### F: Kan jag använda dispositionskoddefinitioner för att gruppera uppgifter baserat på anpassade kriterier?
S: Ja, definitioner av dispositionskod låter dig kategorisera uppgifter baserat på anpassade kriterier, vilket ger flexibilitet vid organisering av projektdata.## Komplett källkod
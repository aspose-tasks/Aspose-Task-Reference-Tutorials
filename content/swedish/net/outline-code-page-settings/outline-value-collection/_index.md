---
title: Hantera MS Project Outline-värden med Aspose.Tasks
linktitle: Samling av dispositionsvärden i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar dispositionsvärden i Microsoft Project-filer med Aspose.Tasks för .NET. Steg-för-steg handledning med kodexempel.
type: docs
weight: 17
url: /sv/net/outline-code-page-settings/outline-value-collection/
---
## Introduktion
Aspose.Tasks för .NET tillhandahåller en omfattande uppsättning funktioner för att interagera med Microsoft Project-filer. En sådan funktion är möjligheten att hantera konturvärden inom ett projekt. I den här handledningen kommer vi att utforska hur man samlar in och manipulerar konturvärden med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Aspose.Tasks för .NET: Du kan ladda ner biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Se till att du har en lämplig IDE installerad, till exempel Visual Studio.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.
## Importera namnområden
Importera de nödvändiga namnområdena i din C#-kodfil för att komma åt klasser och metoder i Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Låt oss dela upp exemplet i flera steg:
## Steg 1: Ladda en projektfil
 Initiera först a`Project` objekt genom att ladda en befintlig Microsoft Project-fil:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Steg 2: Rensa befintliga dispositionsvärden
Rensa sedan alla befintliga dispositionsvärden från projektet:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Steg 3: Definiera ny dispositionskod
Definiera nu en ny dispositionskod med en beskrivning och ett värde:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Steg 4: Uppdatera dispositionsvärde
Uppdatera värdet på dispositionskoden:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Steg 5: Iterera över dispositionsvärden
Iterera genom dispositionsvärdena och skriv ut deras detaljer:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Steg 6: Manipulera dispositionsvärden
Utför åtgärder som att ta bort, infoga och kopiera konturvärden efter behov:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Slutsats
den här handledningen lärde vi oss hur man arbetar med konturvärden i Microsoft Project-filer med Aspose.Tasks för .NET. Genom att följa de angivna stegen kan du effektivt hantera översiktsvärden inom dina projekt, vilket möjliggör större kontroll och flexibilitet.
## FAQ's
### F: Kan jag manipulera flera dispositionskoder samtidigt?
S: Ja, du kan definiera och manipulera flera dispositionskoder inom ett projekt med Aspose.Tasks.
### F: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project-filer?
S: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project-filer, inklusive MPP- och XML-format.
### F: Hur kan jag hantera fel när jag arbetar med konturvärden?
S: Du kan implementera felhanteringsmekanismer som try-catch-block för att hantera undantag elegant.
### F: Kan jag anpassa utseendet på konturvärden i mitt projekt?
S: Ja, Aspose.Tasks tillhandahåller omfattande API:er för att anpassa utseendet och beteendet hos konturvärdena enligt dina krav.
### F: Var kan jag hitta ytterligare resurser och support för Aspose.Tasks?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och utforska[dokumentation](https://reference.aspose.com/tasks/net/) för detaljerad information om API:er och funktioner.
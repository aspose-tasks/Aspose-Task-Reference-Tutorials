---
title: Master Extended Attribute Definitions MS Project i Aspose.Tasks
linktitle: Samling av utökade attributdefinitioner i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar utökade attributdefinitioner i Microsoft Project med Aspose.Tasks för .NET. Anpassa och förbättra dina projektdata utan ansträngning.
type: docs
weight: 14
url: /sv/net/tasks-project-management/extended-attribute-definition-collection/
---
## Introduktion
I den här handledningen kommer vi att utforska hur man arbetar med utökade attributdefinitioner i Microsoft Project med Aspose.Tasks för .NET. Utökade attribut erbjuder ett flexibelt sätt att anpassa och förbättra projektdata, vilket gör att användare kan lägga till ytterligare fält utöver de standard som tillhandahålls som standard. Med Aspose.Tasks kan du enkelt hantera dessa utökade attribut för att skräddarsy dina projektledningsbehov.
## Förutsättningar
Innan du fortsätter, se till att du har följande förutsättningar installerade:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks för .NET-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).

## Importera namnområden
Först måste du importera de nödvändiga namnrymden för att komma åt Aspose.Tasks-klasser och metoder i ditt .NET-projekt. Följ dessa steg:
## Steg 1: Öppna ditt .NET-projekt
Öppna ditt .NET-projekt i din föredragna IDE, till exempel Visual Studio.
## Steg 2: Lägg till namnområdet Aspose.Tasks
Lägg till följande rad i början av din kodfil för att importera Aspose.Tasks-namnrymden:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Låt oss nu dela upp de medföljande kodexemplen i flera steg för en heltäckande förståelse:
## Steg 1: Ladda projektfilen
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Steg 2: Rensa befintliga utökade attributdefinitioner (valfritt)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Steg 3: Skapa och lägg till utökad attributdefinition för en uppgift
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Steg 4: Iterera över uppgiftsutvidgade attribut
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Steg 5: Skapa och lägg till utökad attributdefinition för en resurs
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Steg 6: Infoga en resursutvidgad attributdefinition
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Steg 7: Ta bort ett utökat attribut efter index
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Slutsats
den här handledningen har vi täckt grunderna för att arbeta med utökade attributdefinitioner i Microsoft Project med Aspose.Tasks för .NET. Genom att följa dessa steg kan du effektivt hantera och anpassa utökade attribut för att passa dina projektledningskrav.
## FAQ's
### F: Kan jag ändra befintliga utökade attributdefinitioner?
S: Ja, du kan ändra befintliga utökade attributdefinitioner eller skapa nya enligt dina behov.
### F: Stöds utökade attribut i alla versioner av Microsoft Project?
S: Ja, utökade attribut stöds i de flesta versioner av Microsoft Project, inklusive de senaste.
### F: Kan jag använda utökade attribut för att beräkna anpassade fält?
S: Absolut, utökade attribut kan användas för att beräkna anpassade fält baserat på specifika kriterier som du definierar.
### F: Är Aspose.Tasks kompatibelt med andra .NET-ramverk?
S: Aspose.Tasks är kompatibelt med olika .NET-ramverk, vilket säkerställer flexibilitet och enkel integration.
### F: Var kan jag hitta fler resurser och support för Aspose.Tasks?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för stöd och utforska dokumentationen[här](https://reference.aspose.com/tasks/net/).
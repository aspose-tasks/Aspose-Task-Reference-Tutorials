---
title: Hantera MS Project Attributes Collection i Aspose.Tasks
linktitle: Hantera utökad attributsamling i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du effektivt hanterar MS Project utökade attribut med Aspose.Tasks för .NET. Manipulera sömlöst uppgiftsattribut med steg-för-steg-vägledning.
weight: 12
url: /sv/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera MS Project Attributes Collection i Aspose.Tasks

## Introduktion
Är du ute efter att effektivt hantera MS Project utökade attribut med Aspose.Tasks för .NET? I den här handledningen guidar vi dig genom processen steg för steg. Låt oss dyka in!
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Visual Studio: Installera Visual Studio på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande kunskaper i C#: Bekanta dig med grunderna i programmeringsspråket i C#.

## Importera namnområden
Börja med att importera de nödvändiga namnrymden till ditt projekt:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Steg 1: Ladda projektfilen
Ladda först MS Project-filen med följande kodavsnitt:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Steg 2: Åtkomstuppgift och utökade attribut
Få åtkomst till en specifik uppgift och dess utökade attribut:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Steg 3: Rensa utökade attribut
Rensa befintliga utökade attribut om det behövs:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Steg 4: Skapa utökade attributdefinitioner
Skapa definitioner för nya utökade attribut:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Steg 5: Iterera över Task Extended Attributes
Iterera över uppgiftsutvidgade attribut:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Steg 6: Lägg till utökade attribut
Lägg till nya utökade attribut till uppgiften:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Steg 7: Arbeta med utökade attribut
Utför åtgärder på utökade attribut efter behov.
## Steg 8: Ta bort utökade attribut
Ta bort utökade attribut efter index eller villkorligt:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Steg 9: Kopiera attribut till en annan uppgift
Kopiera attribut till en annan uppgift inom samma eller ett annat projekt:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Slutsats
Att hantera MS Project utökade attributsamlingar blir sömlöst med Aspose.Tasks för .NET. Genom att följa stegen som beskrivs i denna handledning kan du effektivt hantera utökade attribut, vilket förbättrar dina projektledningsmöjligheter.
## FAQ's
### F: Kan jag manipulera utökade attribut över flera projekt?
S: Ja, du kan kopiera utökade attribut mellan uppgifter i olika projekt med Aspose.Tasks för .NET.
### F: Finns det begränsningar för antalet utökade attribut per uppgift?
S: Aspose.Tasks för .NET lägger inga inneboende begränsningar på antalet utökade attribut per uppgift.
### F: Kan jag skapa anpassade utökade attributfält?
A: Absolut! Aspose.Tasks för .NET låter dig definiera anpassade utökade attributfält skräddarsydda för dina projektkrav.
### F: Stöder Aspose.Tasks för .NET läsning och skrivning till MS Project-filer av olika versioner?
S: Ja, Aspose.Tasks för .NET stöder MS Project-filformat i olika versioner.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

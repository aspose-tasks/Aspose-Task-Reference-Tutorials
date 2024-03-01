---
title: Samling av resurstilldelningar i Aspose.Tasks
linktitle: Samling av resurstilldelningar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar resurstilldelningar i Microsoft Project med Aspose.Tasks för .NET. Steg-för-steg handledning med kodexempel.
type: docs
weight: 12
url: /sv/net/resource-risk-analysis/resource-assignment-collection/
---
## Introduktion
Välkommen till denna omfattande handledning om hantering av resurstilldelningar i Microsoft Project med Aspose.Tasks för .NET. I den här handledningen kommer vi att fördjupa oss i processen steg för steg, för att säkerställa att du har en gedigen förståelse för hur du manipulerar resurstilldelningar effektivt. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här guiden att gå igenom allt du behöver veta.
## Förutsättningar
Innan vi dyker in i koden, se till att du har följande inställning:
1.  Aspose.Tasks för .NET installerat: Se till att du har Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Om inte kan du ladda ner den från[här](https://releases.aspose.com/tasks/net/).
2. Grundläggande kunskaper om C#: Denna handledning förutsätter att du har en grundläggande förståelse för programmeringsspråket C#.
3. Microsoft Project File: Ha en Microsoft Project-fil redo för teständamål. Om du inte har en kan du skapa en exempelfil.

## Importera namnområden
Låt oss först importera de nödvändiga namnrymden:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Steg 1: Ladda projektfilen
Börja med att ladda Microsoft Project-filen:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Steg 2: Lägg till uppgift och resurs
Låt oss nu lägga till en uppgift och en resurs till projektet:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Steg 3: Tilldela resurs till uppgift
Därefter tilldelar vi resursen till uppgiften:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Steg 4: Arbeta med olika uppdragstyper
Du kan också arbeta med uppdrag som involverar enheter eller kostnader:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Ställ in egenskaper för uppdrag med enheter och kostnader på liknande sätt som visas i steg 3
```
## Steg 5: Skriv ut uppdrag
Skriv ut uppdragen för projektet:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Skriv ut uppgifter om uppdraget
}
```
## Steg 6: Hämta uppdrag med UID
Du kan hämta uppdrag med UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Steg 7: Kontrollera skrivskyddad status
Verifiera om resurstilldelningssamlingen är skrivskyddad:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Steg 8: Konvertera samling till lista och iterera
Konvertera samlingen till en lista och iterera över den:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Slutsats
Grattis! Du har lärt dig hur du hanterar resurstilldelningar i Microsoft Project med Aspose.Tasks för .NET. Genom att följa dessa steg kan du effektivt manipulera uppgifter och resurser, vilket gör projektledning till en bris.
## FAQ's
### F: Kan jag använda Aspose.Tasks för .NET med olika versioner av Microsoft Project-filer?
S: Ja, Aspose.Tasks för .NET stöder olika versioner av Microsoft Project-filer, inklusive MPP-, MPT- och XML-format.
### F: Finns det en testversion innan du köper Aspose.Tasks för .NET?
 S: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från[här](https://releases.aspose.com/).
### F: Hur kan jag få support om jag stöter på några problem när jag använder Aspose.Tasks för .NET?
 S: Du kan söka stöd från Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).
### F: Kan jag använda tillfälliga licenser för Aspose.Tasks för .NET?
 S: Ja, tillfälliga licenser är tillgängliga för utvärderingssyften. Du kan få en från[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag köpa en fullständig licens för Aspose.Tasks för .NET?
 S: Du kan köpa en fullständig licens från Asposes onlinebutik[här](https://purchase.aspose.com/buy).
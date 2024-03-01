---
title: Master Timephased Data Handling med Aspose.Tasks för .NET
linktitle: Hantering av tidsfasad data i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska Aspose.Tasks för .NET för att enkelt hantera tidsfasdata, förbättra projektplaneringen och optimera resurshanteringen. #Aspose #Tasks #MS Project
type: docs
weight: 14
url: /sv/net/text-view-configuration/timephased-data/
---
## Introduktion
I en värld av projektledning är effektiv hantering av tidsfasad data avgörande för resursallokering, kostnadsuppskattning och övergripande projektplanering. Aspose.Tasks för .NET tillhandahåller en kraftfull lösning för att arbeta med anpassade tidsfasade data sömlöst. Denna handledning guidar dig genom processen att hantera tidsfasad data med Aspose.Tasks, så att du kan optimera resurshanteringen i dina projekt.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En grundläggande förståelse för projektledningskoncept.
-  Installerade Aspose.Tasks för .NET. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
- En kodredigerare, till exempel Visual Studio, för att implementera de medföljande exemplen.
## Importera namnområden
ditt .NET-projekt, se till att importera de nödvändiga namnområdena för att utnyttja Aspose.Tasks-funktionerna. Lägg till följande rader i början av din kodfil:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Låt oss nu dela upp exemplet i flera steg för att guida dig genom att hantera tidsfasdata med Aspose.Tasks:
## Steg 1: Konfigurera projektet
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Här initierar vi ett nytt projekt och ställer in dess beräkningsläge.
## Steg 2: Definiera resurser och uppgifter
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Skapa arbets- och kostnadsresurser, samt en uppgift, för att simulera en projektstruktur.
## Steg 3: Tilldela resurser till uppgift
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Tilldela arbets- och kostnadsresurser till uppgiften.
## Steg 4: Lägg till anpassade tidsfasade data
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Liknande steg för kostnadstilldelning
costAssignment.TimephasedData.Clear();
```
Lägg till anpassade tidsfasdata för både arbets- och kostnadsuppdrag.
## Steg 5: Visa tidsfasdata
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Visa relevant information om varje tidsfasad datainmatning
    }
}
```
Slutligen, visa tidsfasdata för varje uppdrag.
#
## Slutsats
Effektiv hantering av tidsfasad data i Aspose.Tasks öppnar nya möjligheter för detaljerad projektplanering och resurshantering. Genom att följa den här steg-för-steg-guiden har du lärt dig hur du manipulerar tidsfasdata för att möta dina projekts specifika behov.
## Vanliga frågor
### Kan jag använda Aspose.Tasks för .NET med andra projekthanteringsverktyg?
Aspose.Tasks är främst designat för .NET-utveckling. Dess funktioner kan dock komplettera olika projektledningsverktyg.
### Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?
 Ja, du kan utforska en gratis provperiod[här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Tasks för .NET?
 Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd.
### Vad är en tillfällig licens och hur kan jag få en?
 Lär dig mer om tillfälliga licenser[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta dokumentationen för Aspose.Tasks för .NET?
 Se den omfattande[dokumentation](https://reference.aspose.com/tasks/net/) för detaljerad information.
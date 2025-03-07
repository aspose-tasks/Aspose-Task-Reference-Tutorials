---
title: Bemästra tidsfasad datainsamling i Aspose.Tasks
linktitle: Insamling av tidsfasad data i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska tidsfasad datainsamling i Aspose.Tasks för .NET. Steg-för-steg-guide, vanliga frågor och mer. Förbättra dina projektledningsförmåga idag!
weight: 15
url: /sv/net/text-view-configuration/timephased-data-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra tidsfasad datainsamling i Aspose.Tasks

## Introduktion
Vill du utnyttja kraften i tidsfasad data i dina .NET-applikationer med Aspose.Tasks? Kolla inte vidare! Denna omfattande guide kommer att leda dig genom processen att samla in tidsfasad data med Aspose.Tasks för .NET, vilket säkerställer att du får ut det mesta av detta kraftfulla bibliotek.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  Aspose.Tasks för .NET Library: Ladda ner och installera biblioteket från[Aspose.Tasks .NET-dokumentation](https://reference.aspose.com/tasks/net/).
2. .NET-utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö inställd.
3. Din dokumentkatalog: Ersätt platshållaren "Din dokumentkatalog" i kodavsnitten med sökvägen till din dokumentkatalog.
## Importera namnområden
I ditt .NET-projekt börjar du med att importera de nödvändiga namnrymden för att utnyttja Aspose.Tasks-funktionerna:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Skapa ett projekt och resurser
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Lägg till uppgifter i projektet
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Ställ in uppgiftsegenskaper...
var task2 = project.RootTask.Children.Add("Task 2");
// Ställ in egenskaper för uppgift 2...
```
## 3. Tilldela resurser till uppgifter
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Ange tilldelningsegenskaper...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//Ange egenskaper för uppdrag 2...
```
## 4. Arbeta med tidsfasad data
```csharp
// Ställ in konturerad arbetskontur
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Kontrollera om tidsfasinsamling av data är skrivskyddad
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Rensa genererad tidsfasdata
assignment.TimephasedData.Clear();
// Skapa och lägg till tidsfasdata
var td = new TimephasedData
{
    // Ställ in tidsfasade dataegenskaper...
};
assignment.TimephasedData.Add(td);
// Lägg till en lista med tidsfasdata
var list = new List<TimephasedData>();
// Lägg till fler tidsinställda dataobjekt till listan...
assignment.TimephasedData.AddRange(list);
// Filtrera tidsfasdata efter typ och datumintervall
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Skriv ut filtrerad tidsfasdata...
```
## 5. Manipulera tidsfasdata
```csharp
// Lägg till en felaktig tidsinställd datapost och radera den sedan
var td4 = new TimephasedData
{
    // Ange fel tidsfasade dataegenskaper...
};
assignment.TimephasedData.Add(td4);
// Ta bort fel tidsfasdataobjekt
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Iterera över alla tidsfasade objekt
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Skriv ut tidsinställd artikelinformation...
}
```
## 6. Kopiera tidsfasdata till en annan uppgift
```csharp
// Kopiera tidsfasdata till en annan uppgift
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Konvertera samlingen till en vanlig lista
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Ta bort tidsinställda dataobjekt en efter en
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Slutsats
Sammanfattningsvis har denna handledning gett en detaljerad genomgång av insamling av tidsfasdata med Aspose.Tasks för .NET. Genom att följa dessa steg kan du sömlöst integrera denna funktion i dina projekt, vilket möjliggör effektiv tidsspårning och resurshantering.
## Vanliga frågor
### Kan jag använda Aspose.Tasks för .NET med andra projekthanteringsverktyg?
Ja, Aspose.Tasks för .NET är designat för att fungera med populära projekthanteringsverktyg och stöder olika filformat.
### Finns det en gräns för antalet resurser och uppgifter jag kan hantera med Aspose.Tasks?
Aspose.Tasks hanterar projekt av varierande storlek och det finns ingen strikt gräns för antalet resurser och uppgifter.
### Hur kan jag få support för eventuella problem eller frågor relaterade till Aspose.Tasks för .NET?
 För support, besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) att få kontakt med samhället och få hjälp.
### Kan jag prova Aspose.Tasks för .NET innan jag köper det?
 Ja, du kan utforska funktionerna i Aspose.Tasks för .NET genom att gå till[gratis provperiod](https://releases.aspose.com/).
### Var kan jag köpa en licens för Aspose.Tasks för .NET?
Du kan köpa en licens för Aspose.Tasks för .NET[här](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

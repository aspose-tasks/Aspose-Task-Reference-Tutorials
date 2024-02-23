---
title: Konfigurera MS Project XLSX-alternativ i Aspose.Tasks för .NET
linktitle: Konfigurera XLSX-alternativ i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du konfigurerar MS Project XLSX-alternativ i Aspose.Tasks för .NET. Anpassa kolumner, kodning och mer utan ansträngning.
type: docs
weight: 11
url: /sv/net/file-format-options/configuring-xlsx-options/
---
## Introduktion
Microsoft Project (MS Project) är ett kraftfullt verktyg för projektledning, och Aspose.Tasks för .NET ger sömlös integration för att arbeta med MS Project-filer programmatiskt. I den här handledningen går vi igenom processen att konfigurera MS Project XLSX-alternativ med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande:
### 1. Aspose.Tasks för .NET installerat
 Se till att du har Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Om inte kan du ladda ner den från[Aspose.Tasks för .NET nedladdningssida](https://releases.aspose.com/tasks/net/).
### 2. Grundläggande förståelse för C# och .NET Framework
Bekantskap med programmeringsspråket C# och .NET-ramverket krävs för att följa med i denna handledning.
### 3. Microsoft Project File
Ha en Microsoft Project-fil (MPP) redo som du vill konfigurera och spara som en XLSX-fil.

## Importera namnområden
För att börja, importera de nödvändiga namnrymden:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Steg 1: Ladda projektet
```csharp
var project = new Project("YourProjectFile.mpp");
```
Ladda Microsoft Project-filen du vill konfigurera.
## Steg 2: Definiera XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Skapa en instans av`XlsxOptions` för att konfigurera inställningar för att spara som XLSX.
## Steg 3: Lägg till Gantt-diagramkolumner
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Lägg till önskade Gantt-diagramkolumner till alternativen.
## Steg 4: Lägg till resursvykolumner
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Inkludera önskade kolumner för resursvyn i alternativen.
## Steg 5: Lägg till uppdragsvykolumner
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Lägg till önskade kolumner för uppdragsvyn i alternativen.
## Steg 6: Ställ in kodning
```csharp
options.Encoding = Encoding.Unicode;
```
Ställ in kodningen för utdatafilen.
## Steg 7: Spara projektet som XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Spara projektet med de konfigurerade alternativen som en XLSX-fil.

## Slutsats
den här handledningen har vi lärt oss hur man konfigurerar MS Project XLSX-alternativ med Aspose.Tasks för .NET. Genom att följa dessa steg kan du anpassa utdataformatet efter dina krav, vilket förbättrar flexibiliteten och användbarheten i ditt projektledningsarbetsflöde.
## FAQ's

### F: Kan jag konfigurera olika kolumner för Gantt-diagrammet, Resursvyn och Tilldelningsvyn separat?

S: Ja, du kan anpassa kolumner oberoende för varje vy med Aspose.Tasks för .NET.

### F: Finns det en testversion innan du köper Aspose.Tasks för .NET?

 S: Ja, du kan ladda ner en gratis provversion från[Aspose.Tasks för .NET-versioner sida](https://releases.aspose.com/).

### F: Hur kan jag få support om jag stöter på några problem eller har frågor under implementeringen?

 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för hjälp från samhället och Asposes supportteam.

### F: Kan jag generera XLSX-filer med Aspose.Tasks för .NET på icke-Windows-plattformar?

S: Aspose.Tasks för .NET är främst designat för Windows-plattformar, men du kan utforska kompatibilitetsalternativ för andra plattformar.

### F: Finns det några tillfälliga licensalternativ tillgängliga för testsyften?

 S: Ja, du kan få en tillfällig licens från[Aspose.Tasks temporära licenssida](https://purchase.aspose.com/temporary-license/).
---
title: Bemästra MS Project Spara alternativ för Aspose.Tasks
linktitle: Allmänna sparaalternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig att spara MS Project-filer effektivt med Aspose.Tasks för .NET. Anpassa utskriftsalternativ utan ansträngning för dina projekt.
weight: 17
url: /sv/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra MS Project Spara alternativ för Aspose.Tasks

## Introduktion
Aspose.Tasks för .NET erbjuder kraftfulla funktioner för att manipulera Microsoft Project-filer programmatiskt. I den här handledningen kommer vi att fördjupa oss i krångligheterna med att spara MS Project-filer med hjälp av olika alternativ som tillhandahålls av Aspose.Tasks. Specifikt kommer vi att fokusera på de allmänna sparalternativen som är tillgängliga för Aspose.Tasks, så att du kan skräddarsy utdata efter dina specifika krav.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Installation av Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[nedladdningslänk](https://releases.aspose.com/tasks/net/).
2. Grundläggande förståelse för .NET Framework: Bekantskap med .NET-programmeringskoncept är fördelaktigt.

## Importera namnområden
Innan du dyker in i koden, se till att importera de nödvändiga namnrymden:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Steg 1: Ladda projektfilen
Först måste du ladda MS Project-filen med Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Steg 2: Definiera sparalternativ
 Definiera sparalternativen enligt dina krav. I det här exemplet använder vi`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Steg 3: Anpassa vykolumner
Du kan anpassa vykolumner som Gantt-diagram, resursvy och tilldelningsvy. Så här lägger du till kolumner till var och en:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Steg 4: Spara projektet med alternativ
Slutligen, spara projektet med de angivna alternativen:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Slutsats
Att bemästra allmänna MS Project-sparalternativ med Aspose.Tasks för .NET ger dig möjlighet att effektivt anpassa utdataformatet efter ditt projekts behov.
## FAQ's
### F: Är Aspose.Tasks kompatibel med olika versioner av MS Project-filer?
S: Ja, Aspose.Tasks stöder olika versioner av MS Project-filer, vilket säkerställer kompatibilitet mellan olika miljöer.
### F: Kan jag prova Aspose.Tasks innan jag köper?
 S: Ja, du kan utforska Aspose.Tasks med en gratis provperiod tillgänglig[här](https://releases.aspose.com/).
### F: Var kan jag hitta dokumentation för Aspose.Tasks?
 S: Detaljerad dokumentation finns[här](https://reference.aspose.com/tasks/net/), som ger omfattande vägledning om hur du använder Aspose.Tasks-funktioner.
### F: Hur kan jag få tillfälliga licenser för Aspose.Tasks?
 S: Tillfälliga licenser är tillgängliga för utvärderingssyften[här](https://purchase.aspose.com/temporary-license/).
### F: Var kan jag söka stöd för Aspose.Tasks-relaterade frågor?
 S: Du kan gå med i Aspose.Tasks communityforum[här](https://forum.aspose.com/c/tasks/15)för att få hjälp av experter och andra utvecklare.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

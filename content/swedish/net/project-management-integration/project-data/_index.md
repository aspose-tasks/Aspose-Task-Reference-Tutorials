---
title: Bemästra projektdata med Aspose.Tasks
linktitle: Arbeta med projektdata i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du manipulerar Microsoft Project-data med Aspose.Tasks i .NET. Skapa uppgifter, lägg till resurser och spara projekt med lätthet.
type: docs
weight: 16
url: /sv/net/project-management-integration/project-data/
---
## Introduktion
den här handledningen kommer vi att utforska hur man arbetar med Microsoft Project-data med hjälp av Aspose.Tasks-biblioteket för .NET. Aspose.Tasks tillhandahåller kraftfulla funktioner för att manipulera projektfiler, inklusive att skapa uppgifter, lägga till resurser, ställa in egenskaper och spara projekt i olika format.
## Förutsättningar
Innan du börjar, se till att du har följande:
1.  Installation av Aspose.Tasks-biblioteket: Ladda ner och installera Aspose.Tasks-biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Se till att du har en .NET-utvecklingsmiljö inrättad.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnområden
Innan du arbetar med Aspose.Tasks, importera de nödvändiga namnrymden till ditt projekt:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg 1: Initiera projektobjekt
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Denna rad initierar en ny instans av`Project` klass, som representerar en Microsoft Project-fil.
## Steg 2: Ställ in projektegenskaper
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Dessa rader visar hur man ställer in egenskaper för projektet såsom arbetsformat och uppgiftsskapande läge.
## Steg 3: Lägga till uppgifter
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Här läggs en ny uppgift med namnet "Task 1" till rotuppgiften för projektet.
## Steg 4: Ställ in uppgiftsegenskaper
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Dessa rader anger startdatum, varaktighet och slutdatum för "Uppgift 1".
## Steg 5: Lägga till resurser
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Den här delen visar hur man lägger till en arbetsresurs till projektet.
## Steg 6: Tilldela resurser till uppgifter
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Dessa rader visar hur man tilldelar den tidigare tillagda arbetsresursen till "Uppgift 1" med specifika start-, arbets- och slutdatum.
## Steg 7: Spara projekt
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Slutligen sparas projektet i Microsoft Project XML-filformat.

## Slutsats
I den här handledningen har vi lärt oss hur man arbetar med Microsoft Project-data med hjälp av Aspose.Tasks-biblioteket i .NET. Genom att följa steg-för-steg-guiden kan du manipulera projektfiler, lägga till uppgifter, resurser, tilldela resurser till uppgifter och spara projekt i olika format.
## FAQ's
### F: Kan Aspose.Tasks hantera komplexa projektstrukturer?
S: Ja, Aspose.Tasks tillhandahåller omfattande stöd för komplexa projektstrukturer, vilket gör att du kan hantera uppgifter, resurser och uppdrag effektivt.
### F: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project?
S: Aspose.Tasks stöder ett brett utbud av Microsoft Project-versioner, vilket säkerställer kompatibilitet mellan olika miljöer.
### F: Kan jag integrera Aspose.Tasks med andra .NET-bibliotek?
S: Absolut, Aspose.Tasks integreras sömlöst med andra .NET-bibliotek, vilket ger flexibilitet i dina utvecklingsprojekt.
### F: Erbjuder Aspose.Tasks stöd för projektschemaläggningsalgoritmer?
S: Ja, Aspose.Tasks inkluderar avancerade schemaläggningsalgoritmer som hjälper dig att optimera projekttidslinjer och resursutnyttjande.
### F: Finns det ett communityforum för Aspose.Tasks-användare?
 S: Ja, du kan hitta användbara resurser och engagera dig med andra Aspose.Tasks-användare på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
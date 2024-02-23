---
title: Spara MS Project-filer i olika format i Aspose.Tasks
linktitle: Spara filer i olika format i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du sparar MS Project-filer i olika format med Aspose.Tasks för .NET. Enkla steg för effektiv projektledning.
type: docs
weight: 17
url: /sv/net/rate-recurring-tasks/save-file-formats/
---
## Introduktion
I den här handledningen kommer vi att utforska hur man sparar Microsoft Project-filer i olika format med Aspose.Tasks för .NET. Aspose.Tasks är ett kraftfullt API som tillåter utvecklare att manipulera och hantera projektfiler programmatiskt.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[här](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö, till exempel Visual Studio.
3. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnområden
Se till att importera de nödvändiga namnrymden i början av din C#-fil:
```csharp

using Aspose.Tasks.Saving;
```
## Steg 1: Skapa ett projektobjekt
Skapa först ett projektobjekt och ladda din Microsoft Project-fil.
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Steg 2: Spara projekt i CSV-format
Låt oss nu spara projektet i CSV-format. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Steg 3: Utforska andra format
 Aspose.Tasks stöder olika format för att spara projektfiler, såsom XML, PDF, XLSX och mer. Du kan utforska dessa format genom att helt enkelt ändra`SaveFileFormat` parametrar i`Save` metod.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Genom att följa dessa steg kan du enkelt spara Microsoft Project-filer i olika format med Aspose.Tasks för .NET.

## Slutsats
I den här handledningen lärde vi oss hur man sparar MS Project-filer i olika format med Aspose.Tasks för .NET. Aspose.Tasks förenklar processen att manipulera projektfiler programmatiskt, vilket erbjuder flexibilitet och effektivitet till utvecklare.
## FAQ's
### F: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?
S: Aspose.Tasks stöder Microsoft Project 2003 XML, Microsoft Project 2007 MPP och Microsoft Project 2010 MPP-format.
### F: Kan jag prova Aspose.Tasks innan jag köper?
 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### F: Hur kan jag få support för Aspose.Tasks?
 S: Du kan få stöd från Aspose.Tasks communityforum.[här](https://forum.aspose.com/c/tasks/15).
### F: Finns tillfälliga licenser tillgängliga för Aspose.Tasks?
 S: Ja, tillfälliga licenser är tillgängliga för utvärderingssyften. Du kan få en[här](https://purchase.aspose.com/temporary-license/).
### F: Vad är priset för Aspose.Tasks?
 S: Prisinformation finns på köpsidan för Aspose.Tasks[här](https://purchase.aspose.com/buy).
---
title: Konfigurera användningsvyer i Aspose.Tasks
linktitle: Konfigurera användningsvyer i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig att konfigurera uppgiftsanvändningsvyer i Aspose.Tasks för .NET. Förbättra projektvisualiseringen med detaljerade steg. Ladda ner biblioteket nu!
type: docs
weight: 17
url: /sv/net/text-view-configuration/usage-views/
---
## Introduktion
Om du är en .NET-utvecklare som vill förbättra dina projektledningsmöjligheter, är Aspose.Tasks ett kraftfullt verktyg som låter dig manipulera Microsoft Project-filer utan ansträngning. I den här handledningen kommer vi att fokusera på att konfigurera användningsvyer med Aspose.Tasks för .NET. Följ med för att få insikter i hur du renderar uppgiftsanvändningsvyer med detaljer för bättre projektvisualisering.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Tasks Library: Se till att du har Aspose.Tasks-biblioteket integrerat i ditt .NET-projekt. Om inte kan du ladda ner den[här](https://releases.aspose.com/tasks/net/) och följ installationsanvisningarna.
- Dokumentkatalog: Skapa en katalog där dina projektdokument lagras. Ersätt "Din dokumentkatalog" i kodavsnitten med den faktiska sökvägen till din dokumentkatalog.
## Importera namnområden
I kodavsnittet som tillhandahålls kommer du att märka användningen av vissa namnområden. Se till att inkludera dessa i ditt projekt för sömlös integration:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## Steg 1: Återge uppgiftsanvändningsvy med detaljer
Låt oss börja med att återge en uppgiftsanvändningsvy med detaljer. Följ dessa steg:
## Steg 1.1: Ladda projekt
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## Steg 1.2: Få vyn
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## Steg 1.3: Anpassa vyinställningar
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## Steg 1.4: Spara projekt som PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## Steg 2: Visa informationshuvudkolumn
I det här steget kommer vi att ändra vyinställningarna för att visa kolumnen för detaljerad rubrik och spara projektet som PDF:
## Steg 2.1: Visa informationshuvudkolumn
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## Steg 2.2: Upprepa informationshuvudet på alla rader
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## Steg 2.3: Spara projekt som PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## Slutsats
Grattis! Du har framgångsrikt konfigurerat användningsvyer i Aspose.Tasks. Denna handledning ger en grund för effektiv projektledning och visualisering med Aspose.Tasks-biblioteket.

### FAQ's
### F: Var kan jag hitta Aspose.Tasks dokumentation?
 Den omfattande dokumentationen finns tillgänglig[här](https://reference.aspose.com/tasks/net/).
### F: Hur kan jag ladda ner Aspose.Tasks för .NET?
 Ladda ner biblioteket[här](https://releases.aspose.com/tasks/net/).
### F: Var kan jag köpa Aspose.Tasks?
 Du kan köpa Aspose.Tasks[här](https://purchase.aspose.com/buy).
### F: Finns det en gratis provperiod?
 Ja, utforska den kostnadsfria provperioden[här](https://releases.aspose.com/).
### F: Behöver du support eller har frågor?
 Besök supportforumet[här](https://forum.aspose.com/c/tasks/15).
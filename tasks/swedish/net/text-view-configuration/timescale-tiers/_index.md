---
title: Konfigurera Gantt-diagrams tidsskalanivåer i Aspose.Tasks
linktitle: Konfigurera tidsskalanivåer i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska Aspose.Tasks för .NET för att konfigurera tidsskalanivåer i din Gantt-diagramvy för exakt projekttidslinjevisualisering. #Aspose.Tasks #MS Project
type: docs
weight: 16
url: /sv/net/text-view-configuration/timescale-tiers/
---
## Introduktion
I det dynamiska landskapet för projektledning är effektiv visualisering avgörande för att förstå tidslinjer och deadlines. Aspose.Tasks för .NET tillhandahåller en kraftfull verktygsuppsättning, och i den här handledningen kommer vi att utforska hur man konfigurerar tidsskalanivåer för optimal representation i Gantt-diagramvyn. Följ dessa steg-för-steg-instruktioner för att förbättra din projektvisualisering.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande:
- Grundläggande kunskaper i C# och .NET.
-  Aspose.Tasks för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
- En utvecklingsmiljö inrättad för .NET-applikationsutveckling.
## Importera namnområden
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Låt oss nu dela upp varje steg i exemplet.
## Steg 1: Initiera projekt och lägg till uppgiftslänkar
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Här skapar vi ett projekt och upprättar uppgiftslänkar mellan "Task 1" och "Task 2."
## Steg 2: Konfigurera Gantt-diagramvy
```csharp
var view = (GanttChartView)project.DefaultView;
```
Öppna Gantt-diagramvyn för anpassning.
## Steg 3: Ställ in mellantidsskalanivån
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Anpassa den mellersta tidsskalanivån för att visa veckor med specifika etiketter och justering.
## Steg 4: Lägg till Top Timescale Tier
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Lägg till en högsta tidsskalanivå för att representera månader.
## Steg 5: Anpassa mellannivådatum
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Anpassa månadsetiketterna för bättre visualisering.
## Steg 6: Ställ in projekttidsskala
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Definiera projektets tidsskala för att styra den övergripande tidslinjen.
## Steg 7: Spara projektet med anpassad tidsskala
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Spara projektet med de definierade tidsskalainställningarna.
## Slutsats
Sammanfattningsvis, konfigurering av tidsskalanivåer i Aspose.Tasks för .NET möjliggör en mer skräddarsydd och visuellt tilltalande representation av projektets tidslinjer. Dessa steg ger dig möjlighet att skapa en Gantt-diagramvy som exakt motsvarar dina projektledningsbehov.
## Vanliga frågor
### Kan jag använda Aspose.Tasks med andra .NET-bibliotek?
Ja, Aspose.Tasks integreras sömlöst med andra .NET-bibliotek, vilket erbjuder flexibilitet i din utvecklingsstack.
### Finns en tillfällig licens tillgänglig för teständamål?
 Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för utvärdering.
### Finns det ytterligare anpassningsalternativ för Gantt-diagramvyn?
Absolut, Aspose.Tasks erbjuder omfattande anpassningsalternativ för Gantt-diagramvyn för att passa olika projektkrav.
### Kan jag rendera tidsskalor i olika format?
Visst kan du utforska olika format och stilar för tidsskalarepresentation för att bäst passa ditt projekts sammanhang.
### Finns det ett communityforum för Aspose.Tasks-support?
 Ja, besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och diskussioner.
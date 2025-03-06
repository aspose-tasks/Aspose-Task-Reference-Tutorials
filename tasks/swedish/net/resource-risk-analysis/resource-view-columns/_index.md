---
title: Anpassa MS Project Resource View-kolumner i Aspose.Tasks
linktitle: Anpassa resursvykolumner i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du anpassar MS Projects resursvykolumner effektivt med Aspose.Tasks för .NET. Skapa skräddarsydda vyer för bättre projektledning.
weight: 17
url: /sv/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Anpassa MS Project Resource View-kolumner i Aspose.Tasks

## Introduktion
Aspose.Tasks för .NET är ett kraftfullt API som låter utvecklare arbeta med Microsoft Project-filer programmatiskt. En vanlig uppgift inom projektledning är att anpassa vyer för att visa specifik information. I den här handledningen kommer vi att utforska hur man anpassar MS Project-resursvykolumner med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Aspose.Tasks för .NET Library: Du kan ladda ner det från[här](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Ha ett exempel på MS Project-filen till hands för testning.
3. Utvecklingsmiljö: En utvecklingsmiljö inrättad med .NET framework.
## Importera namnområden
Låt oss först importera de nödvändiga namnrymden till vårt projekt:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Steg 1: Ladda projektfilen
Ladda MS Project-filen med Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Steg 2: Hämta resurs och definiera alternativ
Skaffa sedan resursen vars vykolumner du vill anpassa och definiera PDF-sparalternativen:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Steg 3: Definiera anpassade kolumner
Definiera nu anpassade kolumner för resursvyn. Du kan ange olika fält och till och med använda delegater för anpassade beräkningar:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Steg 4: Iterera över kolumner
Iterera över de definierade kolumnerna och visa deras egenskaper:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Steg 5: Spara den anpassade vyn
Slutligen, ställ in den anpassade vyn och spara den som en PDF-fil:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Genom att följa dessa steg kan du effektivt anpassa MS Projects resursvykolumner med Aspose.Tasks för .NET.
## Slutsats
Att anpassa MS Project-resursvykolumner är viktigt för att visa relevant information skräddarsydd för ditt projekts behov. Med Aspose.Tasks för .NET blir denna uppgift enkel och effektiv, så att du enkelt kan skapa anpassade vyer.
## FAQ's
### Kan jag anpassa vyer för andra element förutom resurser?
Ja, Aspose.Tasks tillåter anpassning för uppgifter, uppdrag och andra projektelement också.
### Stöder Aspose.Tasks att spara vyer i andra format än PDF?
Ja, du kan spara vyer i olika format som XLSX, HTML och bilder.
### Är det möjligt att använda formatering på den anpassade vyn?
Absolut, Aspose.Tasks erbjuder omfattande formateringsalternativ för att förbättra utseendet på dina anpassade vyer.
### Kan jag dynamiskt uppdatera den anpassade vyn baserat på ändrade projektdata?
Ja, du kan uppdatera och återskapa den anpassade vyn när den underliggande projektdatan ändras.
### Stöder Aspose.Tasks utveckling över plattformar?
Aspose.Tasks för .NET riktar sig främst till .NET-plattformar, men det finns även versioner tillgängliga för Java och andra plattformar.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

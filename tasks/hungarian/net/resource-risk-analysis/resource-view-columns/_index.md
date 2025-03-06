---
title: Testreszabhatja az Aspose.Tasks MS Project erőforrásnézet oszlopait
linktitle: Az Aspose.Tasks erőforrásnézet oszlopainak testreszabása
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan szabhatja hatékonyan az MS Project erőforrásnézet oszlopait az Aspose.Tasks for .NET használatával. Hozzon létre személyre szabott nézeteket a jobb projektmenedzsment érdekében.
weight: 17
url: /hu/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Testreszabhatja az Aspose.Tasks MS Project erőforrásnézet oszlopait

## Bevezetés
Az Aspose.Tasks for .NET egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal. A projektmenedzsment egyik gyakori feladata a nézetek testreszabása bizonyos információk megjelenítéséhez. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet testreszabni az MS Project erőforrásnézet oszlopait az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
1.  Aspose.Tasks for .NET Library: Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Legyen kéznél egy minta MS Project fájl a teszteléshez.
3. Fejlesztői környezet: .NET keretrendszerrel beállított fejlesztői környezet.
## Névterek importálása
Először is importáljuk a szükséges névtereket a projektünkbe:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 1. lépés: Töltse be a projektfájlt
Töltse be az MS Project fájlt az Aspose.Tasks API segítségével:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 2. lépés: Erőforrás beszerzése és beállítások megadása
Ezután szerezze be azt az erőforrást, amelynek nézetoszlopait testre szeretné szabni, és adja meg a PDF mentési beállításait:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## 3. lépés: Egyéni oszlopok meghatározása
Most határozzon meg egyéni oszlopokat az erőforrásnézethez. Különféle mezőket adhat meg, és akár delegáltakat is használhat egyéni számításokhoz:
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
## 4. lépés: Iteráció oszlopok felett
Iteráljon a meghatározott oszlopokon, és jelenítse meg tulajdonságaikat:
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
## 5. lépés: Mentse el a testreszabott nézetet
Végül állítsa be az egyéni nézetet, és mentse el PDF fájlként:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Az alábbi lépések követésével hatékonyan testreszabhatja az MS Project erőforrásnézet oszlopait az Aspose.Tasks for .NET használatával.
## Következtetés
Az MS Project erőforrásnézet oszlopainak testreszabása elengedhetetlen a projekt igényeihez szabott releváns információk megjelenítéséhez. Az Aspose.Tasks for .NET segítségével ez a feladat egyszerűvé és hatékonysá válik, így könnyedén hozhat létre testreszabott nézeteket.
## GYIK
### Testreszabhatom a nézeteket az erőforrásokon kívül más elemekhez is?
Igen, az Aspose.Tasks lehetővé teszi a feladatok, megbízások és egyéb projektelemek testreszabását is.
### Az Aspose.Tasks támogatja a nézetek PDF-től eltérő formátumba történő mentését?
Igen, mentheti a nézeteket különböző formátumokban, például XLSX, HTML és képek formájában.
### Alkalmazható formázás az egyéni nézetben?
Természetesen az Aspose.Tasks kiterjedt formázási lehetőségeket kínál a testreszabott nézetek megjelenésének javításához.
### Dinamikusan frissíthetem az egyéni nézetet a változó projektadatok alapján?
Igen, frissítheti és újra létrehozhatja az egyéni nézetet, amikor az alapul szolgáló projektadatok megváltoznak.
### Az Aspose.Tasks támogatja a platformok közötti fejlesztést?
Az Aspose.Tasks for .NET elsősorban a .NET-platformokat célozza meg, de vannak Java- és más platformok verziói is.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

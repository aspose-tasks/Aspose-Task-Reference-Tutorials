---
title: Egyéni hozzárendelés nézet oszlopa az Aspose.Tasks-ban
linktitle: Egyéni hozzárendelés nézet oszlopa az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan adhat hozzá egyéni hozzárendelési nézet oszlopokat az Aspose.Tasks for .NET-hez a projektkezelési képességek javítása érdekében.
weight: 16
url: /hu/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni hozzárendelés nézet oszlopa az Aspose.Tasks-ban

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan adhat hozzá egyéni oszlopokat hozzárendelési nézetekhez az Aspose.Tasks for .NET használatával. Az egyéni oszlopok rugalmasságot biztosítanak, és lehetővé teszik a projektmenedzsment igényeinek megfelelő további információk megjelenítését.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. C# programozási nyelv alapismerete.
2.  Aspose.Tasks for .NET könyvtár telepítve. Ha nem, akkor letöltheti[itt](https://releases.aspose.com/tasks/net/).
3. Integrált fejlesztői környezet (IDE), például a Visual Studio.

## Névterek importálása

Először is importáljuk a szükséges névtereket az egyéni hozzárendelési nézet oszlopok létrehozásához szükséges osztályok és metódusok eléréséhez:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 1. lépés: Töltse be a projektet

 A kezdéshez töltse be a projektfájlt a`Project` osztály:

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## 2. lépés: Hozzon létre Táblázat mentési opciókat

 Ezután hozzon létre egy példányt a`Spreadsheet2003SaveOptions` amely lehetővé teszi a hozzárendelés nézet oszlopainak testreszabását:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## 3. lépés: Egyéni oszlop meghatározása

 Most határozza meg az egyéni oszlopot a példány létrehozásával`AssignmentViewColumn`. Ez az osztály megköveteli az oszlop nevét, szélességét és egy delegálási függvényt a hozzárendelési adatok oszlopszöveggé alakításához:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## 4. lépés: Adjon egyéni oszlopot a Beállításokhoz

Adja hozzá az egyéni oszlopot a mentési beállítások hozzárendelési nézet oszlopgyűjteményéhez:

```csharp
options.AssignmentView.Columns.Add(column);
```

## 5. lépés: Ismétlés a hozzárendeléseken keresztül

Iteráljon végig a projektben minden erőforrás-hozzárendelésen, és jelenítse meg az egyéni oszlopszöveget:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## 6. lépés: Mentse el a projektet egyéni oszlopokkal

Végül mentse a projektet az egyéni hozzárendelési nézet oszlopaival:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá egyéni hozzárendelési nézet oszlopokat az Aspose.Tasks for .NET használatával. Az egyéni oszlopok rugalmasságot kínálnak a projektkövetelményekhez szabott további információk megjelenítésében, javítva ezzel a projektkezelési képességeket.

## GYIK

### 1. kérdés: Hozzáadhatok több egyéni oszlopot a hozzárendelési nézethez?

 1. válasz: Igen, több egyéni oszlopot is hozzáadhat a következő példányok létrehozásával`AssignmentViewColumn` és hozzáadjuk őket a`Columns` Gyűjtemény.

### 2. kérdés: Rendelkezésre állnak-e előre meghatározott konverterek a közös hozzárendelési mezőkhöz?

2. válasz: Igen, az Aspose.Tasks előre definiált konvertereket biztosít a gyakori hozzárendelési mezőkhöz, megkönnyítve az adatok kinyerését az egyéni oszlopokhoz.

### 3. kérdés: Testreszabhatom az egyéni oszlopok megjelenését, például a szöveg formázását vagy a stílusok alkalmazását?

3. válasz: Igen, testreszabhatja az egyéni oszlopok megjelenését a tulajdonságok, például a szélesség, a betűtípus és az igazítás módosításával.

### 4. kérdés: Eltávolíthatók az alapértelmezett oszlopok a hozzárendelési nézetből?

 4. válasz: Igen, eltávolíthatja az alapértelmezett oszlopokat, ha kizárja őket a`Columns` összegyűjtése vagy szélességük nullára állítása.

### 5. kérdés: Az Aspose.Tasks támogatja a projektek exportálását más formátumokba, az egyéni oszlopokat tartalmazó táblázatokon kívül?

5. válasz: Igen, az Aspose.Tasks támogatja a projektek exportálását különféle formátumokba, például PDF, HTML és XML formátumokba, így sokoldalú projektjelentési lehetőségeket tesz lehetővé.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

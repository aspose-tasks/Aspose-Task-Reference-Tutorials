---
title: Az MS Project Filter Criteria elsajátítása az Aspose.Tasks segítségével
linktitle: Szűrési feltételek az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan valósíthat meg szűrési feltételeket az MS Projectben az Aspose.Tasks for .NET használatával. Növelje a projektmenedzsment hatékonyságát célzott adatelemzéssel.
type: docs
weight: 18
url: /hu/net/tasks-project-management/filter-criteria/
---
## Bevezetés
A projektmenedzsment területén a Microsoft Project megbízható eszköz, amely számos funkciót kínál a projekttervezőknek és -menedzsereknek. Számos funkciója között rejlik a projektadatok szűrésének képessége, amely lehetővé teszi a felhasználók számára, hogy projektfeladataik bizonyos szempontjaira összpontosítsanak. E szűrési képességek elsajátítása azonban megfelelő útmutatás nélkül ijesztő feladat lehet. Ennek az oktatóanyagnak a célja, hogy tisztázza a folyamatot azáltal, hogy lépésről lépésre bemutatja a kritériumszűrők megvalósítását az MS Projectben az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. C# alapvető ismerete: A C# programozási nyelv ismerete szükséges az oktatóanyagban tárgyalt fogalmak megértéséhez.
2.  Az Aspose.Tasks for .NET telepítése: Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van a fejlesztői környezetében. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
3. Microsoft Project File: Készítsen egy Microsoft Project fájlt (pl. Project2003.mpp), amelyet a szűrőfeltételek megvalósításához fog használni.

## Névterek importálása
Először is importálnia kell a szükséges névtereket az Aspose.Tasks for .NET használatához. Kovesd ezeket a lepeseket:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## 1. lépés: Töltse be a projektfájlt
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Magyarázat: Ez a kódsor inicializálja az új példányt`Project` osztályt, és betölti az elérési útjában megadott Microsoft Project fájlt.
## 2. lépés: Töltse le a Feladatszűrőt
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Magyarázat: Itt lekérünk egy feladatszűrőt a projektből. Állítsa be az indexet (`[1]`) a kívánt szűrő kiválasztásához.
## 3. lépés: Feltételsorok megjelenítése
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Magyarázat: Ez a szakasz a szűrő minden feltételsorán keresztül ismétlődik, és megjeleníti annak mezőjét, működését, tesztjét és értékeit (ha vannak).
## 4. lépés: Nyomtatási szűrő kritériumai
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Magyarázat: Kiírja a szűrőfeltételek működését.
## 5. lépés: Megjelenítési feltételek részletei
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Magyarázat: Ez a rész részletes információkat kér le és jelenít meg az egyes feltételsorokról, így betekintést nyújt a szűrő konfigurációjába.

## Következtetés
A szűrőkritériumok elsajátítása az MS Projectben az Aspose.Tasks for .NET használatával értékes készség, amely jelentősen növelheti a projektmenedzsment hatékonyságát. Az oktatóanyag követésével megtanulta, hogyan lehet programozottan módosítani a szűrési feltételeket, lehetővé téve a projektnézetek testreszabását az egyedi igényekhez.
## GYIK
### K: Alkalmazhatok több szűrőt egyidejűleg az MS Projectben?
V: Igen, több szűrőt kombinálhat a projektadatok további finomításához.
### K: Az Aspose.Tasks támogatja a Microsoft Project fájlok régebbi verzióit?
V: Igen, az Aspose.Tasks visszamenőleges kompatibilitást biztosít, lehetővé téve a Microsoft Project fájlok különböző verzióival való munkát.
### K: Az Aspose.Tasks kompatibilis más .NET keretrendszerekkel?
V: Az Aspose.Tasks támogatja a .NET Framework-et, a .NET Core-t és a .NET Standard-t, rugalmasságot biztosítva a különböző fejlesztői környezetekben.
### K: Testreszabhatom a szűrési feltételeket a dinamikus feltételek alapján?
V: Természetesen programozottan módosíthatja a szűrési feltételeket a dinamikus paraméterek alapján, lehetővé téve az adaptív projektadatok elemzését.
### K: Hol kérhetek segítséget, ha problémákat tapasztalok az Aspose.Tasks szolgáltatással?
 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) hogy kérjen támogatást a közösségtől, vagy közvetlenül forduljon az Aspose-hoz.Tasks személyre szabott segítségnyújtás.
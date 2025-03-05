---
title: Táblázatmező-gyűjtemények elsajátítása az Aspose.Tasks-ban .NET-hez
linktitle: Táblázatmezők gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel a projektmenedzsment dinamikus világát az Aspose.Tasks for .NET segítségével. Ismerje meg, hogyan kezelheti a táblázatmező-gyűjteményeket a testreszabott projektélmény érdekében.
type: docs
weight: 13
url: /hu/net/task-table-management/table-field-collection/
---
## Bevezetés
Az Aspose.Tasks for .NET egy hatékony könyvtár, amely megkönnyíti a projektkezelést azáltal, hogy kiterjedt funkcionalitást biztosít a Microsoft Project fájlokkal való munkavégzéshez. Ebben az oktatóanyagban az Aspose.Tasks táblázatmezőinek gyűjteményében fogunk elmélyülni, és megvizsgáljuk, hogyan lehet ezeket hatékonyan kezelni és kezelni a C# használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy beállította a következőket:
- C# programozási nyelv gyakorlati ismerete.
-  Aspose.Tasks for .NET könyvtár telepítve. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
- Integrált fejlesztői környezet (IDE), például a Visual Studio.
## Névterek importálása
Először is győződjön meg arról, hogy a szükséges névtereket importálta a C# fájl elejére:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Most bontsuk le az egyes példákat több lépésre, lépésről lépésre útmutató formátumban.
## 1. lépés: Állítsa be a dokumentumkönyvtárat
Állítsa be a dokumentumkönyvtár elérési útját, ahol a projektfájl található.
```csharp
String DataDir = "Your Document Directory";
```
## 2. lépés: Töltse be a projektfájlt
Töltse be a projektfájlt az Aspose.Tasks könyvtár használatával.
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## 3. lépés: Ismétlés a táblázat mezői felett
Iteráljon a projekten belüli táblázatmezőkön.
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    //iteráljon a táblázat mezői között
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## 4. lépés: Új táblázatmező hozzáadása
Adjon hozzá egy új táblázatmezőt a meglévő táblázathoz.
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## 5. lépés: Szúrjon be egy új mezőt
Szúrjon be egy új mezőt a táblázat egy adott helyére.
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## 6. lépés: Szerkessze az Új táblázat mezőt
Szerkessze az újonnan hozzáadott táblamezőt indexeléréssel.
```csharp
table.TableFields[idx].WrapHeader = true;
```
## 7. lépés: Távolítsa el a mezőt
Távolítsa el a táblázat mezőjét egyenként, vagy törölje a teljes gyűjteményt.
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// Távolítsa el a mezőt
table.TableFields.RemoveAt(idx);
```
## 8. lépés: Törölje a gyűjteményt
Egyenként vagy teljesen törölje a táblázat mezőgyűjteményét.
```csharp
if (deleteOneByOne)
{
    // Egyenként távolítsa el
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // Törölje teljesen a gyűjteményt
    table.TableFields.Clear();
}
```
Sikeresen felfedezte a táblamezők gyűjteményét az Aspose.Tasks for .NET-ben, lehetővé téve ezek kezelését és kezelését a projekt követelményei szerint.
## Következtetés
Összefoglalva, az Aspose.Tasks for .NET táblamezőgyűjteményeinek kezelésének megértése lehetőséget ad a hatékony projektkezelésre és testreszabásra. Az Aspose.Tasks nyújtotta rugalmasságnak köszönhetően a fejlesztők zökkenőmentesen testreszabhatják alkalmazásaikat a konkrét projektigények kielégítésére.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Tasks for .NET programot a Microsoft Project fájlok bármely verziójával?
Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, így biztosítja a kompatibilitást és a rugalmasságot.
### Lehetséges-e dinamikusan létrehozni és módosítani a táblamezőket futás közben?
Teljesen! Ahogy az oktatóanyagban is látható, szükség szerint dinamikusan hozzáadhat, beszúrhat, szerkeszthet és eltávolíthat táblázatmezőket.
### Vannak-e licencelési megfontolások az Aspose.Tasks for .NET használatához kereskedelmi projektekben?
 Igen, érvényes licenc szükséges az Aspose.Tasks for .NET használatához egy kereskedelmi projektben. Engedélyt szerezhet[itt](https://purchase.aspose.com/buy).
### Hogyan kaphatok támogatást vagy kérhetek segítséget az Aspose.Tasks for .NET-hez?
 Meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15)támogatást kapni, kérdéseket feltenni és együttműködni a közösséggel.
### Létezik ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 Igen, egy ingyenes próbaverzióval felfedezheti az Aspose.Tasks for .NET szolgáltatásait. Töltsd le[itt](https://releases.aspose.com/).
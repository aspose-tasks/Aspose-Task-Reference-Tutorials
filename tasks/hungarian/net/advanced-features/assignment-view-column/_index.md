---
date: 2026-03-19
description: Ismerje meg, hogyan adhat hozzá több egyéni oszlopot, és formázhatja
  az egyéni oszlopszélességet egy projekt XML-be exportálásakor az Aspose.Tasks for
  .NET használatával.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Több egyéni oszlop hozzáadása a hozzárendelés nézethez az Aspose.Tasks-ben
url: /hu/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Több egyéni oszlop hozzáadása a hozzárendelés nézethez az Aspose.Tasks-ben

## Bevezetés

Ebben az oktatóanyagban megtudja, **hogyan adjon hozzá több egyéni oszlopot** a hozzárendelés nézethez az Aspose.Tasks for .NET segítségével. Az egyéni oszlopok lehetővé teszik további adatok megjelenítését – például megjegyzések, költségek vagy egyéni jelzők – közvetlenül az exportált jelentésekben. A útmutató végére képes lesz formázni az egyéni oszlop szélességét, exportálni a projektet XML-be, és testre szabni a nézetet a projektmenedzsment igényeihez.

## Gyors válaszok
- **Mit érhetek el?** Bármely hozzárendelési adat megjelenítése egyéni oszlopokban és azok megjelenésének szabályozása.  
- **Melyik formátum támogatja?** A projekt exportálása XML-be (vagy más formátumokba) a `Spreadsheet2003SaveOptions` használatával.  
- **Szükségem van licencre?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termelési használathoz.  
- **Mely .NET verziók működnek?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hány oszlopot adhatok hozzá?** Korlátlan – egyszerűen hozzon létre további `AssignmentViewColumn` példányokat.

## Mi a több egyéni oszlop?
A több egyéni oszlop felhasználó által definiált mezők, amelyek az alapértelmezett hozzárendelési oszlopok mellett jelennek meg, amikor egy projektet mentenek vagy exportálnak. Lehetővé teszik, hogy bármely `ResourceAssignment` objektum tulajdonságát megjelenítsék, például egyéni megjegyzéseket, költségkódokat vagy számított értékeket.

## Miért adjunk hozzá több egyéni oszlopot a hozzárendelés nézethez?
- **Fejlett jelentés:** Projekt‑specifikus információk belefoglalása, amelyeket a beépített oszlopok nem fednek le.  
- **Jobb döntéshozatal:** Az érintettek láthatják a pontos adatokat, amire szükségük van, anélkül, hogy nyers fájlokba kellene mélyedniük.  
- **Következetes formázás:** Az oszlopszélesség és a szövegkonverzió szabályozása a tiszta, olvasható kimenet érdekében.  

## Előfeltételek

Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik:

1. Alapvető C# programozási nyelvi ismeretekkel.  
2. Az Aspose.Tasks for .NET könyvtár telepítve van. Ha nincs, letöltheti **[itt](https://releases.aspose.com/tasks/net/)**.  
3. Integrált fejlesztői környezettel (IDE), például a Visual Studio-val.  

## Lépésről lépésre útmutató

### 1. lépés: Névterek importálása
Először importálja a névtereket, amelyek biztosítják a projektekhez és vizualizációkhoz szükséges osztályokat.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### 2. lépés: Projekt betöltése
Hozzon létre egy `Project` példányt, és töltse be egy meglévő MPP fájlt.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### 3. lépés: Spreadsheet mentési beállítások létrehozása
Példányosítsa a `Spreadsheet2003SaveOptions` osztályt – ez az objektum lehetővé teszi a hozzárendelés nézet testreszabását exportálás előtt.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### 4. lépés: Egyéni oszlop definiálása
Hozzon létre egy `AssignmentViewColumn`-t minden megjeleníteni kívánt adatdarabhoz. Az alábbiakban egy **Notes** (Megjegyzések) oszlopot adunk hozzá 200 pont szélességgel.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tipp:** Több egyéni oszlop hozzáadásához ismételje meg ezt a lépést különböző mezőnevekkel és delegált logikával, majd adja hozzá az egyes példányokat a `options.AssignmentView.Columns`-hoz.

### 5. lépés: Egyéni oszlop hozzáadása a beállításokhoz
Adja hozzá az oszlopot (vagy oszlopokat) a hozzárendelés nézet `Columns` gyűjteményéhez.

```csharp
options.AssignmentView.Columns.Add(column);
```

### 6. lépés: Hozzárendelések bejárása (opcionális hibakeresés)
Átfuthat a hozzárendeléseken, hogy ellenőrizze, a egyéni oszlop szövege helyesen generálódik-e.

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

### 7. lépés: Projekt mentése egyéni oszlopokkal
Végül mentse a projektet. A példa XML-be ment, de bármely támogatott formátumot választhat.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Hogyan exportáljuk a projektet XML-be egyéni oszlopokkal?
Amikor a `project.Save` metódust a konfigurált `Spreadsheet2003SaveOptions`-szal hívja, az Aspose.Tasks a projekt adatokat – beleértve az összes **több egyéni oszlopot** – a kiválasztott XML fájlba írja. Ez megkönnyíti a gazdagított projektinformációk megosztását más rendszerekkel vagy érintettekkel.

## Az egyéni oszlopszélesség formázása a jobb olvashatóság érdekében
Az `AssignmentViewColumn` konstruktor második paramétere szabályozza az oszlopszélességet (pontban mérve). Állítsa be ezt az értéket a várt szövegmennyiséghez. Például a **300** szélesség jól működik hosszabb megjegyzéseknél, míg a **100** elegendő rövid jelzőkhöz.

## Gyakori problémák és megoldások
- **Az oszlop szövege üresnek jelenik meg:** Győződjön meg arról, hogy a delegált stringet ad vissza, és hogy az alapul szolgáló hozzárendelési tulajdonság (pl. `Asn.NotesText`) fel van töltve.  
- **Az oszlopok nem láthatók az exportált fájlban:** Ellenőrizze, hogy a `options.AssignmentView.Columns` tartalmazza az egyéni oszlopokat a `Save` hívása előtt.  
- **A szélesség figyelmen kívül marad:** Egyes export formátumok saját elrendezési szabályokkal rendelkeznek; az XML tiszteletben tartja a szélességet, de a PDF/HTML további stílusozást igényelhet.

## Gyakran ismételt kérdések

### Q1: Hozzáadhatok több egyéni oszlopot a hozzárendelés nézethez?
**A:** Igen, egyszerűen hozzon létre további `AssignmentViewColumn` objektumokat, és adja hozzá őket a `options.AssignmentView.Columns`-hoz.

### Q2: Vannak előre definiált konverterek a gyakori hozzárendelési mezőkhöz?
**A:** Igen, az Aspose.Tasks beépített konvertereket biztosít számos szabványos mezőhöz, így könnyen lekérheti az adatokat anélkül, hogy egyéni delegáltakat kellene írnia.

### Q3: Testreszabhatom-e az egyéni oszlopok megjelenését, például a szöveg formázását vagy stílusok alkalmazását?
**A:** Teljesen. A szélesség beállítása mellett módosíthatja a betűtípust, igazítást és egyéb vizuális tulajdonságokat az oszlop stílusbeállításain keresztül.

### Q4: Lehetőség van az alapértelmezett oszlopok eltávolítására a hozzárendelés nézetből?
**A:** Az alapértelmezett oszlopokat eltávolíthatja a `Columns` gyűjteményből, vagy a szélességüket nullára állíthatja.

### Q5: Támogatja-e az Aspose.Tasks a projektek exportálását más formátumokba a táblázatokon kívül egyéni oszlopokkal?
**A:** Igen, az Aspose.Tasks exportálhat PDF, HTML, XML és sok más formátumba, miközben megőrzi az egyéni oszlopdefiníciókat.

---

**Utoljára frissítve:** 2026-03-19  
**Tesztelve:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-19
description: Tanulja meg, hogyan állíthat be projekt alapvonalat, és kezelheti hatékonyan
  a feladat alapvonalakat az Aspose.Tasks for .NET segítségével, biztosítva a projekt
  előrehaladásának pontos nyomon követését.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projekt alapvonal beállítása – Kiosztási alapvonal kezelése az Aspose.Tasks-ben
url: /hu/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt alapvonal beállítása – Feladat alapvonal kezelése az Aspose.Tasks-ben

## Bevezetés

Projektmenedzsment feladatok során a **projekt alapvonal beállítása** elengedhetetlen a tényleges előrehaladás méréséhez az eredeti tervhez képest. Az Aspose.Tasks for .NET nem csak lehetővé teszi a **projekt alapvonal beállítását**, hanem teljes ellenőrzést ad a feladat alapvonalak felett is, lehetővé téve a pontos teljesítménykövetést. Ebben az útmutatóban végigvezetünk a teljes folyamaton – a projekt betöltését, az alapvonal beállítását, a feladat alapvonal adatainak olvasását és az alapvonalak összehasonlítását – hogy magabiztosan nyomon követhesse projektjeit.

## Gyors válaszok
- **Mit jelent a „projekt alapvonal beállítása”?** Rögzíti az eredeti ütemezési és költségadatokat, hogy később össze lehessen hasonlítani a tényleges teljesítménnyel.  
- **Melyik API metódus állít be alapvonalat?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **A feladat alapvonalakhoz külön hívás szükséges?** Nem, automatikusan tárolódnak, amikor projekt alapvonalat állít be.  
- **Milyen formátumok támogatottak?** MPP, XML, MPX és továbbiak az Aspose.Tasks segítségével.  
- **Szükséges licenc a termeléshez?** Igen, kereskedelmi licenc szükséges a nem‑próbaverzió használatához.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- Alapvető C# programozási ismeretekkel.  
- Visual Studio (bármely friss verzió).  
- Az Aspose.Tasks for .NET könyvtár hozzáadva a projektjéhez. Letöltheti [itt](https://releases.aspose.com/tasks/net/).  
- Hozzáférés egy MPP formátumú projektfájlhoz (pl. `AssignmentBaseline2007.mpp`).

## Névtér importálása

Adja hozzá a szükséges névtereket a C# fájlja tetejéhez, hogy a fordító tudja, hol találja az Aspose.Tasks osztályokat.

```csharp
using Aspose.Tasks;
using System;
```

## 1. lépés: Projekt betöltése és projekt alapvonal beállítása

Először töltse be a meglévő MPP fájlt, majd hívja meg a `SetBaseline` metódust a **projekt alapvonal beállításához** az egész projektre.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 2. lépés: Feladat alapvonal információk olvasása

Miután az alapvonal be lett állítva, minden erőforrás feladat saját alapvonal rekordokat tartalmaz. Az alábbi ciklus kinyeri és kiírja ezeket a részleteket, beleértve a kezdő/vég dátumokat, költséget, munkát és minden időszakos adatot.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## 3. lépés: Feladat alapvonalak összehasonlítása

Az egyes feladatok alapvonalait összehasonlíthatja a beépített egyenlőség- és összehasonlító operátorokkal. Ez hasznos, ha ütemezési eltolódásokat vagy költségtúllépéseket kell felderíteni a feladatok között.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Gyakori problémák és megoldások

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Az alapvonal adatok üresnek jelennek meg** | A projektfájlt csak‑olvasás módban nyitották meg, vagy az alapvonal soha nem lett beállítva. | Hívja meg a `project.SetBaseline(BaselineType.Baseline)` metódust a feladat alapvonalak olvasása előtt. |
| **`NullReferenceException` a `TimephasedData`-n** | Nem minden alapvonal tartalmaz időszakos bejegyzéseket. | Mindig ellenőrizze, hogy `baseline.TimephasedData != null` (ahogy a kódban is látható). |
| **Helytelen UID lekérés** | Az UID értékek fájlverziók között eltérnek. | Használja a `ResourceAssignments.GetByUid` metódust a megfelelő UID-vel, vagy iteráljon a szükséges feladat megtalálásához. |

## Gyakran ismételt kérdések

**Q: Kezelhet-e az Aspose.Tasks több alapvonalat egyetlen feladatnál?**  
A: Igen, az Aspose.Tasks több alapvonalat támogat minden feladatnál, lehetővé téve a projekt előrehaladásának átfogó nyomon követését az idő során.

**Q: Kompatibilis-e az Aspose.Tasks különböző projektfájl formátumokkal az MPP-n kívül?**  
A: Igen, az Aspose.Tasks széles körű projektfájl formátumot támogat, beleértve az XML, MPX és MPP formátumokat, biztosítva a kompatibilitást különböző projektmenedzsment eszközökkel.

**Q: Módosíthatom programozottan az alapvonal információkat az Aspose.Tasks használatával?**  
A: Teljes mértékben, az Aspose.Tasks kiterjedt API-kat biztosít az alapvonal információk dinamikus módosításához a projekt követelményei szerint, rugalmasságot és irányítást nyújtva a projektmenedzsment folyamatok felett.

**Q: Kínál-e az Aspose.Tasks dokumentációt és támogatási erőforrásokat fejlesztőknek?**  
A: Igen, a fejlesztők hozzáférhetnek átfogó dokumentációhoz, útmutatókhoz és fórumokhoz az Aspose.Tasks weboldalán, megkönnyítve a zökkenőmentes integrációt és a hibakeresést.

**Q: Elérhető-e próbaverzió az Aspose.Tasks for .NET-hez?**  
A: Igen, a fejlesztők ingyenes próbaverziót szerezhetnek az Aspose.Tasks for .NET-ből [itt](https://releases.aspose.com/), lehetővé téve a funkciók és képességek értékelését vásárlási döntés előtt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Legutóbb frissítve:** 2026-03-19  
**Tesztelve:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

---
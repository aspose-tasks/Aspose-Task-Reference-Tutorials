---
date: 2026-03-16
description: Tanulja meg, hogyan kombinálhat több feltételt, és szűrheti a projektfeladatokat
  az Aspose.Tasks for .NET fejlett AND műveletével.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Hogyan kombináljunk több feltételt az Advanced AND művelettel az Aspose.Tasks-ben
url: /hu/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fejlett AND művelet az Aspose.Tasks-ben

## Bevezetés

Ebben az oktatóanyagról megtudhatja, **hogyan kombinálhat több feltételt** az *fejlett AND művelettel* az Aspose.Tasks for .NET-ben. A útmutató végére képes lesz **szűrni a projekt feladatokat** több kritérium alapján – ami elengedhetetlen, ha **feladatokat kell szűrni** például összegző elemek, nem‑null értékek vagy egyedi jelzők egyetlen átfutásban.

## Gyors válaszok
- **Mi a fejlett AND művelet?** Két vagy több szűrőfeltételt egyesít, így csak azok a feladatok kerülnek visszaadásra, amelyek *mind* a kritériumoknak megfelelnek.  
- **Melyik osztály egyesíti a feltételeket?** `Util.And<T>` (az API-ban `And<T>` néven érhető el).  
- **Szükségem van külön licencre?** A normál Aspose.Tasks licenc szükséges a termeléshez; ingyenes próbaverzió is elérhető.  
- **Láncolhatok több mint két feltételt?** Igen – a `And<T>` tetszőleges számú feltételt elfogad.  
- **Mely .NET verziókat támogatja?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Mi a “több feltétel kombinálása” az Aspose.Tasks-ben?

A több feltétel kombinálása azt jelenti, hogy egy összetett szűrőt hozunk létre, amely egyszerre több szabály alapján értékeli a feladatokat. Ez a megközelítés sokkal hatékonyabb, mint a feladatlista többszöri bejárása, mivel a könyvtár egy átfutásban alkalmazza a logikát.

## Miért használjuk a fejlett AND műveletet?

- **Teljesítmény:** Csökkenti a feladatgyűjteményen végzett átfutások számát.  
- **Olvashatóság:** Deklaratív és könnyen karbantartható szűrőlogikát biztosít.  
- **Rugalmasság:** Kevert használhat beépített feltételeket (pl. `SummaryCondition`) egyedi predikátumokkal.  

## Előfeltételek

Mielőtt elkezdjük, győződjön meg róla, hogy rendelkezik:

1. Alapvető C# programozási ismeretekkel.  
2. Telepített Aspose.Tasks for .NET. Ha még nem töltötte le, szerezze be **[itt](https://releases.aspose.com/tasks/net/)**.  
3. Egy IDE, például a Visual Studio (bármely kiadás megfelelő).  

## Névterek importálása

Először importálja azokat a névtereket, amelyek a feladatmodellt és a segédosztályokat biztosítják:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## 1. lépés: Projekt inicializálása és feladatok gyűjtése

Létrehozunk egy `Project` példányt, és a `ChildTasksCollector` segítségével összegyűjtjük a fájl összes feladatát. Ez bemutatja, **hogyan használjuk a gyűjtőt** egy lapos feladatlistához.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 2. lépés: Szűrőfeltételek meghatározása

Itt definiáljuk az egyes alkalmazni kívánt feltételeket. Ebben a példában **összegző feladatokat szűrünk**, és biztosítjuk, hogy a feladatobjektum ne legyen null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 3. lépés: Feltételek kombinálása AND művelettel

Most a `And<T>` osztály segítségével **több feltételt egyesítünk**. Ez a **fejlett AND művelet** magja.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 4. lépés: Feltétel alkalmazása és feladatok szűrése

Miután a kompozit feltétel elkészült, meghívjuk a `Filter` metódust, hogy **szűrjük a projekt feladatait** a kombinált logika alapján.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 5. lépés: Szűrt feladatok kiírása

Végül megjelenítjük azokat a feladatokat, amelyek **mind** a feltételeknek megfeleltek. A `Console.WriteLine` hívásokat bármilyen egyedi feldolgozással helyettesítheti.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Gyakori problémák és megoldások

| Probléma | Miért fordul elő | Gyors megoldás |
|----------|------------------|----------------|
| `Filter` metódus nem található | `using Aspose.Tasks.Util;` hiányzik | Győződjön meg róla, hogy a Util névtér importálva van (lásd a Névterek importálása részt). |
| Nincsenek visszaadott feladatok | A feltételek túl szigorúak (pl. összegző feladatok szűrése, ha egyik sem létezik) | Ellenőrizze, hogy a projekt valóban tartalmaz-e összegző feladatokat, vagy módosítsa a feltételeket. |
| NullReferenceException | `coll.Tasks` null bejegyzéseket tartalmaz | A `NotNullCondition` már védi ezt; tartsa meg az AND láncban. |

## GYIK

### Q1: Mi az Aspose.Tasks for .NET?

Az Aspose.Tasks for .NET egy robusztus API, amely lehetővé teszi a fejlesztők számára, hogy programozottan manipulálják a Microsoft Project fájlokat .NET alkalmazásokban.

### Q2: Alkalmazhatok több mint két feltételt a Util.And használatával?

Igen, a Util.And használható tetszőleges számú feltétel egyesítésére összetett szűrési kritériumok létrehozásához.

### Q3: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET-hez?

Igen, ingyenes próbaverziót tölthet le **[itt](https://releases.aspose.com/)**.

### Q4: Hol találom az Aspose.Tasks for .NET dokumentációját?

A dokumentációt **[itt](https://reference.aspose.com/tasks/net/)** találja.

### Q5: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?

Támogatást kaphat az Aspose.Tasks közösségi fórumon **[itt](https://forum.aspose.com/c/tasks/15)**.

**Kiegészítő Q&A**

**K: Hogyan szűrhetem a feladatokat egyéni mezőértékek alapján?**  
V: Hozzon létre egy `CustomFieldCondition` (vagy valósítsa meg az `ICondition<Task>` interfészt), és adja hozzá a `And<T>` lánchoz.

**K: Ugyanezt a megközelítést használhatom erőforrások szűrésére?**  
V: Igen – cserélje a `Task`-ot `Resource`-ra, és használja a megfelelő feltétel osztályokat.

## Összegzés

A fenti lépések követésével most már tudja, **hogyan kombinálhat több feltételt** a **fejlett AND művelettel** az Aspose.Tasks for .NET-ben. Ez a technika lehetővé teszi, hogy **hatékonyan szűrje a projekt feladatait**, legyen szó összegző elemekről, nem‑null bejegyzésekről vagy bármely egyedi kritériumról, amelyet meghatároz.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-19
description: Tanulja meg, hogyan használja az AND operátort minden feltételben az
  Aspose.Tasks for .NET segítségével a projektfeladatok hatékony szűréséhez.
linktitle: Using AND Operator in All Conditions with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hogyan használjuk az AND operátort az All Conditions-ben az Aspose.Tasks segítségével
url: /hu/net/advanced-features/and-operator-all-conditions/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# AND operátor használata minden feltételben az Aspose.Tasks segítségével

## Bevezetés

Szeretné hatékonyan egyszerűsíteni a projektmenedzsment feladatait? Az Aspose.Tasks for .NET segítségével erőteljes funkciókat vehet igénybe a projektadatok hatékony manipulálásához. Az egyik ilyen lehetőség a **AND operátor használata** minden feltételben, amely lehetővé teszi, hogy egyszerre több kritérium alapján szűrje a feladatokat. Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan valósítható meg ez a funkció, hogy **hogyan szűrje a feladatokat** gyorsan és megbízhatóan.

## Gyors válaszok
- **Mit csinál az AND operátor?** Több szűrőfeltételt kombinál úgy, hogy csak azok a feladatok kerülnek visszaadásra, amelyek *mind* a feltételeknek megfelelnek.  
- **Melyik könyvtár biztosítja ezt a funkciót?** Aspose.Tasks for .NET.  
- **Szükségem van licencre?** Egy ingyenes próba verzió elegendő a kiértékeléshez; a licenc a termeléshez kötelező.  
- **Betölthetek MPP fájlt?** Igen – a `Project` osztály segítségével tölthet be egy *.mpp* fájlt.  
- **Lehetséges-e összefoglaló feladatokat szűrni?** Természetesen, egy `SummaryCondition` hozzáadásával a feltételek listájához.

## Mi a “use and operator” funkció?
A **use and operator** képesség lehetővé teszi, hogy több `ICondition<T>` megvalósítást egy `AndAllCondition<T>`-vel kapcsoljon össze. Az eredményül kapott szűrő csak azokat a feladatokat adja vissza, amelyek *minden* megadott feltételnek megfelelnek.

## Miért alkalmazzunk több feltételt?
Több feltétel alkalmazása (például „a feladat nem null” **és** „a feladat összefoglaló feladat”) pontosabb irányítást biztosít a kezelt adatok felett. Ez különösen hasznos, ha **egyedi szűrőlogikát** kell létrehozni összetett projektmenetrendekhez, vagy jelentéseket generálni, amelyek konkrét feladatsorokra fókuszálnak.

## Előfeltételek

Mielőtt elkezdené a gyakorlati példát, győződjön meg róla, hogy a következő előfeltételek teljesülnek:

1. **Alapvető C# ismeretek** – A C# programozási nyelv ismerete előnyös.  
2. **Aspose.Tasks for .NET könyvtár** – Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat [innen](https://releases.aspose.com/tasks/net/).  
3. **Integrált fejlesztői környezet (IDE)** – Telepítsen egy IDE‑t, például a Visual Studio‑t, a kódolás kényelme érdekében.  

## Namespace-ek importálása

Először importálni kell a szükséges namespace‑eket a kívánt osztályok és metódusok eléréséhez.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

Most bontsuk le a példát több lépésre, hogy a folyamatot világosan megértsük.

## 1. lépés: Projektfájl betöltése (load mpp file)

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

A `Project` osztály konstruktorával töltse be a projektfájlt, megadva a fájl elérési útvonalát. Ez a lépés bemutatja a **load mpp file** kezelését.

## 2. lépés: Az összes projektfeladat összegyűjtése

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Használja a `ChildTasksCollector` osztályt az összes feladat begyűjtéséhez a projektben.

## 3. lépés: Szűrőfeltételek definiálása

```csharp
var conditions = new List<ICondition<Task>>
{
    new NotNullCondition(),
    new SummaryCondition()
};
```

Hozzon létre egy feltételek listáját a feladatok szűréséhez. Ebben a példában olyan feladatokat szűrünk, amelyek **nem null** és **összefoglaló feladatok** – ez egy **filter summary tasks** példa.

## 4. lépés: AND operátor alkalmazása a feltételekre (apply multiple conditions)

```csharp
var joinedCondition = new AndAllCondition<Task>(conditions);
```

A feltételeket a `AndAllCondition` osztállyal kapcsolja össze, alkalmazva a **use and operator**-t minden feltételre.

## 5. lépés: Feladatok szűrése

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

Alkalmazza a kombinált feltételt a begyűjtött feladatokra a megfelelő szűrés érdekében. Ez a lépés bemutatja, **hogyan szűrje a feladatokat** egy egyesített feltétel segítségével.

## 6. lépés: Szűrt feladatok feldolgozása

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));
    // Perform operations with filtered tasks
}
```

Iteráljon a szűrt feladatokon, és végezze el a szükséges műveleteket.

## Gyakori problémák és megoldások

- **A feltétellista üres** – Győződjön meg róla, hogy legalább egy `ICondition<T>` elemet hozzáadott, mielőtt létrehozná a `AndAllCondition<T>`‑t.  
- **Nem tér vissza feladat** – Ellenőrizze, hogy a hozzáadott feltételek valóban egyeznek a projekt feladataival (például előfordulhat, hogy összefoglaló feladatokra szűr, de azok nincsenek jelen).  
- **Fájl nem található** – Ellenőrizze a `DataDir` útvonalat és a *.mpp* fájl nevét.

## Gyakran ismételt kérdések

**Q: Alkalmazhatok további feltételeket a példában bemutatottakon kívül?**  
A: Igen, definiálhat és alkalmazhat tetszőleges egyedi feltételeket a projekt igényei szerint.

**Q: Az Aspose.Tasks for .NET kompatibilis-e különböző projektfájl formátumokkal?**  
A: Igen, az Aspose.Tasks számos projektfájl formátumot támogat, például MPP, XML és CSV.

**Q: Az Aspose.Tasks támogatja-e a komplex projektütemezési algoritmusokat?**  
A: Teljes mértékben, az Aspose.Tasks fejlett funkciókat kínál a projektmenetrendek kezeléséhez, beleértve a kritikus út elemzést és az erőforrás-elosztást.

**Q: Integrálhatom az Aspose.Tasks‑t más .NET keretrendszerekkel vagy könyvtárakkal?**  
A: Igen, zökkenőmentesen integrálható más .NET keretrendszerekkel és könyvtárakkal a funkcionalitás bővítése érdekében.

**Q: Van közösségi fórum vagy támogatási csatorna az Aspose.Tasks felhasználók számára?**  
A: Igen, a [Aspose.Tasks közösségi fórumát](https://forum.aspose.com/c/tasks/15) bármilyen kérdés vagy segítségkérés esetén elérheti.

## Összegzés

Összefoglalva, az **AND operátor használata** minden feltételben az Aspose.Tasks for .NET‑el lehetővé teszi, hogy egyszerre több kritérium alapján hatékonyan szűrje a projektfeladatokat. A lépésről‑lépésre bemutatott útmutató követésével könnyedén beépítheti ezt a funkciót a projektmenedzsment munkafolyamatába, növelve a termelékenységet és a szervezettséget.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2026-03-19  
**Tesztelt verzió:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

---
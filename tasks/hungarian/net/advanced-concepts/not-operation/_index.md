---
date: 2026-03-14
description: Tanulja meg, hogyan szűrhet feladatokat a „nem” művelettel az Aspose.Tasks
  for .NET-ben, és fedezze fel, hogyan használhatja a „nem” szűrőt egy alkalmazott
  „nem” feltétellel a rugalmas feladatszűrésekhez.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Feladatok szűrése, nem művelet az Aspose.Tasks-ben
url: /hu/net/advanced-concepts/not-operation/
weight: 20
---

Make sure to keep placeholders {{CODE_BLOCK_X}} unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# feladatok szűrése NOT művelettel az Aspose.Tasks-ben

## Bevezetés

Ebben az útmutatóban megtanulja, **hogyan szűrje a feladatokat NOT művelettel** az Aspose.Tasks for .NET használatával. A NOT művelet megfordítja a szűrőfeltételt, így kiválaszthat minden olyan feladatot, amely **nem** felel meg egy adott kritériumnak. Ez a képesség elengedhetetlen, ha bizonyos elemeket ki szeretne zárni – például érték nélküli feladatokat – vagy ha extra kód írása nélkül szeretne összetett lekérdezéseket építeni.

## Gyors válaszok
- **Mi a NOT művelet feladata?** Megfordítja a szűrőfeltételt, és visszaadja azokat az elemeket, amelyek nem teljesítik az eredeti tesztet.  
- **Miért használjuk a feladatok NOT szűrését?** Egyszerűsíti a kizárási logikát és olvashatóbbá teszi a kódot.  
- **Melyik névtér biztosítja a NOT osztályt?** `Aspose.Tasks.Util`.  
- **Szükségem van licencre a termeléshez?** Igen, egy érvényes Aspose.Tasks licenc szükséges a nem próbaverzióhoz.  
- **Kombinálhatom a NOT műveletet más feltételekkel?** Természetesen—kombinálható `AndCondition`, `OrCondition` stb. használatával.

## Mi a feladatok NOT szűrése?
A **feladatok NOT szűrése** egy logikai negáció, amelyet egy feladatszűrőre alkalmazunk. A feltételnek megfelelő feladatok helyett azokra a feladatokra szűr, amelyek *nem* felelnek meg neki. Ez különösen hasznos, ha üres mezőkkel, adott állapotokkal vagy bármely más, kizárni kívánt attribútummal rendelkező feladatokat szeretne figyelmen kívül hagyni.

## Miért alkalmazzunk NOT feltételt a feladatok szűrésénél?
Az **NOT feltétel** alkalmazása csökkenti a projektadatok többszöri átfutásának szükségességét. Lehetővé teszi a tömör, karbantartható kód írását, és javítja a teljesítményt azáltal, hogy a kiértékelést az Aspose.Tasks optimalizált motorjára bízza.

## Előfeltételek

1. **Visual Studio:** Szüksége van egy működő Visual Studio telepítésre, hogy kövesse a kódrészleteket.  
2. **Aspose.Tasks for .NET:** Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a [weboldalról](https://releases.aspose.com/tasks/net/).  
3. **C# alapvető ismerete:** A C# programozási nyelv ismerete segíti a kódrészletek megértését.

## Névterek importálása

First, let's import the necessary namespaces for our code:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: Projekt és feladatok beállítása

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

Kezdetben betöltünk egy **Project2.mpp** nevű projektfájlt az Aspose.Tasks által biztosított `Project` osztállyal. Győződjön meg róla, hogy a projektfájl létezik a megadott könyvtárban.

## 2. lépés: Projekt feladatok összegyűjtése

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Itt létrehozunk egy `ChildTasksCollector` objektumot, amely összegyűjti a projekt összes feladatát. Ezután a `TaskUtils.Apply` segítségével bejárjuk a projekt feladathierarchiáját, és összegyűjtjük az összes gyermekfeladatot.

## 3. lépés: Szűrőfeltétel meghatározása

```csharp
var filter = new NullCondition();
```

Definiálunk egy szűrőfeltételt egy `NullCondition` nevű egyéni osztály segítségével. Ez a feltétel azokat a feladatokat választja ki, amelyek **null** értékkel rendelkeznek.  

> **Pro tipp:** Cserélje le a `NullCondition`-t bármely más feltételre (pl. `EqualsCondition`), ha más attribútumot szeretne célozni.

## 4. lépés: NOT művelet alkalmazása

```csharp
var condition = new Not<Task>(filter);
```

A **NOT műveletet** a szűrőfeltételre alkalmazzuk az Aspose.Tasks által biztosított `Not<T>` osztállyal. Ez megfordítja az eredeti feltételt, így a szűrő most azokat a feladatokat választja ki, amelyek **nem** null értékkel rendelkeznek. Ez a **hogyan használjuk a NOT szűrőt** technika középpontja.

## 5. lépés: Feladatok szűrése

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

A gyűjtött feladatokat a feltétel alapján szűrjük egy egyéni `Filter` metódussal. A metódus egy feladatok enumerálható gyűjteményét és egy szűrőfeltételt kap, majd visszaad egy listát a feladatok közül, amelyek megfelelnek a **NOT feltétel alkalmazásának**.

## 6. lépés: Szűrt feladatok feldolgozása

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

Végül végigiterálunk a szűrt feladatokon, és elvégezzük a kívánt műveleteket. Ebben a példában egyszerűen kiírjuk a feladatok nevét a konzolra, de ezt a blokkot kibővítheti mezők frissítésére, feladatok áthelyezésére vagy jelentések generálására.

## Gyakori felhasználási esetek

- **Kész feladatok kizárása** a függőben lévő munka listájának generálásakor.  
- **Feladatok keresése, amelyek hiányoznak egyedi mezőkből** (pl. egy null “Owner” oszlop).  
- **Kombinálás más feltételekkel** összetett lekérdezések építéséhez, például „feladatok, amelyek nem null és kezdődátuma ma előtt van”.

## Hibaelhárítás és tippek

| Probléma | Ok | Megoldás |
|----------|----|----------|
| Nincsenek visszaadott feladatok | Az eredeti feltétel túl szigorú lehet. | Ellenőrizze a feltétel logikáját, vagy teszteljen egy egyszerűbb szűrővel, például `new TrueCondition()`. |
| `NullReferenceException` | `DataDir` útvonal hibás. | Győződjön meg róla, hogy a `DataDir` a *Project2.mpp* fájlt tartalmazó mappára mutat. |
| Váratlan eredmények | `Not<T>` helytelen kombinálása más feltételekkel. | Használjon zárójeleket: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Tasks-et más .NET keretrendszerekkel?**  
A: Igen, az Aspose.Tasks támogatja a .NET Core, .NET Standard és a klasszikus .NET Framework-ot.

**Q: Van ingyenes próba verzió az Aspose.Tasks-hez?**  
A: Igen, letölthet egy ingyenes próbaverziót a [weboldalról](https://releases.aspose.com/).

**Q: Hogyan kaphatok támogatást az Aspose.Tasks-hez?**  
A: Látogasson el az [Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15) bármilyen támogatási kérdés vagy technikai segítség esetén.

**Q: Vásárolhatok ideiglenes licencet az Aspose.Tasks-hez?**  
A: Igen, ideiglenes licencet vásárolhat a [vásárlási oldalról](https://purchase.aspose.com/temporary-license/).

**Q: Hol találhatom meg az Aspose.Tasks teljes dokumentációját?**  
A: A teljes dokumentációt elérheti az [Aspose.Tasks dokumentációs oldalon](https://reference.aspose.com/tasks/net/).

## Következtetés

A **feladatok NOT szűrésének** elsajátításával és a **NOT szűrő használatának** megtanulásával a **NOT feltétel alkalmazásával**, finomhangolt irányítást kap a feladatok kiválasztásához az Aspose.Tasks-ben. Ez lehetővé teszi, hogy tisztább kódot írjon, elkerülje a manuális kizárásokat, és erőteljes projektmenedzsment eszközöket építsen.

---

**Legutóbb frissítve:** 2026-03-14  
**Tesztelve:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-03
description: Tanulja meg, hogyan lehet újraszámozni a WBS-t az Aspose.Tasks for Java-ban,
  kezelje a munkafelosztást, és hatékonyan testreszabja a WBS-kódokat lépésről‑lépésre
  bemutatott példákkal.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan lehet újraszámozni a WBS-t az Aspose.Tasks for Java-ban
url: /hu/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan számozzuk újra a WBS-t az Aspose.Tasks for Java-ban

## Introduction
Ha **hogyan számozzuk újra a WBS-t** szeretnél egy Microsoft Project fájlban az Aspose.Tasks for Java használatával, jó helyen vagy. Ez az útmutató végigvezet a meglévő WBS-kódok beolvasásán, testreszabásán, majd a hierarchia újraszámozásán, hogy a projekted rendezett maradjon. Akár egy régi ütemtervet tisztítasz meg, akár egy újat építesz fel a semmiből, ezeknek a lépéseknek a elsajátítása segít **a munka lebontási** struktúrák magabiztos kezelésében.

## Quick Answers
- **Mit csinál a WBS újraszámozása?** Újraszámolja a feladatok hierarchikus számozását, hogy tükrözze a struktúraváltozásokat.  
- **Melyik osztály végzi az újraszámozást?** `Project.renumberWBSCode`.  
- **Szükségem van licencre a kód futtatásához?** Egy érvényes Aspose.Tasks licenc szükséges a termelési környezetben.  
- **Testreszabhatom a WBS formátumot?** Igen – használhatod a `Task.set(Tsk.WBS, "...")` metódust, hogy bármilyen karakterláncot hozzárendelj.  
- **Mik a fő előfeltételek?** Java JDK, Aspose.Tasks for Java könyvtár, és egy érvényes projektfájl (.mpp).

## What is a Work Breakdown Structure (WBS)?
A Work Breakdown Structure (WBS) egy hierarchikus ábrázolása a projekt szállítmányainak és feladatainak. Minden feladat kap egy kódot (pl. 1.2.3), amely a hierarchiában elfoglalt helyét tükrözi. Az újraszámozás akkor válik szükségessé, amikor feladatokat adnak hozzá, távolítanak el vagy átrendeznek, biztosítva, hogy a kódok logikusak és könnyen olvashatóak maradjanak.

## Why manage work breakdown and customize WBS codes?
- **Átláthatóság:** A tiszta WBS-kódok egyszerűvé teszik a résztvevők számára a feladatok megtalálását.  
- **Jelentéskészítés:** Sok jelentéskészítő eszköz a konzisztens számozásra támaszkodik.  
- **Rugalmasság:** Az egyedi kódok lehetővé teszik, hogy a projekt struktúráját a belső szabványokhoz igazítsd.  

## Prerequisites
Mielőtt a kódba merülnél, ellenőrizd, hogy a következők rendelkezésre állnak:

- Java Development Kit (JDK) telepítve van a gépeden.  
- Aspose.Tasks for Java könyvtár hozzáadva a projektedhez. Letöltheted [itt](https://releases.aspose.com/tasks/java/).  

## Import Packages
Győződj meg róla, hogy importálod a szükséges csomagokat a projekt elindításához:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Read WBS Codes
Először beolvassuk a meglévő WBS-kódokat, hogy lásd, mivel dolgozol.

### Step 1: Load the Project
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Step 2: Collect Tasks
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Step 3: Parse and Customize
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

A fenti kódrészlet kiírja minden feladat aktuális WBS-ét és szintjét, majd bemutatja a **WBS-kódok testreszabását** egy új karakterlánc hozzárendelésével.

## Renumber Task WBS Codes
Most pedig ténylegesen újraszámozzuk a WBS-hierarchiát.

### Step 1: Load the Project (Renumber Example)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Step 2: Select All Tasks
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Step 3: Output Initial WBS Codes
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Step 4: Renumber WBS Codes
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Step 5: Output Updated WBS Codes
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Ezeket a lépéseket követve hatékonyan **hogyan számozzuk újra a WBS-t** bármely feladathalmazra a projektfájlodban.

## Common Issues and Solutions
- **A WBS nem változik a `set` hívás után:** Győződj meg róla, hogy a megfelelő feladatpéldányon dolgozol, és a projektet mentetted a módosítások után.  
- **A `renumberWBSCode` kivételt dob:** Ellenőrizd, hogy az azonosítók listája megegyezik a legfelső szintű feladatok számával; különben a metódus nem tudja helyesen hozzárendelni az új számokat.  
- **Hiányzó WBS értékek:** Egyes feladatok `null` WBS-sel rendelkezhetnek, ha olyan fájlból importálták őket, amely nem definiált ilyet. Használj tartalékértéket a kiírás előtt.

## Frequently Asked Questions

**Q: Hol találom meg az Aspose.Tasks for Java dokumentációját?**  
A: A dokumentáció elérhető [itt](https://reference.aspose.com/tasks/java/).

**Q: Hogyan tölthetem le az Aspose.Tasks for Java-t?**  
A: Letöltheted [itt](https://releases.aspose.com/tasks/java/).

**Q: Van ingyenes próbaverzió az Aspose.Tasks for Java-hoz?**  
A: Igen, ingyenes próbaverziót kaphatsz [itt](https://releases.aspose.com/).

**Q: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?**  
A: Látogasd meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) támogatásért.

**Q: Kaphatok ideiglenes licencet az Aspose.Tasks for Java-hoz?**  
A: Igen, ideiglenes licencet szerezhetsz [itt](https://purchase.aspose.com/temporary-license/).

**Q: Át tudom nevezni a WBS formátumot az újraszámozás után?**  
A: Természetesen. A `renumberWBSCode` meghívása után iterálhatsz a feladatokon, és alkalmazhatod a `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` kifejezést a saját elnevezési konvencióidnak megfelelően.

**Q: Az újraszámozás befolyásolja a feladatfüggőségeket?**  
A: Nem. A metódus csak a WBS karakterláncot frissíti; a feladakhivatkozások és korlátozások változatlanok maradnak.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-01-25
description: Tanulja meg, hogyan használja az Aspose Tasks Java-t a Java feladatkezeléshez,
  kezelje a kritikus és erőforrás‑alapú feladatokat projektjeiben. Javítsa a projektfolyamatokat
  ezzel az útmutatóval.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – Kritikus és munka‑alapú feladatok kezelése
url: /hu/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java:‑vezére, hogy közvetlenül a Java kódból azonosítsa és szabályozza a kritikus és erőfeszítés‑vezérelt feladatokat. Akár ütemezőt, jelentéskészítő eszközt vagy egyedi irányítópultot épít, ezen feladatjellemzők helyes kezelése döntő lehet egy a terv szerint haladó projekt és egy kontrollálhatatlanul kifutó projekt között. Ebben az útmutatóban mindent végigvezetünk, amit a kritikus és erőfeszítés‑vezérelt feladatokkal való munka során tudnia kell az Aspose Tasks Java használatával.

## Gyors válaszok
- **Mi a “kritikus” jelentése?** Egy feladat, amelynek késése meghosszabbítja a projekt befejezési dátumát.  
- **Mi a “effort‑driven” (erőfeszítés‑vezérelt) jelentése?** Egy feladat, amely automatikusan módosítja az időtartamát, amikor a munka mennyiségét változtatja.  
- **Melyik könyvtár biztosítja ezeket a funkciókat?** Aspose Tasks Java.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a kiértékeléshez megfelelő; licenc szükséges a termeléshez.  
- **Futtatható ez bármely operációs rendszeren?** Igen – a könyvtár platform‑független (Windows, Linux, macOS).

## Mik azok a kritikus és erőfeszítés‑vezérelt feladatok?
A kritikus feladatok a projekt kritikus útvonalán helyezkednek el; bármely csúszás közvetlenül befolyásolja az összmenetrendet. Az erőfeszítés‑vezérelt feladatok ezzel szemben újraszámolják az időtartamukat a hozzárendelt munka mennyisége alapján, így ideálisak azoknak az erőforrásoknak, amelyek túlórázhatnak vagy több feladat között oszthatják meg az erőfeszítést.

## Miért használjuk az Aspose Tasks Java-t ehhez?
- **Teljes .NET‑stílusú API Java-ban** – Nincs szükség nyelvváltásra.  
- **Nagy teljesítmény** – Nagy XML‑alapú projektfájlokkal dolgozik anélkül, hogy az egész fájlt a memóriába töltené.  
- **Gazdag tulajdonságkészlet** – Hozzáférés az `IS_CRITICAL`, `IS_EFFORT_DRIVEN` és számos további feladatelőíráshoz.  
- **Kereszt‑platform** – Bármely JVM‑kompatibilis környezetben fut.

## Előkövetelmények
- Aspose.Tasks for Java könyvtár: Töltse le és telepítse a könyvtárat a [Aspose.Tasks for Java dokumentációból](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): Győződjön meg róla, hogy a Java telepítve van a rendszerén.
- Integrált fejlesztői környezet (IDE): Használja a kedvenc IDE-jét Java fejlesztéshez.
- Projektfájl: Készítsen egy XML formátumú projektfájlt, amelyet a bemutatóhoz használ.

## Csomagok importálása
Java projektjében importálja a szükséges csomagokat az Aspose.Tasks for Java funkcióinak kihasználásához:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### 1. lépés: Feladatok gyűjtése a `ChildTasksCollector` használatával
Hozzon létre egy `ChildTasksCollector` példányt, amely a `TaskUtils.apply` segítségével összegyűjti az összes feladatot a gyökérfeladattól. Ez biztosítja, hogy a projekt minden feladatához hozzáférjen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### 2. lépés: Gyűjtött feladatok bejárása
Iteráljon végig az összegyűjtött feladatokon egy `for` ciklussal. Minden feladatra határozza meg, hogy erőfeszítés‑vezérelt és kritikus-e, majd írja ki a megfelelő állapotot.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

Ezeket a lépéseket követve hatékonyan kezelheti a kritikus és erőfeszítés‑vezérelt feladatokat projektjeiben a **aspose tasks java** segítségével.

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| `NullPointerException` on `tsk.get(Tsk.IS_CRITICAL)` | A feladat nem rendelkezik a tulajdonsággal beállítva (pl. összegző feladat). | Ellenőrizze a `tsk.get(Tsk.TASK_TYPE)` értéket a jelző elérése előtt, vagy szűrje ki az összegző feladatokat. |
| Project file not found | Helytelen `dataDir` útvonal vagy hiányzó fájlkiterjesztés. | `Paths.get(dataDir, "project.xml").toString()` használata és ellenőrizze, hogy a fájl létezik. |
| License not applied | A könyvtár értékelő módban fut, ami korlátozza a funkciókat. | Töltse be a licencfájlt a `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kóddal a `Project` objektum létrehozása előtt. |

## Gyakran ismételt kérdések
### K: Használhatom az Aspose.Tasks for Java-t Windows és Linux környezetben is?
V: Igen, az Aspose.Tasks for Java platform‑független, és használható Windows és Linux környezetben egyaránt.

### K: a [itt](https://releases.aspose.com/) érhet el.

### K: Hol találok támogatást az Aspose.Tasks for Java-hoz?
V: Látogassa meg a [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) közösségi támogatásért és megbeszélésekért.

### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java-hoz?
V: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhet.

### K: Hol vásárolhatok Aspose.Tasks for Java-t?
V: Az [vásárlási oldalon](https://purchase.aspose.com/buy) vásárolhat.

---

**Utoljára frissítve:** 2026-01-25  
**Tesztelve:** Aspose.Tasks Java 24.11 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
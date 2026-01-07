---
date: 2026-01-07
description: Ismerje meg, hogyan adhat hozzá erőforrást a projekthez, és kezelheti
  az erőforrás‑kiosztások szintezési késleltetési tulajdonságait az Aspose.Tasks for
  Java segítségével.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan adjunk erőforrást a projekthez, és kezeljük a szintezési késleltetés
  tulajdonságait az Aspose.Tasks-ben
url: /hu/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá erőforrást a projekthez, és kezeljük a szintezési késleltetés tulajdonságait az Aspose.Tasks-ben

## Bevezetés
Ebben az oktatóanyagban megtanulja, **hogyan adjon hozzá erőforrást a projekthez**, miközben kezeli a szintezési késleltetés tulajdonságait az erőforrás‑hozzárendelésekhez az Aspose.Tasks for Java segítségével. Akár ütemező motor fejlesztésén dolgozik, akár a projekt frissítéseit automatizálja, ezen lépések elsajátítása lehetővé teszi, hogy a projekt adatait pontosan tartsa, anélkül, hogy a Microsoft Project telepítve lenne.

## Gyors válaszok
- **Mit jelent a „add resource to project”?** Új erőforrás bejegyzést hoz létre, amely feladatokhoz rendelhető.  
- **Beállíthatok szintezési késleltetést a hozzárendelés után?** Igen, a `Asn.DELAY` vagy `Asn.LEVELING_DELAY` mezők használatával.  
- **Szükségem van licencre a kód futtatásához?** Ingyenes próba verzió fejlesztéshez elegendő; a termeléshez fizetett licenc szükséges.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.  
- **Ez kompatibilis minden MS Project fájlformátummal?** Az Aspose.Tasks támogatja a .MPP, .XML, .XER és további formátumokat.

## Mi a „add resource to project” az Aspose.Tasks-ben?
Erőforrás hozzáadása egy projekthez azt jelenti, hogy egy `Resource` objektumot hozunk létre a `Project` modellben. Ez az objektum később a `ResourceAssignment` segítségével kapcsolható feladatokhoz, lehetővé téve a munka, költségek és szintezési beállítások nyomon követését.

## Miért kezeljük a szintezési késleltetés tulajdonságait?
A szintezési késleltetés segít az ütemezőnek elosztani a munkát, ha az erőforrások túlterheltek. Késleltetés beállításával azt mondja a motornak, hogy halassza későbbre a hozzárendelés kezdését, elkerülve a konfliktusokat és a projekt reálisabbá tételét.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a rendszerén telepítve van a Java JDK. Letöltheti és telepítheti a [weboldalról](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java könyvtár: Töltse le az Aspose.Tasks for Java könyvtárat a [letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először importálja a szükséges csomagokat a Java projektjébe az Aspose.Tasks funkciók használatához:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 1. lépés: Projekt objektum létrehozása
Hozzon létre egy `Project` objektumot, amely az összes feladat, erőforrás és hozzárendelés tárolója lesz:
```java
Project prj = new Project();
```

## 2. lépés: Feladat létrehozása
Adjon egy feladatot a projekthez. Ez bemutatja, hogyan **adjunk hozzá feladatot** programozottan:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 3. lépés: Feladat kezdő dátumának és időtartamának beállítása
Határozza meg, mikor kezdődik a feladat és mennyi ideig tart:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 4. lépés: Erőforrás hozzáadása
Most **erőforrást adunk hozzá a projekthez** egy új `Resource` bejegyzés létrehozásával:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 5. lépés: Erőforrás hozzárendelés létrehozása
Kapcsolja össze a feladatot és az újonnan hozzáadott erőforrást:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 6. lépés: Szintezési késleltetés beállítása
Állítsa be a szintezési késleltetést a hozzárendeléshez. Ha nullára állítja, nincs további késleltetés, de szükség szerint módosíthatja az értéket:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 7. lépés: Eredmények megjelenítése
Nyomtassa ki a fontos tulajdonságokat, hogy ellenőrizze, minden helyesen lett beállítva:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Gyakori hibák és tippek
- **Hiba:** Ha elfelejti beállítani a feladat kezdő dátumát, a hozzárendelés a projekt kezdőpontjára alapulhat.  
- **Tipp:** Használja a `prj.getDuration(value, TimeUnitType.Day)` metódust a késleltetés finomságának szabályozásához.  
- **Tipp:** Több erőforrás hozzáadása után hívja meg a `prj.updateResourceAssignments()` metódust, hogy az ütemező újraszámolja a szintezést.

## Következtetés
Ezeknek a lépéseknek a követésével most már tudja, **hogyan adjon hozzá erőforrást a projekthez**, hogyan rendelje hozzá egy feladathoz, és hogyan kezelje a szintezési késleltetés tulajdonságait az Aspose.Tasks for Java segítségével. Ez a tudás lehetővé teszi, hogy robusztus projekt‑automatizálási megoldásokat építsen, amelyek összhangban maradnak a valós erőforrás‑korlátozásokkal.

## Gyakran ismételt kérdések
### K: Használhatom az Aspose.Tasks-et más Java könyvtárakkal?
A: Igen, az Aspose.Tasks integrálható más Java könyvtárakkal a projektmenedzsment képességek bővítése érdekében.

### K: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?
A: Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különböző verzióit, biztosítva a kompatibilitást különböző környezetekben.

### K: Hol találok további támogatást az Aspose.Tasks-hez?
A: Támogatást és forrásokat a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) talál.

### K: Kipróbálhatom az Aspose.Tasks-et vásárlás előtt?
A: Igen, ingyenes próbaverziót szerezhet az Aspose.Tasks‑ből a [kiadási oldalról](https://releases.aspose.com/).

### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks-hez?
A: Ideiglenes licencet kérhet a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalról értékelési célokra.

## További gyakran ismételt kérdések

**Q: Mi történik, ha nem nulla szintezési késleltetést állítok be?**  
A: Az ütemező a megadott időtartammal elhalasztja a hozzárendelés kezdését, segítve a túlterhelések megoldását.

**Q: Vissza tudom-e olvasni a szintezési késleltetést a projekt mentése után?**  
A: Igen, újra megnyithatja a projektfájlt és kiolvashatja a `Asn.DELAY` tulajdonságot a hozzárendelésből.

**Q: Van mód arra, hogy egyszerre minden hozzárendelésre alkalmazzam a szintezési késleltetést?**  
A: Végigiterálhat a `prj.getResourceAssignments()` elemein, és egy ciklusban beállíthatja a késleltetést minden hozzárendelésnél.

---

**Utoljára frissítve:** 2026-01-07  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
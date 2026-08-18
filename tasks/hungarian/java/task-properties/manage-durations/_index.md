---
date: 2026-02-20
description: Fedezze fel, hogyan adhat feladatot egy projekthez, és kezelheti az időtartamokat
  az Aspose.Tasks for Java segítségével. Tanulja meg, hogyan állíthat be időtartamot,
  és hogyan konvertálhatja azt egyszerűen.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Feladat hozzáadása a projekthez és időtartamok kezelése az Aspose.Tasks segítségével
url: /hu/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladat hozzáadása a projekthez és időtartamok kezelése az Aspose.Tasks segítségével

## Bevezetés
Ebben az útmutatóban megtanulja, **hogyan adjon feladatot a projekthez**, és hogyan szabályozza annak időtartamát az Aspose.Tasks for Java használatával. Akár új projekttervező eszközt épít, akár egy meglévő megoldást bővít, a feladat‑időtartam kezelése elengedhetetlen a pontos ütemezéshez és jelentéskészítéshez.

## Gyors válaszok
- **Mit jelent a „feladat hozzáadása a projekthez”?** Új feladatobjektumot hoz létre a projekt gyökerénél vagy egy adott összegző feladat alatt.  
- **Melyik osztály képviseli az időtartamot?** `com.aspose.tasks.Duration`.  
- **Hogyan állítsuk be az időtartamot?** Használja a `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))` metódust.  
- **Átkonvertálhatok egy időtartamot más egységre?** Igen, hívja a `duration.convert(TimeUnitType.Hour)` vagy bármely más `TimeUnitType` metódust.  
- **Szükség van licencre a termeléshez?** Egy érvényes Aspose.Tasks licenc szükséges kereskedelmi felhasználáshoz.

## Mi az a „feladat hozzáadása a projekthez”?
A feladat hozzáadása a projekthez azt jelenti, hogy létrehoz egy `Task` objektumot, és azt a projekt feladat-hierarchiájához csatolja. Ez a művelet az első lépés, mielőtt meghatározná a munkát, erőforrásokat vagy az időtartamot az adott feladathoz.

## Miért kezeljük a feladat időtartamait?
A pontos időtartamok reális ütemterveket, erőforrás-elosztást és kritikus út elemzést biztosítanak. Az Aspose.Tasks segítségével programozottan beállíthat, olvashat, konvertálhat és módosíthat időtartamokat, így teljes irányítást kap a projekt ütemezése felett.

## Prerequisites
Mielőtt elkezdené, győződjön meg róla, hogy a következők rendelkezésre állnak:

- Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a gépén. Letöltheti [itt](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Töltse le és illessze be az Aspose.Tasks könyvtárat a projektjébe. A könyvtárat megtalálja [itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Java projektjében importálja a szükséges csomagokat az Aspose.Tasks használatához:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 1. lépés: A projekt beállítása
```java
// Create a new project
Project project = new Project();
```

## 2. lépés: Új feladat hozzáadása (feladat hozzáadása a projekthez)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Hogyan állítsuk be az időtartamot
Most, hogy a feladat létezik, meghatározhatja annak hosszát. Alapértelmezés szerint az időtartamok napokban vannak kifejezve.

## 3. lépés: Feladat időtartamának lekérése és konvertálása
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Hogyan konvertáljuk az időtartamot
A `convert` metódus lehetővé teszi, hogy egy `Duration`‑t egy `TimeUnitType`‑ról egy másikra (például nap → óra, hét → nap) átalakítson.

## 4. lépés: Feladat időtartamának frissítése 1 hétre
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## 5. lépés: Feladat időtartamának csökkentése
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Ezeknek a lépéseknek a követésével sikeresen **feladatot adott hozzá egy projekthez**, és az időtartamát az Aspose.Tasks for Java segítségével kezelte.

## Gyakori hibák és tippek
- **Hiba:** Az időtartam átalakításának elhagyása a számítások előtt helytelen eredményekhez vezethet. Mindig ellenőrizze az egységet a `duration.getTimeUnit()` metódussal.
- **Tipp:** Használja a `project.getDuration(value, TimeUnitType)` metódust, hogy a kívánt egységben hozza létre az időtartamokat, a későbbi konvertálás helyett.
- **Hiba:** Negatív időtartam beállítása kivételt dob. Győződjön meg a bemeneti értékek validálásáról.

## Következtetés
Ebben az útmutatóban megtanulta, hogyan **adjunk feladatot a projekthez**, olvassa el annak alapértelmezett időtartamát, **állítsa be az időtartamot**, és **konvertálja az időtartamot** különböző időegységek között. Most már beépítheti ezeket a technikákat nagyobb ütemező alkalmazásokba a pontos projekttervezés érdekében.

## Gyakran Ismételt Kérdések
### Kompatibilis-e az Aspose.Tasks minden Java verzióval?
Az Aspose.Tasks kompatibilis a Java 6‑os és újabb verzióival.

### Használhatom az Aspose.Tasks‑et kereskedelmi projektekhez?
Igen, az Aspose.Tasks használható személyes és kereskedelmi projektekhez egyaránt. A licenc részleteiért látogasson el [ide](https://purchase.aspose.com/buy).

### Hol találok további támogatást és erőforrásokat?
Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi támogatás és a megbeszélések céljából.

### Hogyan szerezhetek ideiglenes licencet tesztelési célokra?
Ideiglenes licencet szerezhet [ide](https://purchase.aspose.com/temporary-license/) a tesztelés és értékelés céljából.

### Elérhető-e ingyenes próba az Aspose.Tasks‑hez?
Igen, az ingyenes próbaverziót [ide](https://releases.aspose.com/) érheti el, hogy felfedezze az Aspose.Tasks-et vásárlás előtt.

## Gyakran Ismételt Kérdések

**Q: Hogyan változtathatom meg egy feladat időtartamát, miután már be lett állítva?**  
A: Szerezze meg a jelenlegi időtartamot a `task.get(Tsk.DURATION)` metódussal, módosítsa (például `add`, `subtract` vagy `convert`), majd állítsa vissza a `task.set(Tsk.DURATION, newDuration)` segítségével.

**Q: Beállíthatok időtartamot percekben?**  
A: Igen, használja a `TimeUnitType.Minute` értéket a `project.getDuration(value, TimeUnitType.Minute)` hívásakor.

**Q: Az időtartam módosítása automatikusan frissíti a feladat kezdő‑ és befejező dátumát?**  
A: Csak akkor, ha a projekt ütemezési módja automatikusra van állítva. Ellenkező esetben újraszámolhatja az ütemtervet a `project.calculateCriticalPath()` metódussal.

**Q: Lehet-e az időtartamot nyers számként lekérni?**  
A: Hívja a `duration.getTimeSpan()` metódust, hogy megkapja a numerikus értéket az aktuális időegységben.

**Q: Mi történik, ha a jelenlegi időtartamnál nagyobb értéket vonok le?**  
A: Az API `ArgumentOutOfRangeException` kivételt dob. Mindig ellenőrizze, hogy a kapott időtartam pozitív maradjon.

---

**Legutóbb frissítve:** 2026-02-20  
**Tesztelve:** Aspose.Tasks for Java (legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
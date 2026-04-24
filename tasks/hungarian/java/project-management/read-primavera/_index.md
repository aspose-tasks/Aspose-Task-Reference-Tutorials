---
date: 2026-04-24
description: Tanulja meg, hogyan használja az Aspose.Tasks Java-t a Primavera XML
  importálásához az MS Projectbe, lehetővé téve a zökkenőmentes adatcserét és a jobb
  projektmenedzsmentet.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Projekt beolvasása a Primavera‑ból az Aspose.Tasks‑ben
second_title: Aspose.Tasks Java API
title: aspose tasks java – Primavera XML beolvasása MS Project-be
url: /hu/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Olvassa be az MS Projectet a Primavera-ból az Aspose.Tasks for Java segítségével

## Bevezetés
A mai gyors tempójú projektmenedzsment világában gyakran szükség van a menetrendek áthelyezésére a Primavera P6 és a Microsoft Project között anélkül, hogy bármilyen részletet elveszítenénk. Ez az útmutató bemutatja, **hogyan kell beolvasni a Primavera XML** fájlokat, és importálni őket az MS Projectbe a **aspose tasks java** használatával. A útmutató végére képes lesz a Primavera‑specifikus feladatjellemzőket egy Java alkalmazásba átemelni, ezzel egyetlen igazságforrást biztosítva az elemzéshez, jelentéskészítéshez vagy további automatizáláshoz.

## Gyors válaszok
- **Mit csinál az Aspose.Tasks for Java?** Olvas és ír számos projektfájlformátumot, beleértve a Primavera XML-t és a Microsoft Projectet (MPP).  
- **Szükségem van licencre?** Egy ingyenes próba a kiértékeléshez működik; licenc szükséges a termeléshez.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb szükséges.  
- **Importálhatok más formátumokat is a Primavera XML mellett?** Igen, az aspose tasks java támogatja az MPP-t, XML-t és még sok mást.  
- **Ez a megközelítés alkalmas nagy vállalati projektekhez?** Teljesen – az Aspose.Tasks magas teljesítményű, vállalati szintű forgatókönyvekre lett tervezve.

## aspose tasks java – Primavera XML beolvasása
A Primavera XML beolvasása azt jelenti, hogy az Oracle Primavera P6 XML exportját elemzi a projektmenetrend adatok – feladatok, időtartamok, erőforrások és a Primavera‑specifikus attribútumok – visszanyerésére, hogy azokat más eszközök, például a Microsoft Project felhasználhassa.

## Miért használjuk az Aspose.Tasks for Java-t a Primavera XML beolvasásához?
- **Teljes pontosság:** Minden Primavera‑specifikus tulajdonság megmarad.  
- **Nincs külső függőség:** Tiszta Java könyvtár, nincs szükség Primavera vagy MS Project telepítésre.  
- **Skálázható:** Nagy, több ezer feladatot tartalmazó projekteket hatékonyan kezel.  
- **Keresztplatformos:** Windows, Linux és macOS rendszereken működik.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy a következőkkel rendelkezik:
1. **Java Development Kit (JDK)** – Java 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java** – Töltse le innen: [here](https://releases.aspose.com/tasks/java/).  
3. Egy Primavera XML fájl (pl. `PrimaveraProject.xml`), amelyet be szeretne olvasni.

## Hogyan olvassuk be a projektfájlt Java-val az Aspose.Tasks segítségével?
Az alábbi lépésről‑lépésre útmutató végigvezeti a teljes folyamaton.

### Csomagok importálása
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### 1. lépés: Adatkatalógus beállítása
```java
String dataDir = "Your Data Directory";
```
Cserélje le a `"Your Data Directory"`-t a teljes útra, ahol a Primavera XML fájlja található.

### 2. lépés: Projekt beolvasása Primavera XML-ből
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Frissítse a `"PrimaveraProject.xml"`-t a Primavera export tényleges fájlnevével.

### 3. lépés: Feladatok bejárása és Primavera‑specifikus tulajdonságok lekérése
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Ez a ciklus kiírja minden feladat Primavera‑specifikus részleteit, például az Activity ID-t, a WBS-sorozatot, időtartam típusokat, költség bontásokat és egyebeket.

## Gyakori problémák és megoldások
- **File not found hiba:** Ellenőrizze, hogy a `dataDir` útvonal elválasztóval (`/` vagy `\\`) végződik-e, és hogy az XML fájlnév helyes.  
- **Hiányzó Primavera tulajdonságok:** Győződjön meg róla, hogy az XML minden szükséges mezővel exportálva lett; a régebbi Primavera verziók kihagyhatnak bizonyos attribútumokat.  
- **Teljesítmény nagy fájloknál:** Fontolja meg a JVM heap méretének növelését (`-Xmx2g` vagy nagyobb) tízezrek feladatát tartalmazó projektekhez.

## Gyakran Ismételt Kérdések
### K: Módosíthatom a Primavera‑specifikus feladattulajdonságokat az Aspose.Tasks for Java segítségével?
V: Igen, az Aspose.Tasks for Java API-kat biztosít a Primavera‑specifikus feladattulajdonságok módosításához, ahogy szükséges.

### K: Támogatja-e az Aspose.Tasks for Java más projektfájlformátumok beolvasását?
V: Igen, az Aspose.Tasks for Java támogatja különböző projektfájlformátumok beolvasását, beleértve az MPP-t, XML-t és a Primavera XML-t.

### K: Alkalmas-e az Aspose.Tasks for Java vállalati szintű projektmenedzsment alkalmazásokhoz?
V: Teljesen, az Aspose.Tasks for Java robusztus funkciókat és skálázhatóságot kínál, így alkalmas vállalati szintű projektmenedzsment alkalmazásokhoz.

### K: Kinyerhetek erőforrás-információkat Primavera projektekből az Aspose.Tasks for Java segítségével?
V: Igen, az Aspose.Tasks for Java lehetővé teszi erőforrás-információk kinyerését a feladatok részleteivel együtt Primavera projektekből.

### K: Hol találok további támogatást vagy dokumentációt az Aspose.Tasks for Java-hoz?
V: A [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) oldalon megtalálja a részletes dokumentációt és a fórumokat a támogatáshoz.

## Következtetés
Most már megtanulta, **hogyan kell beolvasni a primavera xml** fájlokat, és részletes feladatinformációkat egy Java alkalmazásba átemelni a **aspose tasks java** segítségével. Ez a képesség áthidalja a szakadékot a Primavera és a Microsoft Project között, teljes átláthatóságot biztosítva a platformok között, és növelve a projektmenedzsment hatékonyságát.

---

**Legutóbb frissítve:** 2026-04-24  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
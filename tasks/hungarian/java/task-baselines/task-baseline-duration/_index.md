---
date: 2026-01-23
description: Tanulja meg, hogyan állíthatja be az alapvonal időtartamát, és hogyan
  hozhat létre projektpéldányt az Aspose.Tasks for Java használatával. Ez a lépésről‑lépésre
  útmutató segít hatékonyan kezelni a feladat alapvonalakat.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Hogyan állítsuk be az alapvonal időtartamát az Aspose.Tasks Java-ban
url: /hu/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be az alapvonal időtartamát az Aspose.Tasks for Java-ban

## Bevezetés
Az alapvonal beállítása alapvető lépés a projekt előrehaladásának nyomon követéséhez az eredeti tervhez képest. Ebben az útmutatóban megtanulja, hogyan **állítsa be az alapvonal** időtartamát a feladatokhoz a Microsoft Projectben az Aspose.Tasks Java könyvtár segítségével, és megtudja, miért takaríthat meg időt és fejfájást, ha korán létrehozza az alapvonalat.

## Gyors válaszok
- **Mi jelent a „set baseline”?** Rögzíti egy feladat eredeti kezdési, befejezési és időtartam adatait, hogy a jövőbeli változásokat össze tudja hasonlítani.  
- **Melyik Aspose.Tasks osztály hoz létre projektet?** A `Project` osztály – megtanulja, hogyan **hozzon létre projektpéldányt** helyesen.  
- **Szükségem van licencre a kód futtatásához?** Egy ingyenes értékelő licenc teszteléshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Lekérhetek köztes alapvonalakat?** Igen, az Aspose.Tasks lehetővé teszi a köztes alapvonalak és azok rögzített költségeinek lekérdezését.  
- **Milyen Java verzió szükséges?** A Java 8 vagy újabb ajánlott.

## Mi az a feladat alapvonal, és miért kell beállítani?
A feladat alapvonal rögzíti a tervezett ütemtervet (kezdő dátum, befejező dátum és időtartam) egy adott időpontban. Az alapvonal beállításával egy referencia pontot hoz létre, amely megkönnyíti a menetrendelt eltérések, költségtúllépések és erőforrás‑túlterhelés észlelését a projekt előrehaladtával.

## Miért használja az Aspose.Tasks-et az alapvonal kezeléséhez?
- **Teljes .mpp kompatibilitás** – natív Microsoft Project fájlok olvasása és írása Office telepítése nélkül.  
- **Gazdag API** – programozottan hozzáférhet az alapvonal adatokhoz, köztes alapvonalakhoz és idő‑fázisos információkhoz.  
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken bármely szabványos JDK-val.

## Előfeltételek
1. **Java fejlesztői környezet** – JDK 8+ telepítve és konfigurálva.  
2. **Aspose.Tasks for Java** – töltse le a könyvtárat [itt](https://releases.aspose.com/tasks/java/).  
3. **IDE vagy build eszköz** – Maven, Gradle vagy bármely kedvelt IDE.

## Csomagok importálása
Először importálja a szükséges osztályokat a Java projektjébe:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## 1. lépés: Projektpéldány létrehozása
A projektpéldány létrehozása minden további művelet alapja. Ez a lépés megmutatja, hogyan **hozzon létre projektpéldányt** az Aspose.Tasks használatával:

```java
Project project = new Project();
```

## 2. lépés: Feladat alapvonal létrehozása
Adjon hozzá egy új feladatot a projekt gyökeréhez, és állítsa be az alapvonalát. Ez rögzíti a feladat eredeti ütemtervét:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 3. lépés: Feladat alapvonal információk megjelenítése
Hívja le a most létrehozott alapvonalat, és írja ki a kulcsfontosságú tulajdonságait. Ez segít ellenőrizni, hogy az alapvonal helyesen lett beállítva:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 4. lépés: Köztes alapvonal és rögzített költség ellenőrzése
Ha köztes alapvonalakkal dolgozik, lekérdezheti, hogy a jelenlegi alapvonal köztes-e, és van-e hozzá kapcsolódó rögzített költség:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## 5. lépés: Idő‑fázisos adatok kiírása
Az idő‑fázisos adatok megmutatják, hogyan oszlik el az alapvonal az időben. Iteráljon a gyűjteményen, hogy megvizsgálja az egyes bejegyzéseket:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Ezeknek a lépéseknek a követésével **beállíthatja az alapvonal** időtartamát bármely feladathoz, és részletes alapvonal információkat kérhet le az Aspose.Tasks for Java segítségével.

## Gyakori problémák és megoldások
- **Az alapvonal nem jelenik meg az MS Projectben:** Győződjön meg róla, hogy a `project.setBaseline(BaselineType.Baseline)` **a feladat hozzáadása után** lett meghívva.  
- **NullPointerException a `getBaselines()` hívásakor:** Ellenőrizze, hogy a feladat a projekthez lett-e hozzáadva az alapvonal beállítása előtt.  
- **Időegység eltérés:** Használja a `TimeUnitType`‑ot az időtartam helyes formázásához, különösen egyedi naptárak esetén.

## GYIK
### Mi az a feladat alapvonal az MS Projectben?
Az MS Projectben a feladat alapvonal egy pillanatfelvétel a feladat kezdeti tervezett ütemtervéről, beleértve a kezdő dátumot, befejező dátumot és időtartamot.

### Miért fontos a feladat alapvonalak kezelése?
A feladat alapvonalak kezelése segít összehasonlítani a tervezett ütemtervet a projekt tényleges előrehaladásával, ezáltal jobb nyomon követést és döntéshozatalt tesz lehetővé.

### Módosíthatom a feladat alapvonalat, miután be lett állítva?
Igen, módosíthatja a feladat alapvonalakat az MS Projectben a projekt terv változásainak tükrözésére. Azonban fontos dokumentálni minden eltérést az eredeti alapvonaltól.

### Támogatja az Aspose.Tasks más projektmenedzsment funkciókat?
Igen, az Aspose.Tasks számos projektmenedzsment funkciót kínál, beleértve a feladat ütemezést, erőforrás‑elosztást és Gantt-diagram generálást.

### Hol találok támogatást az Aspose.Tasks‑hez?
Támogatást az Aspose.Tasks‑hez a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) talál, ahol kérdéseket tehet fel és más felhasználókkal léphet kapcsolatba.

## További gyakran ismételt kérdések
**Q: Kell minden feladatra külön meghívni a `setBaseline`‑t?**  
A: Nem. A `project.setBaseline(BaselineType.Baseline)` meghívása egyszerre rögzíti az alapvonalat a projekt összes feladata számára.

**Q: Hogyan állíthatok be köztes alapvonalat egy konkrét feladathoz?**  
A: Használja a `project.setBaseline(BaselineType.Baseline1)` (vagy Baseline2‑Baseline10) parancsot a feladat ütemezésének frissítése után.

**Q: Lehet exportálni az alapvonal adatokat CSV‑be?**  
A: Igen. Iteráljon a `task.getBaselines()`‑en, és írja a kívánt mezőket egy CSV fájlba a szabványos Java I/O használatával.

**Q: Olvashatok meglévő .mpp fájlt, amely már tartalmaz alapvonalakat?**  
A: Természetesen. Töltse be a fájlt a `new Project("myproject.mpp")` segítségével, majd a fenti módon férjen hozzá minden feladat alapvonalához.

**Q: Kezeli az Aspose.Tasks a több‑projekt fájlokat?**  
A: Az Aspose.Tasks egy‑projekt .mpp fájlokkal dolgozik. Több projekt esetén programozottan kombinálja a projekteket.

---

**Utoljára frissítve:** 2026-01-23  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
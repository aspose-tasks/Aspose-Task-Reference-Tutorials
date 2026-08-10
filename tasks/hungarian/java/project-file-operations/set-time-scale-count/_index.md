---
date: 2026-03-29
description: Ismerje meg, hogyan hozhat létre projekt PDF‑fájlokat, miközben testreszabja
  a Gantt-diagram időskálájának számát az Aspose.Tasks for Java segítségével. Ez az
  útmutató lépésről lépésre bemutatja, hogyan exportálhatja a Gantt‑diagramot PDF‑be
  teljes irányítással.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt PDF létrehozása – Gantt-diagram időskálájának testreszabása
url: /hu/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt PDF létrehozása – Gantt-diagram időskála testreszabása

## Bevezetés
Ha **projekt PDF** fájlokat kell létrehoznod, amelyek tökéletesen hangolt Gantt-diagramot tükröznek, az időskála számának szabályozása a kulcs. Az Aspose.Tasks for Java-val programozottan beállíthatod az alsó és középső időskála szinteket, elrejtheted a jelölőket, majd **projekt mentése PDF-ként** a könnyű terjesztés érdekében. Ebben az útmutatóban mindent végigvezetünk, amire szükséged van – a fejlesztői környezet beállításától a testreszabott Gantt-nézetet bemutató kifinomult PDF generálásáig.

## Gyors válaszok
- **Mi jelent a „Gantt-diagram testreszabása”?** Az időskála szintek, színek és elrendezés módosítása, hogy megfeleljenek a jelentési igényeidnek.  
- **Melyik API metódus állítja be az alsó szint számát?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Generálhatok PDF-et közvetlenül a projektből?** Igen – használd a `project.save(..., SaveFileFormat.Pdf)` metódust.  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges; ingyenes próba verzió elérhető.  
- **Melyik Java verzió támogatott?** A Java 8 vagy újabb működik a legújabb Aspose.Tasks könyvtárral.

## Mi az a „Gantt-diagram testreszabása” az Aspose.Tasks-ben?
A Gantt-diagram testreszabása azt jelenti, hogy programozottan módosítod a vizuális elemeit – például az időskála intervallumokat, jelölőket és feladatsávokat – hogy a diagram megfeleljen annak, ahogyan **a projekt vizualizációját** szeretnéd kezelni. Az időskála számának módosításával szabályozhatod, hogy hány nap, hét vagy hónap legyen egy szegmens, ezáltal a diagram érthetőbbé válik különböző közönségek számára.

## Miért hozunk létre projekt PDF-et testreszabott Gantt-diagrammal?
- **Érintetteknek készült kimenet:** A PDF univerzálisan megtekinthető, biztosítva, hogy mindenki ugyanazt az ütemterv elrendezést lássa.  
- **Nyomtatásra alkalmas:** Az időskála szintek pontos szabályozása megakadályozza a zsúfolt vagy félreérthető nyomatokat.  
- **Automatizálás:** A PDF generálás integrálása CI csővezetékekbe vagy jelentési szolgáltatásokba nulla manuális erőfeszítéssel.  

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

1. **Java fejlesztői környezet** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Tasks for Java könyvtár** – Töltsd le [innen](https://releases.aspose.com/tasks/java/).  
3. **Alap Java ismeretek** – Ismerd a Java szintaxist és az objektum‑orientált koncepciókat.

## Csomagok importálása
Importáld a szükséges osztályokat a Java projektedbe:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Adatkönyvtár beállítása
Határozd meg, hogy a projekt fájlok honnan lesznek beolvasva és hová lesznek írva:

```java
String dataDir = "Your Data Directory";
```

Cseréld ki a `"Your Data Directory"` értéket a géped abszolút útvonalára.

### 2. lépés: Új projekt példány létrehozása
Hozz létre egy új `Project` objektumot, amely tartalmazni fogja az összes feladatot és nézetbeállítást:

```java
Project project = new Project();
```

### 3. lépés: Gantt-diagram nézet konfigurálása
Hozz létre egy `GanttChartView` objektumot – itt **generálod a Gantt nézet Java** kódot a diagram megjelenésének szabályozásához:

```java
GanttChartView view = new GanttChartView();
```

### 4. lépés: Időskála szám beállítása az alsó szinthez
Állítsd be az alsó szintet, hogy két intervallumot mutasson, és rejtsd el a jelölőket:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 5. lépés: Időskála szám beállítása a középső szinthez
Alkalmazd ugyanazt a konfigurációt a középső szintre:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 6. lépés: Testreszabott nézet hozzáadása a projekthez
Csatold a most konfigurált nézetet a `Project` példányhoz:

```java
project.getViews().add(view);
```

### 7. lépés: Minta feladatok hozzáadása (tesztadatok)
Hozz létre néhány feladatot meghatározott időtartamokkal, hogy bemutasd a testreszabott Gantt-diagramot:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 8. lépés: Projekt mentése PDF-ként
Végül exportáld a projektet – beleértve a **testreszabott Gantt-diagramot** – PDF fájlba:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Az eredményül kapott PDF bemutatja, hogyan lettek az alsó és középső időskála szintek **testreszabva**, így az érintettek számára egy tiszta, nyomtatható ütemterv nézetet biztosít.

## Gyakori problémák és hibaelhárítás
- **A PDF üres** – Győződj meg arról, hogy a `dataDir` útvonal fájlelválasztóval (`/` vagy `\`) végződik, és a könyvtár létezik.  
- **A jelölők még mindig megjelennek** – Ellenőrizd, hogy a `setShowTicks(false)` mindkét szinten meghívásra került.  
- **Az időtartam nem alkalmazott** – Erősítsd meg, hogy a `TimeUnitType.Hour` (vagy a megfelelő egység) használatával hozod létre az időtartamokat.

## Gyakran ismételt kérdések

**Q: Az Aspose.Tasks for Java képes nagy méretű projektfájlok kezelésére?**  
A: Igen, a könyvtár optimalizált a nagy mennyiségű projektadat magas teljesítményű feldolgozására.

**Q: Az Aspose.Tasks for Java kompatibilis különböző Java IDE-kkel?**  
A: Teljesen – zökkenőmentesen működik az Eclipse, IntelliJ IDEA, NetBeans és más népszerű IDE-k esetén.

**Q: Testreszabhatom a Gantt-diagramok megjelenését az időskála beállításokon túl?**  
A: Igen, az Aspose.Tasks kiterjedt stílusbeállítási lehetőségeket kínál, például sávszínek, betűtípusok és rácsvonalak.

**Q: Elérhető próba verzió az Aspose.Tasks for Java-hoz?**  
A: Igen, ingyenes próba verziót kaphatsz [innen](https://releases.aspose.com/).

**Q: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?**  
A: Támogatást és segítséget az Aspose.Tasks fórumon találsz [itt](https://forum.aspose.com/c/tasks/15).

**Q: Hogyan változtathatom programozottan a Gantt-diagram háttérszínét?**  
A: Használd a `view.getGanttChartProperties().setBackgroundColor(Color)` metódust a `java.awt.Color` importálása után.

## Összegzés
A lépések követésével megtanultad, hogyan **hozz létre projekt PDF** fájlokat egy teljesen testreszabott Gantt-diagram időskálával, hogyan javíthatod a **projekt vizualizációját**, és hogyan **mentheted a projektet PDF-ként** az Aspose.Tasks for Java segítségével. Ez a megközelítés teljes irányítást ad a vizuális kimenet felett, megkönnyítve a tiszta, professzionális ütemtervek megosztását a csapatoddal vagy ügyfeleiddel.

---

**Utolsó frissítés:** 2026-03-29  
**Tesztelve:** Aspose.Tasks for Java (legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
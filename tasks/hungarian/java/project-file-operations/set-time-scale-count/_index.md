---
date: 2025-12-21
description: Ismerje meg, hogyan testreszabhatja a Gantt-diagram nézeteket, kezelheti
  a projekt megjelenítését, és mentheti a projektet PDF formátumban az Aspose.Tasks
  for Java segítségével. Állítsa be könnyedén az időskála számát.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gantt-diagram testreszabása – Az MS Project időskála számlálásának elsajátítása
  az Aspose.Tasks-ben
url: /hu/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gantt-diagram testreszabása – Az MS Project időskála számlálásának elsajátítása az Aspose.Tasks-ben

## Bevezetés
Ha a Microsoft Projectben a **Gantt-diagram** megjelenését szeretné testreszabni, az időskála számlálásának vezérlése kulcsfontosságú technika. Az Aspose.Tasks for Java segítségével programozottan beállíthatja az alsó és középső időskála rétegeket, finomhangolhatja a jelölőpontok láthatóságát, majd **projekt mentése PDF‑ként** a résztvevőkkel való megosztáshoz. Ez az útmutató végigvezeti Önt a teljes folyamaton – a környezet beállításától a testreszabott Gantt-nézetet tükröző, kifinomult PDF generálásáig.

## Gyors válaszok
- **Mit jelent a “Gantt-diagram testreszabása”?** Az időskála rétegek, színek és elrendezés módosítása a jelentési igényeknek megfelelően.  
- **Melyik API metódus állítja be az alsó réteg számlálását?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Generálhatok PDF‑et közvetlenül a projektből?** Igen – használja a `project.save(..., SaveFileFormat.Pdf)` metódust.  
- **Szükség van licencre a termelési használathoz?** Kereskedelmi licenc szükséges; ingyenes próba verzió is elérhető.  
- **Melyik Java verzió támogatott?** A Java 8 vagy újabb verzió működik a legújabb Aspose.Tasks könyvtárral.

## Mi jelent a “Gantt-diagram testreszabása” az Aspose.Tasks-ben?
A Gantt-diagram testreszabása azt jelenti, hogy programozottan módosítja a diagram vizuális elemeit – például az időskála intervallumokat, a jelölőpontokat és a feladatsávokat – hogy a diagram megfeleljen annak a módnak, ahogyan **a projekt megjelenítését** kezelni szeretné. Az időskála számlálásának megváltoztatásával szabályozhatja, hogy egy szegmens hány napot, hetet vagy hónapot képvisel, ezáltal a diagram érthetőbbé válik különböző közönségek számára.

## Előfeltételek
1. **Java fejlesztői környezet** – telepített JDK 8 vagy újabb.  
2. **Aspose.Tasks for Java könyvtár** – letölthető innen: [here](https://releases.aspose.com/tasks/java/).  
3. **Alapvető Java ismeretek** – ismerje a Java szintaxist és az objektum‑orientált koncepciókat.

## Csomagok importálása
Importálja a szükséges osztályokat a Java projektjébe:

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
Határozza meg, hogy a projektfájlok honnan lesznek beolvasva és hová lesznek írva:

```java
String dataDir = "Your Data Directory";
```

Cserélje le a `"Your Data Directory"` értéket a gépén lévő abszolút útvonalra.

### 2. lépés: Új Project példány létrehozása
Hozzon létre egy új `Project` objektumot, amely tartalmazni fogja az összes feladatot és nézetbeállítást:

```java
Project project = new Project();
```

### 3. lépés: A Gantt-diagram nézet konfigurálása
Hozzon létre egy `GanttChartView` objektumot – itt fogja **generálni a Gantt nézet Java** kódot a diagram megjelenésének vezérléséhez:

```java
GanttChartView view = new GanttChartView();
```

### 4. lépés: Az alsó réteg időskála számlálásának beállítása
Állítsa be az alsó réteget úgy, hogy két intervallumot jelenítsen meg, és elrejtse a jelölőpontokat:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 5. lépés: A középső réteg időskála számlálásának beállítása
Alkalmazza ugyanazt a konfigurációt a középső rétegre:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 6. lépés: A testreszabott nézet hozzáadása a projekthez
Csatolja a most konfigurált nézetet a `Project` példányhoz:

```java
project.getViews().add(view);
```

### 7. lépés: Minta feladatok hozzáadása (teszt adatok)
Hozzon létre néhány feladatot meghatározott időtartamokkal a testreszabott Gantt-diagram bemutatásához:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 8. lépés: Projekt mentése PDF‑ként
Végül exportálja a projektet – beleértve a **testreszabott Gantt-diagramot** – PDF fájlba:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Az eredményül kapott PDF bemutatja, hogyan lettek **testreszabva** az alsó és középső időskála rétegek, így a résztvevők számára egyértelmű, nyomtatható ütemtervet biztosít.

## Gyakori problémák és hibaelhárítás
- **A PDF üres** – Győződjön meg arról, hogy a `dataDir` útvonal fájlelválasztóval (`/` vagy `\`) végződik, és hogy a könyvtár létezik.  
- **A jelölőpontok még mindig megjelennek** – Ellenőrizze, hogy a `setShowTicks(false)` mindkét rétegen meghívásra került.  
- **Az időtartam nem alkalmazódik** – Győződjön meg arról, hogy a `TimeUnitType.Hour` (vagy a megfelelő egység) használatával hozza létre az időtartamokat.

## Gyakran feltett kérdések

**K: Kezelni tudja az Aspose.Tasks for Java a nagyméretű projektfájlokat?**  
V: Igen, a könyvtár a nagy mennyiségű projektadat magas teljesítményű feldolgozására van optimalizálva.

**K: Kompatibilis-e az Aspose.Tasks for Java különböző Java IDE‑kkel?**  
V: Teljes mértékben – zökkenőmentesen működik az Eclipse, IntelliJ IDEA, NetBeans és más népszerű IDE‑kkel.

**K: Testreszabhatom a Gantt-diagramok megjelenését az időskála beállításain túl?**  
V: Igen, az Aspose.Tasks kiterjedt stílusbeállítási lehetőségeket kínál, például sávszínek, betűtípusok és rácsvonalak.

**K: Elérhető próba verzió az Aspose.Tasks for Java‑hoz?**  
V: Igen, ingyenes próba verziót szerezhet [innen](https://releases.aspose.com/).

**K: Hol kaphatok támogatást az Aspose.Tasks for Java‑hoz?**  
V: Támogatást és segítséget az Aspose.Tasks fórumon találhat [itt](https://forum.aspose.com/c/tasks/15).

**K: Hogyan változtathatom meg programozottan a Gantt-diagram háttérszínét?**  
V: Használja a `view.getGanttChartProperties().setBackgroundColor(Color)` metódust a `java.awt.Color` importálása után.

## Összegzés
A lépések követésével megtanulta, hogyan **testreszabja a Gantt-diagram** időskála rétegeit, javítsa a **projekt megjelenítését**, és **projektet mentse PDF‑ként** az Aspose.Tasks for Java segítségével. Ez a megközelítés teljes irányítást biztosít a vizuális kimenet felett, megkönnyítve a tiszta, professzionális ütemtervek megosztását a csapatával vagy ügyfeleivel.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-29
description: Ismerje meg, hogyan olvashatja be az alapvonal adatokat és ütemezheti
  a feladatokat az Aspose.Tasks for Java használatával, hogy hatékonyan összehasonlíthassa
  a tervezett és a tényleges előrehaladást.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Alapvonal feladat ütemezése az Aspose.Tasks-ben
og_description: Ismerje meg, hogyan olvashatja be az alapvonal adatokat és ütemezheti
  a feladatokat az Aspose.Tasks for Java használatával, lehetővé téve a tervezett
  és a tényleges előrehaladás pontos összehasonlítását.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Hogyan olvassuk be az alapvonalat és ütemezzük a feladatokat az Aspose.Tasks
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Hogyan olvassuk be az alapvonalat és ütemezzük a feladatokat az Aspose.Tasks
  segítségével
url: /hu/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan olvassuk el az alapvonalat és ütemezzük a feladatokat az Aspose.Tasks segítségével

Ebben az útmutatóban megtudja, **hogyan olvassa el az alapvonal** információkat, és hogyan ütemezze a feladatokat programozottan az Aspose.Tasks for Java segítségével. A tutorial végére képes lesz rögzíteni az eredeti projekttervet, összehasonlítani a tényleges előrehaladással, és varianciajelentéseket generálni – mindezt anélkül, hogy a Microsoft Project telepítve lenne.

## Bevezetés a projektmenedzsment alapvonalához
A **project management baseline** kezelése az eredményes projektmenedzsment egyik alappillére. Lehetővé teszi az eredeti terv rögzítését, majd a **tervezett és a tényleges előrehaladás** összehasonlítását, így időben észlelheti az eltéréseket. Ebben a tutorialban végigvezetjük, hogyan ütemezzük a feladatok alapvonalait az Aspose.Tasks for Java segítségével, és biztosítjuk a **projektalapvonalak** magabiztos kezeléséhez szükséges eszközöket, hogy projektjei a helyes úton maradjanak.

## Gyors válaszok
- **Mi képvisel egy projektmenedzsment alapvonal?**  
  Rögzíti a jóváhagyott ütemtervet, költséget és hatókört a projekt kezdetén, referencia pontot biztosítva a varianciaelemzéshez.  
- **Melyik könyvtár kezeli az alapvonal ütemezését Java-ban?**  
  Az Aspose.Tasks for Java egy tiszta Java API-t kínál, amely támogatja a 45+ bemeneti és kimeneti formátumot, és akár 100 000 feladatot is kezelő projekteket.  
- **Szükségem van licencre a kód futtatásához?**  
  Egy ingyenes próba a teszteléshez működik; a termeléshez kereskedelmi licenc szükséges.  
- **Mik a fő előfeltételek?**  
  Java Development Kit (JDK) 11+ és az Aspose.Tasks for Java könyvtár.  
- **Megtekinthetem az alapvonal dátumait a beállítás után?**  
  Igen – használja a `TaskBaseline` objektumot a kezdő, befejező és időtartam értékek olvasásához.

## Mi az a projektmenedzsment alapvonal?
A projektmenedzsment alapvonal rögzíti a jóváhagyott ütemtervet, költségvetést és hatókört a végrehajtás kezdetén. Referenciapontként szolgál a teljesítmény méréséhez és az eltérések azonosításához a projekt életciklusa során. Tartalmazza a tervezett kezdő- és befejezési dátumokat, a teljes költséget és a hatókör részleteit, átfogó pillanatképet nyújtva a későbbi összehasonlításhoz.

## Miért használja az Aspose.Tasks-et az alapvonal ütemezéséhez?
Az Aspose.Tasks egy tiszta Java API-t biztosít, amely a Microsoft Project telepítése nélkül működik. Támogatja a **45+ bemeneti és kimeneti formátumot**, képes **akár 100 000 feladat** kezelésére memóriahatékony módban, és beépített módszereket kínál az alapvonal adatok olvasásához és írásához – ezáltal egyszerűvé téve az automatizált jelentéskészítést és integrációt.

## Előfeltételek
- **Java Development Kit (JDK)** – telepítse a JDK 11 vagy újabb verziót. Letöltheti a [weboldalról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – töltse le a legújabb kiadást a [letöltési oldalról](https://releases.aspose.com/tasks/java/), és adja hozzá a JAR-t a projekt osztályútvonalához.

## Csomagok importálása
A `Project`, `Task` és `TaskBaseline` osztályok a `com.aspose.tasks` névtérben találhatók. Importálja őket a forrásfájl tetején:

A `Project` osztály az Aspose.Tasks felső szintű objektuma, amely egyetlen projektfájlt képvisel a memóriában. Hozzáférést biztosít a feladatokhoz, erőforrásokhoz és alapvonal gyűjteményekhez.

## Hogyan olvassuk el az alapvonalat?
Töltse be a projektet, majd kérdezze le a `TaskBaseline` gyűjteményt minden feladatra. A `TaskBaseline` objektum visszaadja az alapvonal kezdő, befejező és időtartam értékeit, amelyeket a `setBaseline` hívásakor rögzített. Ez a közvetlen megközelítés lehetővé teszi az alapvonal értékek olvasását XML vagy bináris fájlok elemzése nélkül.

## 1. lépés: új projektpéldány létrehozása
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## 2. lépés: feladat definiálása és alapvonal beállítása
```java
Project project = new Project();
```

## 3. lépés: alapvonal információk elérése
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 4. lépés: alapvonal időtartam megjelenítése
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## 5. lépés: alapvonal kezdő dátum megjelenítése
```java
System.out.println(baseline.getDuration().toString());
```

## 6. lépés: alapvonal befejező dátum megjelenítése
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Gyakori problémák és megoldások
- **Az alapvonal nincs beállítva:** Győződjön meg róla, hogy a feladatok hozzáadása **után** hívja a `project.setBaseline(BaselineType.Baseline)`-t; ellenkező esetben az alapvonal gyűjtemény üres lesz.  
- **Null értékek:** Ha a `task.getBaselines()` egy üres listát ad vissza, ellenőrizze, hogy a feladat a projekt hierarchiájához lett-e hozzáadva az alapvonal beállítása előtt.  
- **Dátumformátum:** A `getStart()` és `getFinish()` metódusok `java.util.Date` objektumokat adnak vissza. Használja a `SimpleDateFormat`-ot, ha egyedi megjelenítési formátumra van szüksége.

## Gyakran ismételt kérdések

**K: Hogyan hozhatok létre új projektpéldányt az Aspose.Tasks-ben?**  
A: Hozza létre a `Project` osztályt (`Project project = new Project();`). Ez egy új projektfájlt hoz létre, amely készen áll a feladatokra és alapvonalakra.

**K: Mi a különbség a `BaselineType.Baseline` és a többi alapvonal típus között?**  
A: A `BaselineType.Baseline` az elsődleges alapvonalra (Baseline 1) utal. Az Aspose.Tasks a Baseline 2‑10-et is támogatja további pillanatképekhez.

**K: Exportálhatom az alapvonal adatokat Excel vagy CSV formátumba?**  
A: Igen, iterálhat a `TaskBaseline` objektumokon, és a standard Java I/O segítségével CSV fájlba írhatja az értékeket.

**K: Befolyásolja az alapvonal beállítása a meglévő feladat dátumokat?**  
A: Az alapvonal beállítása rögzíti a jelenlegi dátumokat, de nem módosítja a feladat aktív ütemtervét. A beállítás után is módosíthatja a kezdő/befejező dátumokat.

**K: Lehetséges több alapvonalat programozottan összehasonlítani?**  
A: Teljesen lehetséges. Szerezze be az egyes alapvonalakat a `task.getBaselines().get(index)` segítségével, és hasonlítsa össze a `Start`, `Finish` és `Duration` tulajdonságaikat.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Kapcsolódó oktatóanyagok

- [Create Task List Java – MS Project Baseline using Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [How to Set Baseline Duration in Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Create MPP Project Java – Change Task Progress with Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
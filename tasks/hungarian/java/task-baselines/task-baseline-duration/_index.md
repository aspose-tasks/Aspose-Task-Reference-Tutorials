---
date: 2026-08-29
description: Tanulja meg, hogyan állíthatja be a baseline duration-t és követheti
  nyomon a projekt előrehaladását az Aspose.Tasks for Java használatával. Ez a lépésről‑lépésre
  útmutató segít hatékonyan kezelni a task baselines-t.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Hogyan állítsuk be a baseline duration-t az Aspose.Tasks for Java-ban
og_description: Tanulja meg, hogyan állíthatja be a baseline duration-t és követheti
  nyomon a projekt előrehaladását az Aspose.Tasks for Java használatával. Kövesse
  ezt a részletes útmutatót a task baselines hatékony kezeléséhez.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Hogyan állítsuk be a baseline duration-t a projekt előrehaladásának nyomon
  követéséhez
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Hogyan állítsuk be a baseline duration-t a projekt előrehaladásának nyomon
  követéséhez
url: /hu/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be az alapvonal időtartamát a projekt előrehaladásának nyomon követéséhez

## Bevezetés
A projekt előrehaladásának nyomon követése egy szilárd alapvonallal kezdődik. Ebben az útmutatóban megtudja, **hogyan állítsa be a feladatok alapvonal időtartamát** Microsoft Project fájlokban az Aspose.Tasks Java könyvtár segítségével, és megérti, miért segít a korai alapvonal létrehozása a menetrendelt eltérés, költségeltérés és erőforrás-túlterhelés nyomon követésében a projekt teljes életciklusa során.

## Gyors válaszok
- **Mi jelent a “set baseline”?** Rögzíti egy feladat eredeti kezdő, befejező és időtartamát, hogy a későbbi változásokat össze lehessen hasonlítani.  
- **Melyik Aspose.Tasks osztály hoz létre projektet?** A `Project` osztály – megtanulja, hogyan **hozzon létre projektpéldányt** helyesen.  
- **Szükségem van licencre a kód futtatásához?** Egy ingyenes értékelési licenc teszteléshez működik; a termeléshez kereskedelmi licenc szükséges.  
- **Lekérhetek köztes alapvonalakat?** Igen, az Aspose.Tasks lehetővé teszi a köztes alapvonalak és azok fix költségeinek lekérdezését.  
- **Milyen Java verzió szükséges?** Java 8 vagy újabb ajánlott.  
- **Hogyan segít ez a projekt előrehaladásának nyomon követésében?** Miután az alapvonal be van állítva, azonnal összehasonlíthatja a tényleges dátumokat az eredeti tervvel a beépített jelentési funkciók segítségével.

## Mi az a feladat alapvonal, és miért állítsuk be?
A feladat alapvonal rögzíti a tervezett ütemtervet (kezdő dátum, befejező dátum és időtartam) egy adott időpontban. Az alapvonal beállításával egy referencia pontot hoz létre, amely megkönnyíti a menetrendi eltérés, költségtúllépés és erőforrás-túlterhelés észlelését a projekt fejlődése során.

## Miért használja az Aspose.Tasks‑t az alapvonal kezeléséhez?
Az Aspose.Tasks **teljes .mpp kompatibilitást** biztosít – natív Microsoft Project fájlokat olvashat és írhat anélkül, hogy a Microsoft Office telepítve lenne. Az API programozott hozzáférést biztosít **50+ bemeneti és kimeneti formátumhoz**, támogatja a **1‑10 köztes alapvonalakat**, és képes **több száz oldalas projekteket** kezelni anélkül, hogy a teljes fájlt a memóriába töltené, ami elengedhetetlen a nagy teljesítményű kötegelt feldolgozáshoz.

## Előfeltételek
1. **Java fejlesztői környezet** – JDK 8+ telepítve és konfigurálva.  
2. **Aspose.Tasks for Java** – töltse le a könyvtárat a [Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **IDE vagy build eszköz** – Maven, Gradle vagy bármely kedvelt IDE.

## Csomagok importálása
A következő importok hozzák be az Aspose.Tasks alapvető osztályait, amelyek a projektek, feladatok, alapvonalak és időszakos adatok kezeléséhez szükségesek.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## 1. lépés: projektpéldány létrehozása
A `Project` osztály egy Microsoft Project fájlt reprezentál a memóriában, és minden művelet belépési pontja.

```java
Project project = new Project();
```

## 2. lépés: feladat alapvonal létrehozása
A `TaskBaseline` tárolja egy adott feladat tervezett kezdő, befejező és időtartamát.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 3. lépés: feladat alapvonal információk megjelenítése
A `getBaselines()` metódus visszaadja a feladathoz kapcsolódó alapvonalak gyűjteményét.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 4. lépés: köztes alapvonal és fix költség ellenőrzése
`BaselineType` felsorolja az elsődleges és köztes alapvonalakat (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## 5. lépés: időszakos adatok kiírása
`TimephasedData` egy adott időintervallumra vonatkozó ütemtervi információt képvisel.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Ezeknek a lépéseknek a követésével **beállíthatja a feladat alapvonal időtartamát** bármely feladatra, és részletes alapvonal információkat kérhet le az Aspose.Tasks for Java segítségével, ami megbízható módot biztosít a **projekt előrehaladásának nyomon követésére** a projekt életciklusa során.

## Gyakori problémák és megoldások
- **Az alapvonal nem jelenik meg az MS Projectben:** Győződjön meg róla, hogy a `project.setBaseline(BaselineType.Baseline)` **a** feladat hozzáadása **után** lett meghívva.  
- **NullPointerException a `getBaselines()`-nél:** Ellenőrizze, hogy a feladat a alapvonal beállítása előtt hozzá lett-e adva a projekthez.  
- **Időegység eltérés:** Használja a `TimeUnitType`-ot az időtartam helyes formázásához, különösen egyedi naptárak esetén.

## Gyakran Ismételt Kérdések
### Mi az a feladat alapvonal az MS Projectben?
A feladat alapvonal az MS Projectben egy pillanatkép a feladat kezdeti tervezett ütemtervéről, beleértve a kezdő dátumot, befejező dátumot és időtartamot.

### Miért fontos a feladat alapvonalak kezelése?
A feladat alapvonalak kezelése segít a tervezett ütemterv összehasonlításában a projekt tényleges előrehaladásával, elősegítve a jobb nyomon követést és döntéshozatalt.

### Módosíthatom a feladat alapvonalat, miután be lett állítva?
Igen, módosíthatja a feladat alapvonalakat az MS Projectben a projekt terv változásainak tükrözésére. Azonban fontos dokumentálni minden eltérést az eredeti alapvonaltól.

### Támogatja az Aspose.Tasks más projektmenedzsment funkciókat is?
Igen, az Aspose.Tasks számos projektmenedzsment funkciót kínál, beleértve a feladat ütemezést, erőforrás-elosztást és Gantt-diagram generálást.

### Hol találok támogatást az Aspose.Tasks-hez?
Támogatást az Aspose.Tasks-hez a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) talál, ahol kérdéseket tehet fel és más felhasználókkal léphet kapcsolatba.

## További gyakran ismételt kérdések
**Q: Kell meghívni a `setBaseline`-t minden feladatra külön-külön?**  
A: Nem. A `project.setBaseline(BaselineType.Baseline)` meghívása egyszerre rögzíti az alapvonalat a projekt összes feladata számára.

**Q: Hogyan állíthatok be köztes alapvonalat egy adott feladatra?**  
A: Használja a `project.setBaseline(BaselineType.Baseline1)`-et (vagy Baseline2‑Baseline10) a feladat ütemezésének frissítése után.

**Q: Lehetséges a alapvonal adatokat CSV‑be exportálni?**  
A: Igen. Iteráljon a `task.getBaselines()`-en, és írja a kívánt mezőket egy CSV fájlba a szabványos Java I/O használatával.

**Q: Olvashatok egy meglévő .mpp fájlt, amely már tartalmaz alapvonalakat?**  
A: Természetesen. Töltse be a fájlt a `new Project("myproject.mpp")` segítségével, majd a fenti módon férjen hozzá minden feladat alapvonalához.

**Q: Kezeli az Aspose.Tasks a több projektből álló fájlokat?**  
A: Az Aspose.Tasks egy‑projekt .mpp fájlokkal dolgozik. Több projekt esetén programozottan kombinálja a projekteket.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Kapcsolódó útmutatók

- [Feladatlista létrehozása Java – MS Project alapvonal Aspose.Tasks használatával](/tasks/java/task-baselines/create-task-baseline/)
- [MPP projekt létrehozása Java – Feladat előrehaladás módosítása Aspose.Tasks segítségével](/tasks/java/task-properties/change-progress/)
- [Projektmenedzsment alapvonal – Feladat ütemezés Aspose.Tasks segítségével](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
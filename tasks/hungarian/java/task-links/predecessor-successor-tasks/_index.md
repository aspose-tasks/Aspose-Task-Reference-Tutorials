---
date: 2026-09-20
description: Ismerje meg, hogyan kezelheti a projektfeladat-függőségeket az Aspose.Tasks
  for Java használatával. Ez az útmutató megmutatja, hogyan adhat hozzá predecessor
  links, hogyan nyomtathatja ki a task names, és hogyan állíthatja be a task dependencies
  hatékonyan.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Projektfeladat-függőségek kezelése az Aspose.Tasks for Java segítségével
og_description: Ismerje meg, hogyan kezelheti a projektfeladat-függőségeket az Aspose.Tasks
  for Java használatával. Ez az útmutató megmutatja, hogyan adhat hozzá predecessor
  links, hogyan nyomtathatja ki a task names, és hogyan állíthatja be a task dependencies
  hatékonyan.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Projektfeladat-függőségek kezelése az Aspose.Tasks for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Projektfeladat-függőségek kezelése az Aspose.Tasks for Java segítségével
url: /hu/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt feladatfüggőségek kezelése az Aspose.Tasks for Java segítségével

## Bevezetés
A projekt feladatfüggőségek bármely reális ütemterv gerince, lehetővé téve, hogy modellezze, mely munka befejeződik, mielőtt egy másik elkezdődhet. Ebben az oktatóanyagról megtanulja, hogyan kezelje a **project task dependencies**‑t az Aspose.Tasks for Java‑val, beleértve az előd hivatkozások hozzáadását, a feladatnevek kiírását és a feladatfüggőségek programozott beállítását.

## Gyors válaszok
- **Mi az első lépés?** Töltse be az MPP fájlt egy `Project` objektumba.  
- **Hogyan adhat hozzá egy elődöt?** Hozzon létre egy `TaskLink`‑et, és állítsa be a `PredecessorTaskUid`‑t és a `SuccessorTaskUid`‑t.  
- **Felsorolhatja az összes hivatkozást?** Használja a `project.getTaskLinks()`‑t, és iteráljon a gyűjteményen.  
- **Szükségem van licencre?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc szükséges a termeléshez.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.

## Mi a projekt feladatfüggőségek?
A projekt feladatfüggőségek meghatározzák két feladat közötti logikai kapcsolatot, például Finish‑to‑Start vagy Start‑to‑Start, és meghatározzák a munkavégzés sorrendjét. Ezeknek a hivatkozásoknak a létrehozásával az ütemterv automatikusan figyelembe veszi a valós világ korlátozásait, megakadályozza az átfedő tevékenységeket, és biztosítja, hogy az alárendelt feladatok csak akkor induljanak, amikor előfeltételeik teljesülnek.

## Miért használja az Aspose.Tasks for Java‑t?
Az Aspose.Tasks for Java több mint harminc projektfájl-formátumot támogat, beleértve a legújabb Microsoft Project verziókat, és képes akár két gigabájt méretű fájlok feldolgozására anélkül, hogy a teljes dokumentumot a memóriába töltené. Ez a nagy teljesítményű képesség lehetővé teszi, hogy hatalmas ütemterveket manipuláljon, jelentéseket generáljon, és hatékonyan végezzen tömeges frissítéseket, így ideális vállalati szintű projektmenedzsment megoldásokhoz.

## Előkövetelmények
- Java fejlesztői környezet: Java 8 vagy újabb telepítve a gépén.  
- Aspose.Tasks for Java könyvtár: Töltse le és telepítse az Aspose.Tasks könyvtárat a [Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/).  
- Integrált fejlesztői környezet (IDE): Eclipse, IntelliJ IDEA vagy bármely Java‑kompatibilis IDE, amelyet preferál.

## Csomagok importálása
Importálnia kell a projektmanipulációt lehetővé tevő alap osztályokat.

A `Project` osztály a belépési pont a Microsoft Project fájlok betöltéséhez és mentéséhez.  
A `TaskLink` osztály két feladat közötti függőséget képviseli.

## Hogyan adjon hozzá egy előd hivatkozást két feladat között?
Hozzon létre egy `TaskLink` példányt, rendelje hozzá az előd feladat UID‑jét és a utód feladat UID‑jét, válassza ki a megfelelő `TaskLinkType`‑ot, például Finish‑to‑Start, majd adja hozzá a hivatkozást a projekt feladatlink gyűjteményéhez. A hozzáadás után az ütemterv azonnal tükrözi az új függőségi kapcsolatot.

### 1. lépés: a projekt objektum inicializálása
Hozzon létre egy új példányt a `Project` osztályból, és adja meg a projektfájl elérési útját (például `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### 2. lépés: feladatlinkek elérése
Szerezze be az összes feladatlinket a projektből a `getTaskLinks()` metódus használatával.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### 3. lépés: feladatlinkek bejárása
Használjon egy ciklust, hogy bejárja a gyűjteményben lévő minden feladatlinket, és kiírja az előd és utód feladatok információit.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### 4. lépés: új előd hivatkozás hozzáadása (opcionális)
Ha új függőséget kell létrehoznia, példányosítson egy `TaskLink`‑et, állítsa be a `PredecessorTaskUid`, `SuccessorTaskUid` és `LinkType` értékeket, majd adja hozzá a projekt linkgyűjteményéhez.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

Ismételje meg ezeket a lépéseket a konkrét projektkövetelményeknek megfelelően.

## Gyakori problémák és megoldások
- **Hiányzó előd a hivatkozás hozzáadása után** – Győződjön meg róla, hogy meghívja a `project.updateTaskLinks()`‑t (vagy ment és újratölt), hogy a belső gráf frissüljön.  
- **Teljesítménycsökkenés nagy fájlok esetén** – Használja a `project.setReadOnly(true)`‑t a tömeges műveletek előtt a memóriaigény csökkentése érdekében.  
- **Helytelen hivatkozástípus** – Ellenőrizze, hogy a megfelelő `TaskLinkType` enum értéket (pl. `FinishToStart`) használja-e az ütemterv logikájának megfelelően.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Tasks for Java‑t a meglévő Java projektemben?**  
A: Igen, egyszerűen adja hozzá az Aspose.Tasks JAR‑t a classpath‑hoz vagy a Maven/Gradle függőségekhez.

**Q: Az Aspose.Tasks kompatibilis különböző projektfájl-formátumokkal?**  
A: Igen, támogatja az MPP, XML, CSV és több mint 30 további formátumot.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks‑hez?**  
A: Szerezzen ideiglenes licencet a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalról.

**Q: Hol találok további támogatást az Aspose.Tasks‑hez?**  
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi támogatás és megbeszélésekért.

**Q: Letölthetek ingyenes próbaverziót az Aspose.Tasks for Java‑ból?**  
A: Igen, töltsön le egy ingyenes próbaverziót a [Aspose free trial page](https://releases.aspose.com/) oldalról.

---

**Utolsó frissítés:** 2026-09-20  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Projektmenedzsment feladatfüggőségek létrehozása az Aspose.Tasks-ben](/tasks/java/task-links/create-task-link/)
- [Projekt kezdődátum beállítása és szülő-gyermek feladatok kezelése az Aspose.Tasks-ben](/tasks/java/task-properties/parent-child-tasks/)
- [Feladatprioritások olvasása és beállítása az Aspose.Tasks for Java segítségével](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
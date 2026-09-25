---
date: 2026-09-25
description: Ismerje meg, hogyan hozhat létre projektmenetrendet Java-ban az Aspose.Tasks
  használatával. Ez az útmutató megmutatja, hogyan adjon hozzá összegző feladatokat,
  kezelje a projekt hierarchiáját, és állítsa be hatékonyan a dokumentumkönyvtárat.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Feladatok létrehozása az Aspose.Tasks-ben
og_description: Ismerje meg, hogyan hozhat létre projektmenetrendet Java-ban az Aspose.Tasks
  használatával. Kövesse a lépésről‑lépésre útmutatót az összegző feladatok hozzáadásához,
  a hierarchia kezeléséhez és a dokumentumkönyvtár beállításához.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Hogyan készítsünk projektmenetrendet az Aspose.Tasks for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Hogyan készítsünk projektmenetrendet az Aspose.Tasks for Java segítségével
url: /hu/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre projekt ütemtervet az Aspose.Tasks for Java segítségével

## Bevezetés
Ezen az útmutatón megtanulja, hogyan **hozzon létre projekt ütemtervet** egy Java alkalmazásban az Aspose.Tasks használatával. Akár egy egyszerű teendőlistát, akár egy összetett vállalati szintű tervezőt épít, az alábbi lépések végigvezetik a felhasználót összegző feladatok hozzáadásában, a projekt hierarchia kezelésében és a dokumentum könyvtár beállításában – mindezt világos, futtatható kódrészletekkel. A végére egy teljesen felépített ütemtervet kap, amely később további módosításra vagy exportálásra kész.

## Gyors válaszok
- **Az Aspose.Tasks mit kezel?** Kezeli a feladat hierarchiákat, erőforrásokat, naptárakat és a projektfájl formátumokat (MS‑Project, Primavera stb.).
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes ideiglenes licenc elegendő értékeléshez; a teljes licenc a termeléshez szükséges.
- **Mely Java verzió támogatott?** A Java 8 és újabb verziók teljes mértékben támogatottak.
- **Hozzáadhatok egyéni mezőket a feladatokhoz?** Igen, a feladatokat felhasználó által definiált mezőkkel bővítheti az API-n keresztül.
- **Van beépített támogatás a Gantt-diagramokhoz?** Az Aspose.Tasks képes PDF/HTML formátumba exportálni, amely tartalmaz Gantt megjelenítéseket.

## Mi az a projekt ütemterv az Aspose.Tasks-ben?
A projekt ütemterv a feladatok, függőségek és idővonalak teljes halmaza, amely meghatározza, hogyan lesz a munka elvégezve. Az Aspose.Tasks ezt az információt egy `Project` objektumban tárolja, amelyet olvashat, módosíthat és különböző formátumokban menthet. Tartalmazza a kezdő és befejező dátumokat, korlátozásokat és erőforrás hozzárendeléseket, lehetővé téve a átfogó tervezést és jelentést.

## Miért használjuk az Aspose.Tasks-et Java projektmenedzsmenthez?
Az Aspose.Tasks **30+ bemeneti és kimeneti formátumot** támogat, és képes **akár 10 000 feladatot** tartalmazó projekteket feldolgozni anélkül, hogy a teljes fájlt a memóriába töltené, így magas teljesítményt nyújt nagy léptékű Java projektmenedzsment helyzetekben.

## Előkövetelmények
Mielőtt belemerülne az útmutatóba, győződjön meg róla, hogy a következő előkövetelmények rendelkezésre állnak:
- **Java Development Kit (JDK)** – JDK 8 vagy újabb telepítve a gépén.  
- **Aspose.Tasks for Java library** – Töltse le és telepítse a könyvtárat a [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/) oldalról.  
- **Integrated Development Environment (IDE)** – Használja az Eclipse, IntelliJ IDEA vagy bármely kedvelt Java‑barát IDE-t.

## Csomagok importálása
`Project`, `Task`, és a kapcsolódó osztályok a `com.aspose.tasks` névtérben találhatók. Importálja őket a Java fájl tetején:
A `Project` osztály egy teljes projekt ütemtervet képvisel, és módszereket biztosít a feladatok és erőforrások manipulálásához.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

A `Project` osztály a belépési pont minden projektfájl művelethez.

## Hogyan hozzunk létre projekt ütemtervet az Aspose.Tasks segítségével?

Betölt egy új `Project` példányt, beállítja a dokumentum könyvtárát, és elkezdi a feladatok hozzáadását. Ez a közvetlen válasz bekezdés leírja a fő folyamatot: létrehoz egy `Project`-et, konfigurálja a `RootFolder`-t (a dokumentum könyvtárát), majd hozzáad egy összegző feladatot, amelyet alfeladatok követnek. Minden változtatás a memóriában marad, amíg a `save` hívásával nem menti az ütemtervet egy fájlba.

### 1. lépés: a dokumentum könyvtár beállítása
Határozza meg, hová kerül a létrehozott projektfájl. A könyvtár korai beállítása biztosítja, hogy az összes későbbi mentési művelet egységes útvonalat használjon.

A `RootFolder` tulajdonság meghatározza az alapmappát, ahonnan a projektfájlok olvasásra vagy írásra kerülnek.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### 2. lépés: új projekt létrehozása
Hozzon létre egy új `Project` objektumot, amely a saját ütemtervét tárolja. Opcionálisan megadhat egy már létező fájl útvonalát, hogy betöltsön egy meglévő ütemtervet módosítás céljából.

A `Project` konstruktor egy üres ütemtervet hoz létre, amely készen áll a feladatok hozzáadására.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 3. lépés: összegző feladat hozzáadása
Az összegző feladat csoportosítja a kapcsolódó alfeladatokat, és Gantt-diagramokban összecsukható csomóként jelenik meg. Használja a `Task` osztályt, és állítsa az `IsSummary` értékét `true`-ra.

Az `addTask` metódus egy új feladatot hoz létre a megadott szülő alatt, és visszaadja annak azonosítóját.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### 4. lépés: alfeladat hozzáadása
Az alfeladatok öröklik a kezdő/befejező dátumokat a szülő összegző feladattól, hacsak nem írja felül őket. Alfeladat hozzáadása olyan egyszerű, mint az `addTask` újbóli meghívása és a szülő azonosítójának megadása.

`addTask` hívása szülő azonosítóval alfeladatot ad hozzá az adott összegző feladathoz.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Folytassa a feladatok és alfeladatok hozzáadását a projekt igényei szerint. Minden lépés hozzájárul egy strukturált projekt hierarchia felépítéséhez, amely exportálható MS‑Project, PDF vagy más támogatott formátumba.

## Gyakori problémák és megoldások
- **Probléma:** “Document directory not found.”  
  **Megoldás:** Ellenőrizze, hogy a `RootFolder`-nek megadott útvonal létezik-e a fájlrendszeren, és hogy a Java folyamatnak írási jogosultsága van-e.
- **Probléma:** Alfeladatok nem jelennek meg az összegző feladat alatt.  
  **Megoldás:** Győződjön meg róla, hogy a `addTask` hívásakor a helyes szülő feladat azonosítót adja meg. Az API a szülő azonosítót második argumentumként várja.
- **Probléma:** Nagy projektek OutOfMemoryError-t okoznak.  
  **Megoldás:** Az Aspose.Tasks feladatokat streaming módban dolgozza fel; növelje a JVM heap méretét (`-Xmx2g`), vagy ossza fel az ütemtervet több fájlra.

## Gyakran ismételt kérdések
**Q: Az Aspose.Tasks alkalmas kis‑méretű projektekhez?**  
A: Teljes mértékben. A könyvtár egyetlen feladatlistától a vállalati szintű ütemtervekig skálázható, több ezer feladattal.

**Q: Hol találhatók részletes dokumentációk az Aspose.Tasks for Java-hoz?**  
A: Tekintse meg a dokumentációt a [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/) oldalon.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks-hez?**  
A: Látogassa meg a [temporary license request page](https://purchase.aspose.com/temporary-license/) oldalt egy időkorlátos licencért, amely fejlesztéshez és teszteléshez használható.

**Q: Testreszabhatom a feladat attribútumait az Aspose.Tasks segítségével?**  
A: Igen, a feladatokat egyéni mezőkkel bővítheti, erőforrásokat rendelhet, és programozottan módosíthatja a naptárakat.

**Q: Van támogatói közösség az Aspose.Tasks felhasználók számára?**  
A: Természetesen! Csatlakozzon az Aspose.Tasks közösséghez a [the support forum](https://forum.aspose.com/c/tasks/15) oldalon.

---

**Legutóbb frissítve:** 2026-09-25  
**Tesztelve ezzel:** Aspose.Tasks 24.12 for Java  
**Szerző:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Kapcsolódó oktatóanyagok

- [Projekt kezdő dátum beállítása MS Projectben az Aspose.Tasks for Java használatával](/tasks/java/project-properties/write-project-info/)
- [Projektmenedzsment feladatfüggőségek létrehozása az Aspose.Tasks-ben](/tasks/java/task-links/create-task-link/)
- [Hogyan adjon hozzá erőforrást a projekthez és hozzon létre erőforrás hozzárendeléseket az Aspose.Tasks-ben](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
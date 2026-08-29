---
date: 2026-08-29
description: Tanulja meg, hogyan állíthatja be a link types-t és kezelheti a task
  dependencies-t az Aspose.Tasks for Java segítségével egy lépésről‑lépésre útmutatóban.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Hogyan állítsuk be a link types-t az Aspose.Tasks for Java-ban
og_description: Tanulja meg, hogyan állíthatja be a link types-t és kezelheti a task
  dependencies-t az Aspose.Tasks for Java segítségével. Lépésről‑lépésre útmutató
  fejlesztőknek.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Hogyan állítsuk be a link types-t az Aspose.Tasks for Java-ban
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Hogyan állítsuk be a link types-t az Aspose.Tasks for Java-ban
url: /hu/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a hivatkozástípusokat az Aspose.Tasks for Java-ban

## Bevezetés
Ha kíváncsi vagy **how to set link**-re a feladatok között, miközben *manage task dependencies*-t végzel egy projektben, jó helyen jársz. Ebben az útmutatóban végigvezetünk egy új projekt létrehozásán, feladatok hozzáadásán, és a hivatkozástípus (Start‑to‑Start, Finish‑to‑Start stb.) meghatározásán az Aspose.Tasks for Java használatával. A végére magabiztosan tudod majd testreszabni a feladatkapcsolatokat, hogy megfeleljenek a valós ütemezési igényeknek, és láthatod, hogyan kezeli az API a akár 10 000 feladatot tartalmazó nagyméretű terveket.

## Gyors válaszok
- **Melyik osztály képviseli a függőséget?** `TaskLink` a fő objektum, amely egy hivatkozást modellez két feladat között.  
- **Melyik enum határozza meg a kapcsolat típusát?** `TaskLinkType` (pl. `StartToStart`, `FinishToStart`).  
- **Olvashatok meglévő hivatkozástípusokat?** Igen – iterálja a `Project.getTaskLinks()`-t és hívja meg a `getLinkType()`-t.  
- **Szükségem van licencre ehhez a kódhoz?** Ideiglenes licenc teszteléshez működik; a teljes licenc szükséges a termeléshez.  
- **Kompatibilis-e a Java 8+ verzióval?** Teljesen – az Aspose.Tasks támogatja a Java 8-tól a Java 21-ig terjedő verziókat, összesen 13 fő kiadást.  

## Mi a feladatkapcsolat?
A **task link** egy függőséget modellez két feladat között a projekt ütemezésben.  
Létrehozhat, módosíthat vagy törölhet egy `TaskLink`-et, hogy tükrözze az előző‑követő kapcsolatokat, lehetővé téve a tervezőnek, hogy automatikusan kiszámítsa a kezdési és befejezési dátumokat.

## Miért használjuk az Aspose.Tasks hivatkozástípusokat?
Az Aspose.Tasks **30+ bemeneti és kimeneti formátumot** támogat, és képes olyan projekteket feldolgozni, amelyek **akár 10 000 feladatot** tartalmaznak, anélkül, hogy a teljes fájlt a memóriába töltené. Ez a számszerű képesség gyors teljesítményt biztosít még vállalati méretű tervek esetén is, és a könyvtár megőrzi a Microsoft Project összes funkcióját, például az egyéni mezőket és erőforrás‑hozzárendeléseket.

## Előfeltételek
- **Java fejlesztői környezet** – JDK 8 vagy újabb telepítve és konfigurálva.  
- **Aspose.Tasks könyvtár** – Töltse le a legújabb JAR-t a [download link](https://releases.aspose.com/tasks/java/) címről.  
- **Dokumentum könyvtár** – Hozzon létre egy mappát a gépén, ahol a mintaprojekt fájlokat tárolja.  

## Csomagok importálása
Először importáljuk a szükséges Aspose.Tasks osztályokat. Ez felkészíti az IDE-t, hogy felismerje a később használandó API hívásokat.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Hogyan állítsuk be a hivatkozástípusokat az Aspose.Tasks for Java-ban?
Töltsön be egy új `Project` példányt, adjon hozzá két feladatot, majd hozza létre a `TaskLink`-et a kívánt `TaskLinkType`-tal. Ez a kétlépéses minta lehetővé teszi, hogy egyetlen hívással meghatározzon bármelyik a négy szabványos függőségi típus közül. A `Project` a teljes projektfájlt és ütemezését képviseli. A `Task` egy egyedi munkatétel a projektben. A `TaskLink` összeköti az előző feladatot a következő feladattal. A `TaskLinkType` egy felsorolás, amely meghatározza a kapcsolatot (Start‑to‑Start, Finish‑to‑Start, stb.).

### 1. lépés: hivatkozástípus beállítása
`TaskLink` egy függőséget jelent két feladat között, míg a `TaskLinkType` felsorolja a lehetséges kapcsolat típusokat, például a `StartToStart`-ot. Ebben a lépésben létrehozunk egy új projektet, hozzáadunk két feladatot, és összekapcsoljuk őket a **Start‑to‑Start** kapcsolattal.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** A `StartToStart` helyett cserélheti a `FinishToStart`, `StartToFinish` vagy `FinishToFinish` értékekre, attól függően, hogy milyen függőséget kell **manage task dependencies**.

### 2. lépés: hivatkozástípus lekérése
`Project.getTaskLinks()` egy gyűjteményt ad vissza az összes `TaskLink` objektumról az ütemezésben. Ennek a gyűjteménynek az iterálásával kiolvashatja minden hivatkozás `TaskLinkType` értékét, és ellenőrizheti, hogy a helyes kapcsolat lett-e mentve.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

A konzol olyan értékeket fog kiírni, mint `StartToStart`, `FinishToStart` stb., megerősítve a korábban beállított hivatkozástípust.

## Gyakori problémák és megoldások
- **NullPointerException hivatkozások hozzáadása közben** – Győződjön meg róla, hogy mind az előző, mind a következő feladat hozzá van adva a projekthez a `TaskLink` létrehozása előtt.  
- **Helytelen hivatkozástípus mentés után** – Mindig hívja meg a `project.save("output.mpp")`-t (vagy egy másik támogatott formátumot) a hivatkozástípus beállítása után a változások mentéséhez.  
- **Licenc nem található** – Helyezze az Aspose.Tasks licencfájlt a projekt classpath-jába, és töltse be a `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kóddal.  

## Gyakran ismételt kérdések

**Q: Az Aspose.Tasks kompatibilis különböző Java környezetekkel?**  
A: Igen, az Aspose.Tasks integrálódik a standard Java SE, Java EE és Android fejlesztői készletekkel további függőségek nélkül.

**Q: Testreszabhatom a hivatkozástípusokat a projekt követelményei alapján?**  
A: Teljesen. A `TaskLinkType` enum négy szabványos típust biztosít, és kombinálhatja őket késleltetési értékekkel a komplex ütemezések modellezéséhez.

**Q: Hol találok részletes dokumentációt az Aspose.Tasks for Java-hoz?**  
A: Tekintse meg a [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) oldalt a mélyreható útmutatóért, API-referenciaért és kódmintákért.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks-hez?**  
A: Látogassa meg a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalt, hogy ideiglenes licencet szerezzen tesztelési célokra.

**Q: Hol kaphatok támogatást az Aspose.Tasks‑hez kapcsolódó kérdésekhez?**  
A: Csatlakozzon az Aspose.Tasks közösséghez a [support forum](https://forum.aspose.com/c/tasks/15) oldalon segítségért és megbeszélésekért.

**Q: Megváltoztathatom a hivatkozástípust a projekt mentése után?**  
A: Igen. Töltse be a projektet, szerezze meg a `TaskLink`-et, hívja meg a `setLinkType()`-t az új enum értékkel, majd mentse újra a projektet.

**Q: Támogatja az Aspose.Tasks a Microsoft Project (MPP) fájlok olvasását?**  
A: Igen. Használja a `new Project("file.mpp")` kódot MPP fájlok betöltéséhez, és dolgozzon a feladatkapcsolatokkal úgy, mint a fenti XML példában.

---

**Legutóbb frissítve:** 2026-08-29  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Keresztprojekt feladatkapcsolat létrehozása az Aspose.Tasks-ben](/tasks/java/task-links/create-cross-project-task-link/)
- [Projekt kezdő dátum beállítása és szülő-gyermek feladatok kezelése az Aspose.Tasks-ben](/tasks/java/task-properties/parent-child-tasks/)
- [MPP fájl betöltése Java-ban – Projekt tulajdonságok kezelése az Aspose.Tasks segítségével](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
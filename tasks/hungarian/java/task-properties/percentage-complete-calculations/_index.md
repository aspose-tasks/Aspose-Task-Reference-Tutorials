---
date: 2026-02-23
description: Fedezze fel az Aspose.Tasks for Java-t a projektmenedzsment egyszerűsítéséhez,
  és tanulja meg, hogyan számítsa ki a feladat százalékos arányát, valamint hogyan
  kövesse nyomon a haladást hatékonyan.
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Projektmenedzsment Java: Feladat % kész az Aspose.Tasks használatával'
url: /hu/java/task-properties/percentage-complete-calculations/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektmenedzsment Java: Feladat százalékos befejezésének kiszámítása az Aspose.Tasks segítségével

## Introduction
Üdvözöljük átfogó útmutatónkban a **project management java** használatáról az Aspose.Tasks for Java segítségével. Ebben az oktatóanyagban megtanulja, hogyan olvassa be a Microsoft Project fájlt, számolja ki a befejezett munkát, és szerezzen pontos előrehaladási százalékokat minden feladatra. Ezen számítások elsajátítása segít tájékoztatni az érintetteket és biztosítja, hogy a projekt a tervek szerint haladjon.

## Quick Answers
- **Melyik könyvtár kezeli a Microsoft Project fájlokat Java-ban?** Aspose.Tasks for Java.  
- **Melyik tulajdonság mutatja az általános előrehaladást?** `Tsk.PERCENT_COMPLETE`.  
- **Hogyan olvashatok be egy .mpp fájlt?** Load it with `new Project(filePath)`.  
- **Kiszámíthatom a befejezett munkát?** Yes, use `Tsk.PERCENT_WORK_COMPLETE`.  
- **Szükség van licencre a termeléshez?** A valid Aspose.Tasks license is required.

## What is Project Management Java?
A project management java a Java‑alapú eszközök és könyvtárak—például az Aspose.Tasks—használatát jelenti a projektmenetrendek programozott létrehozására, olvasására és manipulálására. Ez a megközelítés lehetővé teszi az automatizált jelentéstételt, egyedi műszerfalak készítését és a meglévő Java alkalmazásokkal való zökkenőmentes integrációt.

## Why Use Aspose.Tasks for Calculating Task Percentage?
- **Pontos előrehaladás nyomon követése** – natív Project mezők lekérése manuális elemzés nélkül.  
- **Teljes .mpp támogatás** – a Microsoft Project fájlok közvetlen olvasása, szerkesztése és mentése.  
- **Skálázható automatizálás** – ezrek feladat feldolgozása másodpercek alatt, ideális nagy portfóliókhoz.  
- **Keresztplatformos** – bármely Java futtatókörnyezetben működik, asztali géptől a felhőszolgáltatásokig.

## Prerequisites
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

- **Java Development Kit (JDK)** telepítve (Java 8 vagy újabb).  
- **Aspose.Tasks for Java** könyvtárral – töltse le a [itt](https://releases.aspose.com/tasks/java/) címről.  
- Egy minta Microsoft Project fájllal (pl. *Software Development.mpp*), amely egy ismert könyvtárban van elhelyezve.

## Import Packages
Először importálja a szükséges osztályokat. Ezt a kódrészletet bármely, az Aspose.Tasks‑kel dolgozó Java osztályba be kell illeszteni.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```

### Step 1: Set the Document Directory
1. lépés: A dokumentum könyvtár beállítása

Adja meg azt a mappát, amelyik a *.mpp* fájlt tartalmazza. Cserélje le a helyőrzőt a gépén lévő tényleges útvonalra.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Load the Project File
2. lépés: A projektfájl betöltése

Hozzon létre egy `Project` példányt, és töltse be a Microsoft Project fájlt. Ez a lépés **beolvassa a Microsoft Project fájlt**, így hozzáférhet a feladataihoz.

```java
Project project = new Project(dataDir + "Software Development.mpp");
```

### Step 3: Retrieve the Task Collection
3. lépés: A feladatelőállítás lekérése

Szerezze meg a gyökérfeladatot, majd annak alfeladatait. Ez a gyűjtemény a projekt összes felső szintű feladatát képviseli.

```java
TaskCollection alTasks = project.getRootTask().getChildren();
```

### Step 4: Print Percentage Complete Values
4. lépés: A százalékos befejezés értékek kiírása

Iteráljon minden feladaton, és jelenítse meg a három kulcsfontosságú előrehaladási mérőszámot:

- **Percentage Complete** – a feladat általános előrehaladása.  
- **Percentage Work Complete** – a munka‑alapú előrehaladás.  
- **Physical Percentage Complete** – a fizikai előrehaladás (ha be van állítva).

```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```

Futtassa ezt a ciklust minden feladatra, amelyet nyomon kell követnie. A kimenet egyértelmű képet ad arról, **hogyan lehet előrehaladást kapni** minden munkatételhez.

## Common Use Cases
- **Műszerfal jelentés:** A százalékokat lekérve betáplálja őket BI eszközökbe.  
- **Automatizált riasztások:** Értesítéseket indít, amikor egy feladat `PERCENT_COMPLETE` értéke egy küszöb alá esik.  
- **Erőforrás kiegyenlítés:** A `PERCENT_WORK_COMPLETE` alapján módosítja a hozzárendeléseket, hogy a menetrend reális maradjon.

## Troubleshooting & Tips
- **Null értékek:** Győződjön meg arról, hogy a projektfájl valóban tartalmazza a lekérdezett mezőket; egyes régebbi .mpp fájlokban hiányozhat a `PHYSICAL_PERCENT_COMPLETE`.  
- **Teljesítmény:** Nagyon nagy projektek esetén fontolja meg a `TaskCollection` lapozását vagy a feladatazonosító szerinti szűrést a memóriahasználat csökkentése érdekében.  
- **Licenc hibák:** Ha licencfigyelmeztetéseket lát, ellenőrizze, hogy egy érvényes Aspose.Tasks licencfájl be legyen töltve a `Project` objektum létrehozása előtt.

## Frequently Asked Questions

**Q: Hol találom az Aspose.Tasks dokumentációt?**  
A: A dokumentáció elérhető [itt](https://reference.aspose.com/tasks/java/).

**Q: Hogyan tölthetem le az Aspose.Tasks könyvtárat Java-hoz?**  
A: Letöltheti [itt](https://releases.aspose.com/tasks/java/).

**Q: Van elérhető ingyenes próba?**  
A: Igen, ingyenes próbát [itt](https://releases.aspose.com/) érhet el.

**Q: Hol kaphatok támogatást az Aspose.Tasks-hez?**  
A: Látogassa meg a támogatási fórumot [itt](https://forum.aspose.com/c/tasks/15).

**Q: Hogyan szerezhetek ideiglenes licencet?**  
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhet.

**Additional Q&A**

**Q: Kiszámíthatom a feladat százalékát az Aspose.Tasks nélkül?**  
A: Megpróbálhatja saját maga parse-olni a .mpp binárist, de az Aspose.Tasks megbízható, teljes körű API-t biztosít, amely kezeli az összes szélhelyzetet.

**Q: Támogatja az Aspose.Tasks a Project Online fájlok olvasását?**  
A: Igen, betöltheti a Project Online-ból exportált fájlokat, amennyiben .mpp formátumban vannak mentve.

---

**Legutóbb frissítve:** 2026-02-23  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.11 (latest)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
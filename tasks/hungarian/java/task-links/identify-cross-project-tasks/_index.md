---
date: 2026-09-09
description: Ismerje meg, hogyan azonosíthatók a keresztprojekt feladatok az Aspose.Tasks
  for Java használatával. Fedezze fel a zökkenőmentes integrációt, a hatékony kezelést
  és a valós példákat.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Keresztprojekt feladatok azonosítása az Aspose.Tasks-ben
og_description: Keresztprojekt feladatok azonosítása az Aspose.Tasks for Java-ban.
  Ismerje meg, hogyan állítható be a dokumentum könyvtár, hogyan kérhetők le a feladatazonosítók,
  és hogyan kezelhetők hatékonyan a kapcsolt projektek.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Keresztprojekt feladatok azonosítása az Aspose.Tasks-ben – Java útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Keresztprojekt feladatok azonosítása az Aspose.Tasks-ben
url: /hu/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Keresztprojekt feladatok azonosítása az Aspose.Tasks-ben

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan azonosítsa a keresztprojekt feladatokat az Aspose.Tasks for Java segítségével. Akár egy egymástól függő ütemtervek portfólióját kezeli, akár külső függőségeket kell ellenőriznie, az alábbi lépések megmutatják, hogyan találja meg azokat a feladatokat, amelyek más projektfájlokra hivatkoznak, hogyan szerezze meg azonosítóikat, és hogyan dolgozzon velük programozottan.

## Gyors válaszok
- **Mi jelenti a „keresztprojekt feladatok azonosítása”?** Ez azt jelenti, hogy megtaláljuk azokat a feladatokat, amelyek egy másik projektfájlban lévő feladatokra hivatkoznak vagy azoktól függenek.  
- **Melyik metódus írja ki a feladat azonosítót?** Használja az `externalTask.get(Tsk.ID)`-t a feladat azonosító kiírásához.  
- **Hogyan állítható be a dokumentum könyvtár?** A mappa útvonalát egy `String` változóhoz kell rendelni (például `dataDir`).  
- **Melyik tulajdonság ad vissza egy feladatot UID alapján?** Hívja a `getChildren().getByUid(yourUid)`-t.  
- **Szükség van licencre a termelési használathoz?** Igen, egy érvényes Aspose.Tasks licenc szükséges a kereskedelmi telepítésekhez.

## Mi az a „keresztprojekt feladatok azonosítása”?
A keresztprojekt feladatok azonosítása lehetővé teszi a feladatok közötti kapcsolatok nyomon követését több Microsoft Project fájl között. Azáltal, hogy megtaláljuk azokat a feladatokat, amelyek külső ütemtervekre hivatkoznak vagy azoktól függenek, megérthetjük, hogyan lépnek kölcsönhatásba a munkák a projekt határain túl, elkerülhetjük a duplikált erőfeszítéseket, és pontos idővonalakat tarthatunk fenn. Ez a képesség elengedhetetlen nagy méretű portfóliók esetén, ahol a feladatok megosztottak vagy külső ütemtervektől függenek.

## Miért használja az Aspose.Tasks for Java-t?
Az Aspose.Tasks for Java **50+ bemeneti és kimeneti formátumot** támogat (beleértve az MPP, MPX, XML és CSV formátumokat), és akár **10 000 feladatot** képes feldolgozni a projektfájl teljes betöltése nélkül. A könyvtár bármely JVM‑kompatibilis platformon működik, nem igényel Microsoft Project telepítést, és teljes API hozzáférést biztosít az azonosítókhoz, UID‑ekhez, külső azonosítókhoz és a kapcsolódási metaadatokhoz.

## Előfeltételek
- Működő Java fejlesztői környezet (JDK 8 vagy újabb).  
- Az Aspose.Tasks for Java telepítve van. Letöltheti **[itt](https://releases.aspose.com/tasks/java/)**.  
- Érvényes Aspose.Tasks licencfájl, ha a kódot termelésben szeretné futtatni.

## Csomagok importálása
`Project` osztály egy Microsoft Project fájlt képvisel, a `Task` egy egyedi feladatot, a `Tsk` pedig feladatmező állandókat biztosít.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 1. lépés: dokumentum könyvtár beállítása
A `dataDir` karakterlánc a `.mpp` fájlokat tartalmazó mappa útvonalát tárolja.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 2. lépés: külső projekt betöltése
`Project externalProject` betölti a megadott külső projektfájlt vizsgálatra.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## 3. lépés: külső feladat lekérése UID alapján
`externalProject.getChildren().getByUid(uid)` egy feladatot kér le a külső projekt feladatgyűjteményéből az egyedi azonosítója alapján.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## 4. lépés: feladat azonosító kiírása (elsődleges felhasználási eset)
`externalTask.get(Tsk.ID)` visszaadja az adott feladathoz az Aspose.Tasks által hozzárendelt belső azonosítót.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## 5. lépés: eredeti (külső) feladat azonosító kiírása
`externalTask.get(Tsk.ExternalID)` lekéri a feladat eredeti azonosítóját, ahogyan az a forrás projektfájlban definiálva van.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Ismételje meg a fenti lépéseket minden további feladatra, amelyet a projektek között nyomon kell követni.

## Gyakori problémák és tippek
- **Útvonal hibák** – Győződjön meg róla, hogy a `dataDir` a megfelelő fájlelválasztóval (`/` vagy `\\`) végződik.  
- **UID nem található** – Ellenőrizze, hogy az UID létezik-e a külső projektben; használja a `externalProject.getRootTask().getChildren().size()`-t az elérhető UID‑k listázásához.  
- **Licenc kivételek** – Hiányzó vagy érvénytelen licenc futásidőben licenckivételt dob.  
- **Nagy projektek** – 5 000 feladatnál nagyobb projektek esetén fontolja meg a `ProjectReader` használatát a `LoadOptions` zászlóval az adatok streameléséhez és a memóriahasználat csökkentéséhez.

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Tasks‑t más programozási nyelvekkel?**  
A: Igen, az Aspose.Tasks több nyelvet támogat, beleértve a Java‑t, a .NET‑et és egyebeket.

**Q: Hol találhatók részletes dokumentációk az Aspose.Tasks for Java‑hoz?**  
A: Tekintse meg a dokumentációt **[itt](https://reference.aspose.com/tasks/java/)**.

**Q: Van ingyenes próba az Aspose.Tasks for Java‑hoz?**  
A: Igen, ingyenes próbát kaphat **[itt](https://releases.aspose.com/)**.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks‑hez?**  
A: Ideiglenes licencet szerezhet **[itt](https://purchase.aspose.com/temporary-license/)**.

**Q: Segítségre van szüksége vagy konkrét kérdései vannak?**  
A: Látogassa meg az Aspose.Tasks támogatási fórumot **[itt](https://forum.aspose.com/c/tasks/15)**.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Projektmenedzsment feladatfüggőségek létrehozása az Aspose.Tasks-ben](/tasks/java/task-links/create-task-link/)
- [Projekt kezdő dátum beállítása és szülő‑gyermek feladatok kezelése az Aspose.Tasks-ben](/tasks/java/task-properties/parent-child-tasks/)
- [MPP projekt létrehozása Java‑ban – Feladat előrehaladás módosítása az Aspose.Tasks segítségével](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
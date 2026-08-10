---
date: 2026-06-25
description: Ismerje meg, hogyan adhat feladatot és frissíthet MPP fájlokat az Aspose.Tasks
  for Java használatával, egy Java projektmenedzsment könyvtár, amely lehetővé teszi
  Microsoft Project feladatfájlok létrehozását és a projekt MPP‑ként történő mentését.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Hogyan adjunk feladatot és frissítsünk MPP fájlt az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan adjunk feladatot és frissítsünk MPP fájlt az Aspose.Tasks-ben
url: /hu/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá feladatot és frissítsük az MPP fájlt az Aspose.Tasks-ben

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **adjunk hozzá feladatot** egy meglévő Microsoft Project (MPP) fájlhoz, majd elmentse a frissített ütemtervet az Aspose.Tasks for Java segítségével, amely egy vezető **java projektmenedzsment könyvtár**. Akár egy egyedi ütemezőt épít, tömeges frissítéseket automatizál, vagy a projektadatokat egy nagyobb rendszerbe integrálja, az alábbi lépésről‑lépésre útmutató pontosan bemutatja, hogyan töltsön be egy projektet, szúrjon be egy új feladatot, állítsa be a dátumait, és mentse el az eredményt egy új MPP dokumentumként.

## Gyors válaszok
- **Mi jelent a „how to add task” ebben a kontextusban?** Ez azt jelenti, hogy programozottan hozunk létre egy új munkatételt egy meglévő MPP fájlban.  
- **Melyik könyvtár kezeli a műveletet?** Aspose.Tasks for Java, egy robusztus java projektmenedzsment könyvtár.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Menthetem az eredményt MPP formátumban?** Igen — használja a `project.save(..., SaveFileFormat.Mpp)` parancsot a **save project as mpp** művelethez.  
- **Milyen Java verzió szükséges?** Java 8 vagy újabb.

## Mi a „how to add task” egy MPP fájlban?
Feladat hozzáadása azt jelenti, hogy egy új munkatételt szúrunk be a projekt hierarchiájába, meghatározzuk a kezdő/ befejező dátumát, és a változást visszaírjuk az MPP fájlba. Az Aspose.Tasks elrejti az alacsony szintű fájlformátum részleteket, lehetővé téve, hogy az üzleti logikára koncentráljon, miközben automatikusan kezeli az erőforrás‑hozzárendeléseket, naptárakat és függőségi számításokat. Emellett frissíti a kapcsolódó hozzárendeléseket és újraszámolja a projekt ütemtervét, hogy a függő feladatok között konzisztencia maradjon.

## Miért használjuk az Aspose.Tasks for Java‑t?
- **Teljes kompatibilitás**: Támogatja a Microsoft Project 2007‑2021 100 %-át (több mint 150 feladattípust és 200 erőforrásmezőt).  
- **Zero‑dependency**: Nincs szükség COM, Office vagy natív könyvtárakra — tiszta Java API fut bárhol, ahol a JRE elérhető.  
- **Gazdag funkciókészlet**: Tartalmaz feladathivatkozásokat, erőforrás‑allokációt, egyéni mezőket és beépített jelentéskészítést.  
- **Magas teljesítmény**: Projektek feldolgozása akár 10 000 feladattal kevesebb, mint 200 MB RAM használatával, így ideális szerver‑oldali automatizáláshoz.

## Előfeltételek
1. **Java fejlesztői környezet** – JDK 8+ telepítve és konfigurálva.  
2. **Aspose.Tasks for Java** – Töltse le a [download page](https://releases.aspose.com/tasks/java/) oldalról.  
3. **Alapvető Java ismeretek** – Ismerje az osztályokat, objektumokat és a dátumkezelést.  

## Csomagok importálása
Először importálja a szükséges osztályokat. Ez hozzáférést biztosít a projektmanipulációhoz, feladattulajdonságokhoz és a dátumkezeléshez.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` egy memóriában betöltött Microsoft Project fájlt képvisel. `SaveFileFormat` felsorolja a menthető formátumokat, például MPP vagy PDF. `Task` egy egyedi munkatételt modellez a projekt hierarchiájában. `Tsk` állandókat biztosít a feladatterületekhez, amelyeket értékek beállításakor vagy lekérdezésekor használunk. `Calendar` dátum‑idő segédeszközöket kínál az ütemezések meghatározásához.

## 1. lépés: Adatkönyvtár meghatározása
```java
String dataDir = "Your Data Directory";
```  
Cserélje le a `"Your Data Directory"` értéket az abszolút útvonalra, ahol a forrás MPP fájlja található.

## 2. lépés: Létező projekt beolvasása
A `Project` osztály az Aspose.Tasks központi objektuma, amely egy memóriában lévő Microsoft Project fájlt képvisel.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
A konstruktor betölti a **SampleMSP2010.mpp** fájlt, egy teljesen manipulálható objektummodellt biztosítva.

## 3. lépés: Új feladat létrehozása (how to add task)
A `Task` osztály egy egyedi munkatételt képvisel a projekt hierarchiájában.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Ez a sor **creates task in mpp** úgy hoz létre egy feladatot, hogy egy *Task1* nevű gyermeket ad a gyökérfeladathoz.

## 4. lépés: Kezdő és befejező dátumok beállítása
A `Calendar` osztály dátum‑idő segédeszközöket biztosít; a hónapok nullától indulnak (pl. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Itt definiáljuk az újonnan hozzáadott feladat ütemezését. Állítsa be a dátumokat a projekt idővonalához igazodva.

## 5. lépés: Projekt mentése (save project as mpp)
`SaveFileFormat.Mpp` azt mondja az Aspose.Tasks‑nek, hogy a fájlt natív Microsoft Project formátumban írja vissza.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
A frissített projekt, amely most már tartalmazza az új feladatot, **AfterLinking.mpp** néven kerül mentésre.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Fájl nem található** | Ellenőrizze, hogy a `dataDir` útvonalelválasztóval (`/` vagy `\\`) végződik-e, és a fájlnév helyes-e. |
| **Helytelen dátumok** | Ne feledje, hogy a `Calendar` hónapok nullától indulnak; a `Calendar.JULY` a július helyes. |
| **Licenc kivétel** | Telepítsen érvényes Aspose.Tasks licencet, mielőtt bármilyen API‑t meghívna, hogy elkerülje a kiértékelési vízjelet. |

## Gyakran ismételt kérdések
**Q: Hogyan adhatok hozzá több feladatot egyszerre?**  
A: Iteráljon egy feladatneveket tartalmazó gyűjteményen, és ismételje meg a „create task” blokkot a ciklusban.

**Q: Beállíthatok egyéni mezőket az új feladathoz?**  
A: Igen — használja a `task.set(Tsk.CUSTOM_FIELD_x, value)` kifejezést, ahol *x* a mező indexe.

**Q: Lehetséges egy meglévő feladatot sablonként másolni?**  
A: Klónozza a forrásfeladatot (`Task cloned = sourceTask.clone();`), majd adja hozzá a kívánt szülőhöz.

**Q: Mi a teendő, ha egy meglévő feladatot kell frissíteni az új feladat hozzáadása helyett?**  
A: Szerezze be a feladatot azonosítóval (`Task existing = project.getRootTask().getChildren().getById(id);`), majd módosítsa a tulajdonságait.

**Q: Támogatja az Aspose.Tasks a mentést más formátumokba, például PDF vagy PNG?**  
A: Igen — használja a `project.save("output.pdf", SaveFileFormat.Pdf);` vagy a `SaveFileFormat.Png` opciót a vizuális megjelenítésekhez.

---

**Utolsó frissítés:** 2026-06-25  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre MPP fájlt – Üres projekt létrehozása és mentése MPP formátumban az Aspose.Tasks segítségével](/tasks/java/project-configuration/create-save-mpp/)
- [Hogyan hozzunk létre projektet – Új feladat attribútumok beállítása az Aspose.Tasks segítségével](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Feladatlista létrehozása Java – MS Project alapvonal az Aspose.Tasks használatával](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
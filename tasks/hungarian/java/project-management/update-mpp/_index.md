---
date: 2025-12-28
description: Tanulja meg, hogyan adjon hozzá feladatot és frissítse az MPP fájlokat
  az Aspose.Tasks for Java, egy Java projektmenedzsment könyvtár segítségével. Kövesse
  lépésről‑lépésre útmutatónkat, hogy feladatot hozzon létre MPP-ben, és a projektet
  MPP formátumban mentse.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan adjunk hozzá feladatot és frissítsük az MPP-fájlt az Aspose.Tasks-ben
url: /hu/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá feladatot és frissítsünk MPP fájlt az Aspose.Tasks-ben

## Bevezetés
Ebben az oktatóanyagban bemutatjuk, **hogyan adjunk hozzá feladatot** és hogyan frissítsünk egy MPP fájlt az Aspose.Tasks for Java segítségével, amely egy vezető **java project management library**. Akár egy egyedi ütemezőt építesz, akár programozottan kell módosítanod meglévő projektterveket, ez az útmutató minden lépésen végigvezet – a fájl betöltésétől az új MPP dokumentumként történő mentésig.

## Gyors válaszok
- **Mi jelent a “how to add task” ebben a kontextusban?** Ez programozottan új feladat létrehozását jelenti egy meglévő Microsoft Project (MPP) fájlban.  
- **Melyik könyvtár kezeli a műveletet?** Aspose.Tasks for Java, egy robusztus java project management library.  
- **Szükségem van licencre?** Fejlesztéshez egy ingyenes próba elegendő; termeléshez kereskedelmi licenc szükséges.  
- **Menthetjük a végeredményt MPP formátumban?** Igen – használja a `project.save(..., SaveFileFormat.Mpp)` parancsot a **save project as mpp** elvégzéséhez.  
- **Milyen Java verzió szükséges?** Java 8 vagy újabb.

## Mi az a “how to add task” egy MPP fájlban?
Feladat hozzáadása azt jelenti, hogy egy új munkatételt illesztünk be a projekt hierarchiájába, meghatározzuk a kezdő‑ és befejező dátumait, majd a változást visszaírjuk az MPP fájlba. Az Aspose.Tasks elrejti az alacsony szintű fájlformátum részleteket, így a vállalati logikára koncentrálhat.

## Miért használjuk az Aspose.Tasks for Java-t?
- **Teljes kompatibilitás** a Microsoft Project 2007‑2021 fájlokkal.  
- **Nincs COM vagy Office telepítés** szükséges – tiszta Java API.  
- **Gazdag funkciókészlet**: feladatkapcsolatok, erőforrás‑allokáció, egyéni mezők és még sok más.  
- **Magas teljesítmény** nagy projektfájlok esetén, ami ideálissá teszi szerver‑oldali automatizáláshoz.

## Előfeltételek
1. **Java fejlesztői környezet** – JDK 8+ telepítve és konfigurálva.  
2. **Aspose.Tasks for Java** – Töltse le a [letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **Alapvető Java ismeretek** – Osztályok, objektumok és dátumkezelés ismerete.

## Csomagok importálása
Először importálja a szükséges osztályokat. Ez hozzáférést biztosít a projektmanipulációhoz, feladattulajdonságokhoz és dátumkezeléshez.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 1. lépés: Adatkönyvtár meghatározása
```java
String dataDir = "Your Data Directory";
```
Cserélje le a `"Your Data Directory"` értéket a teljes elérési útra, ahol a forrás MPP fájlja található.

## 2. lépés: Létező projekt beolvasása
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
A `Project` konstruktor betölti a **SampleMSP2010.mpp** fájlt, egy manipulálható objektummodellt biztosítva.

## 3. lépés: Új feladat létrehozása (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Ez a sor **creates task in mpp** úgy hozza létre a feladatot, hogy egy *Task1* nevű gyermeket ad a gyökérfeladathoz.

## 4. lépés: Kezdő és befejező dátumok beállítása
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Itt definiáljuk az újonnan hozzáadott feladat ütemezését. Állítsa be a dátumokat a projekt idővonalához igazodva.

## 5. lépés: Projekt mentése (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
A frissített projekt, amely már tartalmazza az új feladatot, **AfterLinking.mpp** néven kerül mentésre.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **File not found** | Ellenőrizze, hogy a `dataDir` útvonalelválasztóval (`/` vagy `\\`) végződik‑e, és a fájlnév helyes‑e. |
| **Incorrect dates** | Ne feledje, hogy a `Calendar` hónapjai nullától indulnak; a `Calendar.JULY` a július helyes értéke. |
| **License exception** | Telepítsen érvényes Aspose.Tasks licencet az API hívása előtt, hogy elkerülje a kiértékelési vízjelek megjelenését. |

## GYIK

### K: Kezelhet‑e az Aspose.Tasks for Java összetett projektstruktúrákat?
V: Igen, az Aspose.Tasks for Java robusztus funkciókat biztosít az összetett projektstruktúrák hatékony kezeléséhez.  

### K: Elérhető‑e ingyenes próba az Aspose.Tasks for Java‑hoz?
V: Igen, letölthet egy ingyenes próbaverziót a [weboldalról](https://releases.aspose.com/).  

### K: Támogatja‑e az Aspose.Tasks for Java a Microsoft Project fájlok különböző verzióit?
V: Teljes mértékben, az Aspose.Tasks for Java számos Microsoft Project fájlverziót támogat, beleértve az MPP, MPT és XML formátumokat.  

### K: Kaphatok ideiglenes licenceket az Aspose.Tasks for Java‑hoz?
V: Igen, ideiglenes licencek elérhetők tesztelési célokra. Szerezze be őket a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalon.  

### K: Hol kérhetek segítséget vagy támogatást az Aspose.Tasks for Java‑hoz?
V: Látogasson el az [Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15) bármilyen kérdés vagy segítség esetén.

## Gyakran Ismételt Kérdések
**K: Hogyan adhatok hozzá több feladatot egyszerre?**  
V: Iteráljon egy feladatneveket tartalmazó gyűjteményen, és ismételje meg a “create task” blokkot a cikluson belül.

**K: Beállíthatok‑e egyéni mezőket az új feladathoz?**  
V: Igen – használja a `task.set(Tsk.CUSTOM_FIELD_x, value)` szintaxist, ahol *x* a mező indexe.

**K: Lehetséges‑e egy meglévő feladatot sablonként másolni?**  
V: Klónozza a forrásfeladatot (`Task cloned = sourceTask.clone();`), majd adja hozzá a kívánt szülőhöz.

**K: Mi a teendő, ha egy meglévő feladatot kell frissíteni az új feladat hozzáadása helyett?**  
V: Szerezze be a feladatot azonosítóval (`Task existing = project.getRootTask().getChildren().getById(id);`) és módosítsa a tulajdonságait.

**K: Támogatja‑e az Aspose.Tasks a mentést más formátumokba, például PDF vagy PNG?**  
V: Igen – használja a `project.save("output.pdf", SaveFileFormat.Pdf);` vagy a `SaveFileFormat.Png` opciót a vizuális ábrázoláshoz.

---

**Utolsó frissítés:** 2025-12-28  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
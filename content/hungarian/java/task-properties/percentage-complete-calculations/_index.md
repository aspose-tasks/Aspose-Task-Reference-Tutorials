---
title: Teljesített százalékos számítások az Aspose.Tasks feladatokhoz
linktitle: Teljesített százalékos számítások az Aspose.Tasks feladatokhoz
second_title: Aspose.Tasks Java API
description: Fedezze fel az Aspose.Tasks for Java szolgáltatást, és egyszerűsítse a projekt előrehaladásának nyomon követését. Könnyedén kiszámíthatja a feladat százalékát a hatékony projektmenedzsment érdekében.
type: docs
weight: 25
url: /hu/java/task-properties/percentage-complete-calculations/
---
## Bevezetés
Üdvözöljük részletes útmutatónkban a feladat százalékos számításainak elsajátításáról az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy hatékony Java-könyvtár, amelyet a Microsoft Project fájlokkal való munkára terveztek, és robusztus funkciókat kínál a projektmenedzsmenthez. Ebben az oktatóanyagban a teljes százalékos számításokra fogunk összpontosítani, amelyek olyan ismereteket biztosítanak Önnek, amelyek segítségével hatékonyan nyomon követheti és elemzi a projekt előrehaladását.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- Java fejlesztői környezet: Győződjön meg arról, hogy a Java telepítve van a rendszeren.
-  Aspose.Tasks Library: Töltse le a Java Aspose.Tasks könyvtárat innen[ez a link](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Kezdjük az Aspose.Tasks for Java projekthez szükséges csomagok importálásával. Helyezze be a következő kódrészletet a projektbe:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Most részletezzük az egyes lépéseket részletes magyarázattal.
## 1. lépés: Csomagok importálása
Első lépésben importáljuk az Aspose.Tasks projektünk beállításához szükséges csomagokat.
## 2. lépés: Dokumentumkönyvtár beállítása
 Határozza meg a dokumentumkönyvtár elérési útját a`dataDir`változó. Győződjön meg arról, hogy a Microsoft Project fájl, például a „Software Development.mpp” ebben a könyvtárban van.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
```
## 3. lépés: A projekt betöltése
 Inicializáljon egy újat`Project` objektumot, és töltse be a Microsoft Project fájlt a projektpéldányba.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## 4. lépés: Feladatgyűjtemény lekérése
 Szerezze meg a projekt gyökérfeladatát, és töltse le gyermekeit gyűjteményként`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## 5. lépés: Nyomtatási százalék kész
Nézze át a gyűjtemény minden egyes feladatát, és nyomtassa ki a Percentage Complete, Percentage Work Complete és a Physical Percentage Complete.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Ismételje meg ezeket a lépéseket a projekt minden egyes feladatánál, hogy betekintést nyerjen az egyes feladatok folyamatába.
## Következtetés
Gratulálunk! Sikeresen elsajátította a feladat százalékos számításait az Aspose.Tasks for Java használatával. Ez a hatékony könyvtár lehetővé teszi a fejlesztők számára a projekt előrehaladásának hatékony kezelését és elemzését.
## GYIK
### K: Hol találom az Aspose.Tasks dokumentációt?
 A dokumentáció elérhető[itt](https://reference.aspose.com/tasks/java/).
### K: Hogyan tölthetem le az Aspose.Tasks könyvtárat Java számára?
 Letöltheti[itt](https://releases.aspose.com/tasks/java/).
### K: Van ingyenes próbaverzió?
Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### K: Hol kaphatok támogatást az Aspose.Tasks-hoz?
 Látogassa meg a támogatási fórumot[itt](https://forum.aspose.com/c/tasks/15).
### K: Hogyan szerezhetek ideiglenes engedélyt?
 Ideiglenes jogosítványt szerezhet[itt](https://purchase.aspose.com/temporary-license/).
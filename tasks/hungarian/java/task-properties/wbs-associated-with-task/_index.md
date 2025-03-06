---
title: WBS Aspose.Tasks feladathoz társítva
linktitle: WBS Aspose.Tasks feladathoz társítva
second_title: Aspose.Tasks Java API
description: A WBS elsajátítása Aspose.Tasks for Java segítségével – Tanulja meg a feladatok WBS kódjainak olvasását és újraszámozását. Növelje a projektmenedzsment hatékonyságát!
type: docs
weight: 36
url: /hu/java/task-properties/wbs-associated-with-task/
---
## Bevezetés
Üdvözöljük az Aspose.Tasks for Java projektmenedzsment világában! Ebben az oktatóanyagban az Aspose.Tasks for Java használatával kapcsolatos feladatokhoz kapcsolódó Work Breakdown Structure (WBS) bonyolultságaival foglalkozunk. Akár tapasztalt fejlesztő, akár csak most kezdi, ez az útmutató segít eligazodni a WBS-kódok hatékony kezelésének alapjaiban.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java Development Kit (JDK) telepítve a gépére.
-  Aspose.Tasks a Java könyvtárhoz letöltve és hozzáadva a projekthez. től lehet kapni[itt](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Győződjön meg róla, hogy importálja a szükséges csomagokat a projekt elindításához:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Olvassa el a WBS kódokat
Kezdjük a feladatokhoz kapcsolódó WBS kódok elolvasásával. Kovesd ezeket a lepeseket:
## 1. lépés: Töltse be a projektet
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## 2. lépés: Gyűjtse össze a feladatokat
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 3. lépés: Elemzés és testreszabás
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Ez a kódrészlet beolvassa és testreszabja a projektben lévő feladatokhoz társított WBS-kódokat.
## Újraszámozza a feladat WBS kódjait
Most pedig nézzük meg a feladatok WBS-kódjainak újraszámozását:
## 1. lépés: Töltse be a projektet
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## 2. lépés: Válassza az Összes feladat lehetőséget
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## 3. lépés: A kezdeti WBS kódok kiadása
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## 4. lépés: Számolja át a WBS kódokat
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## 5. lépés: Frissített WBS-kódok kiadása
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Ha követi ezeket a lépéseket, hatékonyan újraszámozza a projektben lévő feladatok WBS-kódjait.
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan kell WBS-kódokkal dolgozni az Aspose.Tasks for Java segítségével. Ez a tudás lehetővé teszi a projekt feladathierarchiájának hatékony kezelését és testreszabását.
## GYIK
### K: Hol találom az Aspose.Tasks for Java dokumentációját?
 V: A dokumentáció elérhető[itt](https://reference.aspose.com/tasks/java/).
### K: Hogyan tölthetem le az Aspose.Tasks for Java-t?
 V: Letöltheti[itt](https://releases.aspose.com/tasks/java/).
### K: Elérhető az Aspose.Tasks for Java ingyenes próbaverziója?
 V: Igen, ingyenes próbaverziót kaphat[itt](https://releases.aspose.com/).
### K: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?
 V: Látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) támogatásért.
### K: Kaphatok ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Igen, szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
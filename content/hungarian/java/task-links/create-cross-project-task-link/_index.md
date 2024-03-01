---
title: Hozzon létre projektközi feladathivatkozást az Aspose.Tasks alkalmazásban
linktitle: Hozzon létre projektközi feladathivatkozást az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Javítsa a projekt együttműködést az Aspose.Tasks for Java segítségével. Ismerje meg lépésről lépésre projektközi feladathivatkozások létrehozását. Növelje a hatékonyságot most!
type: docs
weight: 10
url: /hu/java/task-links/create-cross-project-task-link/
---
## Bevezetés
projektmenedzsment dinamikus világában a hatékonyság és az együttműködés a legfontosabb. Az Aspose.Tasks for Java robusztus megoldást kínál a projektkezelési képességek bővítésére. Ebben az oktatóanyagban a projektek közötti feladathivatkozások létrehozásának folyamatát mutatjuk be az Aspose.Tasks for Java használatával. Ez a részletes útmutató felvértezi azokat a készségeket, amelyekkel zökkenőmentesen összekapcsolhatja a feladatokat a különböző projektek között, elősegítve a jobb koordinációt és az egyszerűsített munkafolyamatokat.
## Előfeltételek
Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- Java programozási ismeretek.
-  Aspose.Tasks for Java telepítve. Letöltheti a[Aspose.Tasks for Java kiadási oldal](https://releases.aspose.com/tasks/java/).
- A projektmenedzsment és a feladatfüggőségek alapvető ismerete.
## Csomagok importálása
A folyamat elindításához importáljuk a szükséges csomagokat a Java környezetbe. Ez biztosítja, hogy hozzáférjen az Aspose.Tasks for Java funkciókhoz. Használja a következő kódrészletet:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Most bontsuk fel a fenti kódot érthető lépésekre:
## 1. lépés: Állítsa be környezetét
Mielőtt belemerülne a kódba, győződjön meg arról, hogy telepítve van a Java, és az Aspose.Tasks for Java könyvtár megfelelően van hozzáadva a projekthez.
## 2. lépés: Hozzon létre egy projektpéldányt
Új projekt inicializálása az Aspose.Tasks könyvtár használatával:
```java
Project project = new Project();
```
## 3. lépés: Összefoglaló feladat hozzáadása
Hozzon létre egy összefoglaló feladatot a kapcsolódó feladatok rendszerezéséhez és kezeléséhez:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## 4. lépés: Külső feladat hozzáadása
Ha egy másik projektből származó feladatra szeretne hivatkozást létrehozni, adjon hozzá egy külső feladatot az összefoglaló feladathoz:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## 5. lépés: Helyi feladat hozzáadása
Adjon hozzá egy helyi feladatot az összefoglaló feladathoz. Ez lesz a külső feladathoz kapcsolódó feladat:
```java
Task t = summary.getChildren().add("Task");
```
## 6. lépés: Feladathivatkozás létrehozása
Hozzon létre feladatkapcsolatot a külső feladat és a helyi feladat között:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## 7. lépés: Eredmények megjelenítése
Végül jelenítse meg az átalakítás eredményét:
```java
System.out.println("Process completed Successfully");
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan hozhat létre projektközi feladathivatkozásokat az Aspose.Tasks for Java használatával. Ez a funkcionalitás fokozza az együttműködést és a koordinációt a projektmenedzsmentben, biztosítva a zökkenőmentes integrációt a különböző projektek feladatai között.
## GYIK
### Összekapcsolhatok több külső projektből származó feladatokat ugyanabban az összefoglaló feladatban?
Igen, ugyanazon összefoglaló feladaton belül különböző külső projektekből származó feladatokat is összekapcsolhat, hasonló folyamatot követve.
### Mi történik, ha a csatolt projektben a külső feladat módosul?
A külső feladat minden módosítása az aktuális projektben szereplő kapcsolódó feladatban is megjelenik.
### Lehetséges hivatkozásokat létrehozni a feladatok között különböző fájlformátumokban?
Igen, az Aspose.Tasks for Java támogatja a feladatok összekapcsolását a projektek között különböző fájlformátumokban.
### Leválaszthatom a feladatok összekapcsolását, miután összekapcsolták őket projektekkel?
Igen, leválaszthatja a feladatokat, ha eltávolítja a feladathivatkozást a megfelelő Aspose.Tasks metódusokkal.
### Vannak-e korlátozások a projektek között összekapcsolható feladatok számában?
Az összekapcsolható feladatok száma az Aspose.Tasks licenc képességeitől és korlátaitól függ.
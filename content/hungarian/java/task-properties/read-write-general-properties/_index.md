---
title: A feladat tulajdonságainak elsajátítása az Aspose.Tasks-ban
linktitle: Olvassa el és írja be a feladatok általános tulajdonságait az Aspose.Tasks programban
second_title: Aspose.Tasks Java API
description: Fedezze fel az Aspose.Tasks for Java erejét a feladat tulajdonságainak könnyed kezelésében. Könnyedén olvashat és írhat lépésenkénti útmutatónk segítségével.
type: docs
weight: 26
url: /hu/java/task-properties/read-write-general-properties/
---
## Bevezetés
Használja ki a Java feladatkezelésben rejlő teljes potenciált az Aspose.Tasks segítségével. Ebben az átfogó útmutatóban az Aspose.Tasks for Java használatával kapcsolatos feladatok általános tulajdonságainak olvasásával és írásával foglalkozunk. Akár tapasztalt fejlesztő, akár kezdő, ez az oktatóanyag felvértezi azokat a készségeket, amelyek segítségével könnyedén kezelheti a feladat tulajdonságait.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Tasks a Java könyvtárhoz letöltve és beállítva. A letöltési linket megtalálod[itt](https://releases.aspose.com/tasks/java/).
- Kódszerkesztő, például IntelliJ IDEA vagy Eclipse.
## Csomagok importálása
dolgok elindításához importálja a szükséges csomagokat a Java projektbe. Ez a lépés biztosítja, hogy hozzáférjen az Aspose.Tasks funkciókhoz. Íme egy részlet, amely eligazítja:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Olvasás A feladatok általános tulajdonságai
## 1. lépés: Hozzon létre egy feladatot
Kezdje egy feladat létrehozásával a projektben. Ez magában foglalja a feladat nevének, kezdési dátumának és egyéb releváns részleteknek a beállítását. Íme egy példa:
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## 2. lépés: Olvassa el a Feladat tulajdonságait
Most, hogy létrehozott egy feladatot, keressük le és jelenítsük meg annak általános tulajdonságait. Ezt a következő kódrészlet valósítja meg:
```java
// Olvasás A feladatok általános tulajdonságai
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## A feladatok általános tulajdonságainak írása
## 3. lépés: Töltse be a projektet és hozzon létre gyűjtőt
 Általános tulajdonságok írásához töltsön be egy meglévő projektet, és állítsa be a`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## 4. lépés: Tulajdonságok elemzése és megjelenítése
Végül elemezze át az összegyűjtött feladatokat, és jelenítse meg tulajdonságaikat:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Gratulálunk! Sikeresen elolvasta és leírta a feladatok általános tulajdonságait az Aspose.Tasks for Java használatával.
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk a feladat tulajdonságainak zökkenőmentes kezelésének alapvető lépéseit az Aspose.Tasks for Java segítségével. Ezen technikák elsajátításával javíthatja Java-fejlesztési készségeit, és egyszerűsítheti projektjei feladatkezelését.
## GYIK
### Az Aspose.Tasks kompatibilis a Java 11-gyel?
Igen, az Aspose.Tasks kompatibilis a Java 11 és újabb verzióival.
### Használhatom az Aspose.Tasks-t kereskedelmi projektekhez?
 Teljesen! Az Aspose.Tasks hatékony eszköz személyes és kereskedelmi projektekhez egyaránt. Látogatás[itt](https://purchase.aspose.com/buy) az engedélyezési lehetőségek feltárására.
### Hogyan szerezhetek ideiglenes licencet tesztelési célból?
 Szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/) teszteléshez és értékeléshez.
### Hol találok közösségi támogatást az Aspose.Tasks számára?
 Csatlakozzon a közösségi beszélgetéshez a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) segítségért és együttműködésért.
### Vannak referenciaként használható mintaprojektek?
 Tekintse meg a dokumentáció példák szakaszát[itt](https://reference.aspose.com/tasks/java/) mintaprojektekhez és kódrészletekhez.
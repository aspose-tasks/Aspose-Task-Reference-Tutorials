---
title: A feladat befejezési dátumának felosztása az Aspose.Tasks-ban
linktitle: A feladat befejezési dátumának felosztása az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan oszthatja fel könnyedén a feladatok befejezési dátumát az Aspose.Tasks for Java segítségével. Javítsa a projektmenedzsmentet pontos idővonalakkal.
weight: 28
url: /hu/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A feladat befejezési dátumának felosztása az Aspose.Tasks-ban

## Bevezetés
projektmenedzsmentben a feladatok ütemezésének megértése kulcsfontosságú a projekt sikeres befejezéséhez. Az Aspose.Tasks for Java hatékony funkciókat kínál a projektfeladatok hatékony kezeléséhez. Ebben az oktatóanyagban a feladatok befejezési dátumainak felosztásával foglalkozunk az Aspose.Tasks használatával, amely segít a projektek ütemezésének hatékony kezelésében.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- Java programozási alapismeretek.
-  Aspose.Tasks for Java könyvtár telepítve. Letöltheti[itt](https://releases.aspose.com/tasks/java/).
- Java fejlesztői környezet beállítva.
## Csomagok importálása
Kezdje azzal, hogy belefoglalja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.tasks.*;
```
## 1. lépés: Keressen egy megosztott feladatot
Keresse meg a projekten belül felosztani kívánt feladatot:
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Olvassa el a projektet
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## 2. lépés: Keresse meg a projekt naptárát
Töltse le a projekt naptárát a pontos dátum kiszámításához:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## 3. lépés: Számítsa ki a feladat befejezési dátumát különböző időtartamokkal
Most számítsa ki a feladat befejezési dátumát különböző időtartamokra:
## 3.1. lépés: 8 órás időtartam
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Ismételje meg a fenti kódot különböző időtartamokhoz, és ennek megfelelően állítsa be az órákat.
## Következtetés
feladatok befejezési dátumának manipulálásának elsajátítása kulcsfontosságú a hatékony projektmenedzsmenthez. Az Aspose.Tasks for Java leegyszerűsíti ezt a folyamatot, lehetővé téve a projekt ütemezésének egyszerűsítését.
## GYIK
### 1. kérdés: Hogyan tölthetem le az Aspose.Tasks for Java-t?
 V1: Letöltheti[itt](https://releases.aspose.com/tasks/java/).
### 2. kérdés: Hol találom az Aspose.Tasks dokumentációját?
 V2: Lásd a dokumentációt[itt](https://reference.aspose.com/tasks/java/).
### 3. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?
 V3: Szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### 4. kérdés: Hol kérhetek támogatást az Aspose.Tasks-hoz?
 4. válasz: Látogassa meg a támogatási fórumot[itt](https://forum.aspose.com/c/tasks/15).
### 5. kérdés: Megvásárolhatom az Aspose.Tasks-t?
 A5: Igen, megvásárolhatja[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

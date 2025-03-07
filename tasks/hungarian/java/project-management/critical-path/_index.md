---
title: Számítsa ki a kritikus MS projekt elérési útját az Aspose.Tasks programban
linktitle: Számítsa ki a kritikus útvonalat az Aspose.Tasks projektekben
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan számíthatja ki a kritikus útvonalat az MS Projectben az Aspose.Tasks for Java segítségével. Ez lépésről lépésre útmutatást ad a hatékony projektmenedzsmenthez.
weight: 10
url: /hu/java/project-management/critical-path/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Számítsa ki a kritikus MS projekt elérési útját az Aspose.Tasks programban

## Bevezetés
Ebben az oktatóanyagban végigvezetjük az MS Project kritikus elérési útjának kiszámításán az Aspose.Tasks for Java használatával. A kritikus út elengedhetetlen a projektmenedzsmenthez, mivel segít azonosítani azokat a feladatokat, amelyeket időben el kell végezni, hogy a projekt általános ütemezése ne csússzon el.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Tasks a Java könyvtárhoz letöltve és hozzáadva a projekthez. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Kezdésként importálja a szükséges csomagokat a Java osztályba:
```java
import com.aspose.tasks.*;
```
## 1. lépés: Állítsa be a Data Directory-t
Határozza meg az adatkönyvtár elérési útját, ahol az MS Project fájl található.
```java
String dataDir = "Your Data Directory";
```
## 2. lépés: Töltse be az MS Project fájlt
Töltse be az MS Project fájlt az Aspose.Tasks könyvtár használatával.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 3. lépés: Állítsa be a számítási módot
A kritikus út kiszámításának engedélyezéséhez állítsa a számítási módot automatikusra.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## 4. lépés: Feladatok hozzáadása
Adjon hozzá feladatokat a projekthez. Ebben a példában három részfeladatot adunk hozzá.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## 5. lépés: Hozzon létre feladathivatkozásokat
Hozzon létre feladathivatkozásokat a feladatok közötti függőségek meghatározásához.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## 6. lépés: Jelenítse meg a kritikus útvonalat
A projekt kritikus útvonalának lekérése és megjelenítése.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## 7. lépés: Eredmény megjelenítése
Jelenítsen meg egy üzenetet, amely jelzi a folyamat sikeres befejezését.
```java
System.out.println("Process completed Successfully");
```

## Következtetés
A kritikus útvonal kiszámítása az MS Projectben az Aspose.Tasks for Java használatával kulcsfontosságú a hatékony projektmenedzsmenthez. Az oktatóanyagban ismertetett lépések követésével pontosan azonosíthatja a projekt idővonala szempontjából kritikus feladatok sorrendjét.
## GYIK
### K: Használhatom az Aspose.Tasks for Java-t az MS Project fájlok bármely verziójával?
V: Igen, az Aspose.Tasks for Java támogatja az MS Project fájlok különféle verzióit, beleértve az .mpp fájlokat az MS Project 2003-tól az MS Project 2019-ig.
### K: Elérhető az Aspose.Tasks for Java ingyenes próbaverziója?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Hol találok támogatást az Aspose.Tasks for Java számára?
 V: Támogatást találhat a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Igen, vásárolhat ideiglenes licencet a következőtől[itt](https://purchase.aspose.com/temporary-license/).
### K: Hogyan vásárolhatok Aspose.Tasks for Java-t?
 V: Az Aspose.Tasks for Java megvásárolható a webhelyen[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

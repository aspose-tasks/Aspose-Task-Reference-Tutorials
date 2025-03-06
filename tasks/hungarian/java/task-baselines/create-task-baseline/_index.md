---
title: Hozzon létre MS Project Task Baseline-t az Aspose.Tasks programban
linktitle: Feladatbázis létrehozása az Aspose.Tasks programban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan hozhat létre Microsoft Project-feladatbázist Java nyelven az Aspose.Tasks segítségével, amely egy hatékony könyvtár a projektadatok könnyű kezeléséhez.
weight: 11
url: /hu/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hozzon létre MS Project Task Baseline-t az Aspose.Tasks programban

## Bevezetés
Ebben az oktatóanyagban a Microsoft Project feladat alapvonalának létrehozásának folyamatát mutatjuk be az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy hatékony Java könyvtár, amely lehetővé teszi a fejlesztők számára, hogy a Microsoft Project telepítése nélkül dolgozzanak Microsoft Project fájlokkal. Az Aspose.Tasks segítségével könnyedén kezelheti a projektadatokat, beleértve a feladatokat, az erőforrásokat és a naptárakat, a projektmenedzsment feladatok egyszerűsítése érdekében.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Az Aspose.Tasks for Java programhoz a JDK telepítése szükséges a rendszeren. A JDK letölthető és telepíthető az Oracle webhelyéről.
2.  Aspose.Tasks for Java Library: Töltse le az Aspose.Tasks for Java könyvtárat a[letöltési link](https://releases.aspose.com/tasks/java/) biztosítani.

## Csomagok importálása
Az Aspose.Tasks használatának megkezdéséhez a Java projektben importálja a szükséges csomagokat:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 1. lépés: Hozzon létre egy projektobjektumot
```java
Project project = new Project();
```
 Először hozzon létre egy újat`Project` tárgy. Ez az objektum a Microsoft Project fájlt képviseli, amellyel dolgozni fog.
## 2. lépés: Adjon hozzá egy feladatot a projekthez
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Használni a`getRootTask()` metódussal érje el a projekt gyökérfeladatát, majd adjon hozzá egy új feladatot a`add()` módszer. Adja meg a feladat nevét a zárójelben.
## 3. lépés: Állítsa be az alaphelyzetet a meghatározott feladatokhoz
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Adott feladatok alaphelyzetének beállításához hozzon létre egy feladatlistát (`myList` ebben az esetben), és töltse fel azokkal a feladatokkal, amelyekhez az alapértéket szeretné beállítani. Ezután használja a`setBaseline()` módszerrel, megadva az alaptípust és a feladatok listáját.
## 4. lépés: Állítsa be a teljes projekt alaphelyzetét
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternatív megoldásként beállíthat egy alapvonalat a teljes projekthez úgy, hogy egyszerűen meghívja a`setBaseline()` módszert a megadott alaptípussal.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan hozhat létre Microsoft Project-feladatok alapvonalát az Aspose.Tasks for Java használatával. A fent vázolt lépések követésével hatékonyan kezelheti a projektadatokat, és egyszerűen ésszerűsítheti a projektkezelési feladatokat.
## GYIK
### Használhatom az Aspose.Tasks for Java programot Microsoft Project telepítése nélkül?
Igen, az Aspose.Tasks for Java lehetővé teszi a Microsoft Project fájlokkal való munkát anélkül, hogy a Microsoft Projectet telepítenie kellene a rendszerére.
### Az Aspose.Tasks for Java kompatibilis a Microsoft Project különböző verzióival?
Igen, az Aspose.Tasks for Java támogatja a Microsoft Project különféle verzióit, biztosítva a kompatibilitást a különböző környezetekben.
### Manipulálhatom a projekt erőforrásait az Aspose.Tasks for Java használatával?
Az Aspose.Tasks for Java robusztus szolgáltatásokat nyújt a projekt erőforrásainak kezeléséhez, beleértve az erőforrások szükség szerinti hozzáadását, frissítését és eltávolítását.
### Az Aspose.Tasks for Java támogatja a feladatfüggőségek beállítását?
Igen, az Aspose.Tasks for Java segítségével könnyedén beállíthat feladatfüggőségeket, lehetővé téve a projekten belüli feladatok sorrendjének meghatározását.
### Elérhető technikai támogatás az Aspose.Tasks for Java számára?
 Igen, elérheti az Aspose.Tasks for Java technikai támogatását a következőn keresztül[támogatói fórum](https://forum.aspose.com/c/tasks/15), ahol kérdéseket tehet fel, és segítséget kérhet a közösségtől és az Aspose támogató személyzetétől.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

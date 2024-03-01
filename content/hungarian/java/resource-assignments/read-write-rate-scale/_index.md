---
title: Olvasási és írási arányskála az Aspose.Tasks erőforrás-hozzárendeléséhez
linktitle: Olvasási és írási arányskála az Aspose.Tasks erőforrás-hozzárendeléséhez
second_title: Aspose.Tasks Java API
description: Ezzel az átfogó oktatóanyaggal megtudhatja, hogyan kezelheti hatékonyan az erőforrás-hozzárendelések arányát az Aspose.Tasks for Java programban.
type: docs
weight: 20
url: /hu/java/resource-assignments/read-write-rate-scale/
---
## Bevezetés
Ebben az oktatóanyagban az erőforrás-hozzárendelési arányskála kezelésével foglalkozunk az Aspose.Tasks for Java használatával, amely egy robusztus könyvtár a Microsoft Project fájlokkal programozottan történő munkavégzéshez. Ha követi ezeket a lépéseket, hatékonyan tudja módosítani a Java-alkalmazások erőforrás-hozzárendeléseinek arányát.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java fejlesztői környezet: Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszerén.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat innen:[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először is importálnia kell a szükséges csomagokat az Aspose.Tasks funkciók használatához. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## 1. lépés: Állítsa be a projektet
Kezdje a Java-projekt beállításával, és vegye fel az Aspose.Tasks könyvtárat a függőségekbe.
## 2. lépés: Töltse be a projektfájlt
Töltse be a kezelni kívánt projektfájlt a Java alkalmazásba.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 3. lépés: Adjon hozzá egy feladatot
Adjon hozzá új feladatot a projekthez.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## 4. lépés: Határozza meg az erőforrásokat
Határozza meg az anyagi és nem anyagi erőforrásokat, és adja meg típusaikat.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## 5. lépés: Rendeljen erőforrásokat a feladathoz
Rendelje hozzá a korábban definiált erőforrásokat a feladathoz a ráta skála típusaival együtt.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## 6. lépés: Mentse el a projektet
Mentse el a projektet a módosított erőforrás-hozzárendelésekkel.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## 7. lépés: Erőforrás-hozzárendelések lekérése
Töltse be újra a mentett projektet, és kérje le az erőforrás-hozzárendeléseket az arányskála beállításainak ellenőrzéséhez.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Következtetés
Az Aspose.Tasks for Java erőforrás-hozzárendelési arányskála kezelése kulcsfontosságú a hatékony projektmenedzsmenthez. Ennek a lépésről-lépésre szóló útmutatónak a követésével zökkenőmentesen módosíthatja a Java-alkalmazások erőforrás-hozzárendelésének sebességi skála beállításait.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks for Java-t bármilyen Java IDE-vel?
V: Igen, az Aspose.Tasks for Java kompatibilis az összes fő Java IDE-vel, beleértve az IntelliJ IDEA-t, az Eclipse-t és a NetBeans-t.
### 2. kérdés: Az Aspose.Tasks támogatja az MPP-n kívül más fájlformátumokat is?
V: Igen, az Aspose.Tasks különféle fájlformátumokat támogat, beleértve az MPP-t, az XML-t és a HTML-t.
### 3. kérdés: Az Aspose.Tasks alkalmas vállalati szintű projektmenedzsmentre?
V: Természetesen az Aspose.Tasks átfogó szolgáltatásokat kínál bármilyen léptékű projektek kezelésére, így alkalmas vállalati szintű projektmenedzsmentre.
### 4. kérdés: Testreszabhatom-e az erőforrás-hozzárendeléseket a tarifaskálán túl is?
V: Igen, az Aspose.Tasks kiterjedt lehetőségeket biztosít az erőforrás-hozzárendelések testreszabásához, beleértve a költségek, a munka és az időtartam módosítását.
### 5. kérdés: Létezik közösségi fórum az Aspose.Tasks támogatására?
 V: Igen, az Aspose.Tasks fórumon találhat támogatást és kapcsolatba léphet más felhasználókkal[itt](https://forum.aspose.com/c/tasks/15).
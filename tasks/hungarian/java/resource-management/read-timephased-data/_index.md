---
title: Olvassa el az Aspose.Tasks erőforrásainak időfázisos adatait
linktitle: Olvassa el az Aspose.Tasks erőforrásainak időfázisos adatait
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kinyerhet időfázisú adatokat az MS Project erőforrásaiból az Aspose.Tasks for Java segítségével. Lépésről lépésre bemutató.
type: docs
weight: 15
url: /hu/java/resource-management/read-timephased-data/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük az MS Project erőforrások időfázisos adatainak olvasásának folyamatán az Aspose.Tasks for Java használatával. Ez a könyvtár hatékony funkciókat kínál a Microsoft Project fájlok programozott kezeléséhez.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. Letöltheti a[weboldal](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) és kövesse a telepítési utasításokat.
2.  Aspose.Tasks for Java Library: Töltse le az Aspose.Tasks for Java könyvtárat a[letöltési oldal](https://releases.aspose.com/tasks/java/) és kövesse a dokumentációban található telepítési utasításokat.

## Csomagok importálása
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## 1. lépés: A Data Directory beállítása
Először határozza meg azt a könyvtárat, ahol az MS Project fájl található.
```java
String dataDir = "Your Data Directory";
```
## 2. lépés: Olvassa el az MS Project sablonfájlt
Adja meg az MS Project sablonfájl nevét.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## 3. lépés: Olvassa be a bemeneti fájlt projektként
Olvassa el a bemeneti fájlt az Aspose.Tasks segítségével, és töltse be Project objektumként.
```java
Project project = new Project(dataDir + fileName);
```
## 4. lépés: Erőforrás lekérése azonosító alapján
Kérje le a kívánt erőforrást a projektből annak egyedi azonosítója (ID) alapján.
```java
Resource resource = project.getResources().getByUid(1);
```
## 5. lépés: Nyomtasson időfázisú adatokat az erőforrás-munkához
Nyomtassa ki az időfázisú adatokat az erőforrás-munkához.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## 6. lépés: Nyomtasson időfázisú adatokat az erőforrásköltséghez
Nyomtassa ki az időfázisú adatokat az erőforrásköltséghez.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell időfázisú adatokat olvasni az MS Project erőforrásaihoz az Aspose.Tasks for Java használatával. Ezen lépések követésével hatékonyan kinyerhet értékes információkat a projektfájlokból programozottan.
## GYIK
### Az Aspose.Tasks kezelhet más típusú projektfájlokat a Microsoft Projecten kívül?
Igen, az Aspose.Tasks különféle fájlformátumokat támogat, beleértve az MPP-t, az XML-t és a CSV-t.
### Az Aspose.Tasks kompatibilis a különböző Java fejlesztői környezetekkel?
Igen, az Aspose.Tasks kompatibilis az összes főbb Java IDE-vel és keretrendszerrel.
### Az Aspose.Tasks segítségével manipulálhatom a projektadatokat?
Természetesen az Aspose.Tasks kiterjedt API-kat biztosít a projektadatok létrehozásához, módosításához és elemzéséhez.
### Az Aspose.Tasks alkalmas vállalati szintű projektekre?
Igen, az Aspose.Tasks-t megbízhatósága és méretezhetősége miatt széles körben használják vállalati környezetben.
### Hol találok támogatást, ha problémákat tapasztalok az Aspose.Tasks használata során?
 Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) a közösség és a támogató csapat segítségéért.
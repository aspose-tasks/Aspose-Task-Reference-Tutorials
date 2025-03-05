---
title: MS Project Manipulation elsajátítása Aspose.Tasks for Java segítségével
linktitle: Bővített attribútumok hozzáadása az Aspose.Tasks erőforrás-hozzárendeléseihez
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan írhat hatékonyan MS Project információkat az Aspose.Tasks for Java használatával. Lépésről lépésre útmutató Java fejlesztőknek.
type: docs
weight: 10
url: /hu/java/resource-assignments/add-extended-attributes/
---
## Bevezetés
Ebben az oktatóanyagban bemutatjuk az Aspose.Tasks for Java használatát, amely egy hatékony könyvtár a Microsoft Project fájlok programozott kezeléséhez. Egy alapvető feladatra összpontosítunk: MS Project információk írására az Aspose.Tasks segítségével. Akár tapasztalt fejlesztő, akár csak most kezdi a Java programozási utat, ez az útmutató lépésről lépésre végigvezeti a folyamaton.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat. től szerezheti be[itt](https://releases.aspose.com/tasks/java/).
3. Integrált fejlesztői környezet (IDE): Válasszon egy IDE-t az Ön által preferált. Az IntelliJ IDEA-t vagy az Eclipse-t ajánljuk.

## Csomagok importálása
Először importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
# Bontsuk fel a példát több lépésre:
## 1. lépés: Állítsa be a Data Directory-t
Határozza meg a könyvtárat, ahol a projekt adatait tárolni kell.
```java
String dataDir = "Your Data Directory";
```
## 2. lépés: Hozzon létre projektpéldányt
Inicializáljon egy új projektpéldányt.
```java
Project project = new Project();
```
## 3. lépés: Állítsa be a Projektinformáció tulajdonságait
Állítsa be a projekt tulajdonságait, például kezdési dátumot, ütemezést a kezdéstől és állapotdátumot.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## 4. lépés: Projekt mentése XML-ként
Mentse el a projektet a frissített információkkal XML-fájlként.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan írjon MS Project információkat az Aspose.Tasks for Java segítségével. Ezzel az újonnan megszerzett tudással automatizálhatja a Microsoft Project fájlokkal kapcsolatos különféle feladatokat, javítva ezzel Java fejlesztői hatékonyságát.
## GYIK
### K: Használhatom az Aspose.Tasks for Java-t MS Project fájlok olvasásához?
V: Igen, az Aspose.Tasks for Java robusztus funkciókat biztosít az MS Project fájlok olvasásához és írásához.
### K: Az Aspose.Tasks for Java kompatibilis az MS Project különböző verzióival?
V: Természetesen az Aspose.Tasks for Java támogatja az MS Project különféle verzióit, biztosítva a különböző fájlformátumok közötti kompatibilitást.
### K: Vannak korlátozások az Aspose.Tasks for Java próbaverziójára vonatkozóan?
V: Bár a próbaverzió lehetővé teszi a könyvtár képességeinek felfedezését, bizonyos korlátai vannak, például vízjelek a kimeneti fájlokon.
### K: Hogyan kaphatok támogatást az Aspose.Tasks for Java számára?
 V: Kérhet segítséget az Aspose.Tasks közösségi fórumtól[itt](https://forum.aspose.com/c/tasks/15).
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Igen, rövid távú használatra ideiglenes licencek állnak rendelkezésre. Az egyiket beszerezheti[itt](https://purchase.aspose.com/temporary-license/).
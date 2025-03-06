---
title: Projektadatok olvasása az MS Project Database-ból az Aspose.Tasks programban
linktitle: Projektadatok olvasása a Microsoft Project Database-ból az Aspose.Tasks programban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan olvashat projektadatokat a Microsoft Project Database-ból az Aspose.Tasks for Java segítségével. Lépésről lépésre útmutató kódpéldákkal.
weight: 12
url: /hu/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektadatok olvasása az MS Project Database-ból az Aspose.Tasks programban

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan olvashatunk projektadatokat egy Microsoft Project Database-ból az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy hatékony Java API, amely lehetővé teszi a fejlesztők számára, hogy a Microsoft Project telepítése nélkül kezeljék a Microsoft Project dokumentumokat. Az ebben az útmutatóban vázolt lépések követésével megtanulhatja, hogyan lehet hatékonyan kivonni a projektadatokat egy adatbázisból, és elmenteni azokat a kívánt formátumban.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java programozási alapismeretek.
2. Java Development Kit (JDK) telepítve a rendszerére.
3. Aspose.Tasks a Java könyvtárhoz letöltve és konfigurálva a projektben.

## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## 1. lépés: Állítsa be az adatbázis-kapcsolatot
Először is be kell állítania a kapcsolatot a Microsoft Project Database-szal. Ez magában foglalja az adatbázis URL-címének, a kiszolgálónévnek, a portszámnak, az adatbázisnévnek, a felhasználónévnek és a jelszónak a megadását.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## 2. lépés: Adja hozzá a JDBC illesztőprogramot
Ezután hozzá kell adnia a JDBC illesztőprogramot a projekthez. Ez az illesztőprogram megkönnyíti a kommunikációt a Java alkalmazások és a Microsoft SQL Server adatbázis között.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## 3. lépés: Olvassa el a projektadatokat
 Most hozzon létre a`Project` objektumot, és töltse be a projektadatokat az adatbázisból a korábban meghatározott beállításokkal.
```java
Project project = new Project(settings);
```
## 4. lépés: Projektadatok mentése
Végül mentse a projekt adatait a kívánt formátumba. Ebben a példában XML fájlként mentjük el.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Gratulálunk! Sikeresen beolvassa a projektadatokat egy Microsoft Project Database-ból az Aspose.Tasks for Java használatával.

## Következtetés
Ebben az oktatóanyagban bemutattuk a projektadatok Microsoft Project Database-ból történő kiolvasásának folyamatát az Aspose.Tasks for Java használatával. A vázolt lépések követésével zökkenőmentesen kinyerheti a projektinformációkat, és igényei szerint módosíthatja azokat. Az Aspose.Tasks leegyszerűsíti a Microsoft Project dokumentumok kezelését, lehetővé téve az adatok hatékony kinyerését és kezelését.
## GYIK
### K: Az Aspose.Tasks használható projektadatok olvasására más adatbázisokból a Microsoft Projecten kívül?
V: Igen, az Aspose.Tasks támogatja a projektadatok olvasását különböző forrásokból, beleértve az XML-fájlokat, a Primavera- és a Microsoft Project-adatbázisokat.
### K: Az Aspose.Tasks kompatibilis a Microsoft Project különböző verzióival?
V: Igen, az Aspose.Tasks a Microsoft Project különböző verzióival való együttműködésre készült, így biztosítva a kompatibilitást és a zökkenőmentes integrációt.
### K: Módosíthatom a projektadatokat a mentés előtt?
V: Természetesen az Aspose.Tasks szolgáltatások széles skáláját kínálja a projektadatok kezeléséhez, például feladatok hozzáadásához, erőforrások frissítéséhez és projekttulajdonságok beállításához.
### K: Az Aspose.Tasks több kimeneti formátumot támogat?
V: Igen, az Aspose.Tasks különféle kimeneti formátumokat támogat, beleértve az XML-t, PDF-et, HTML-t, valamint az olyan képformátumokat, mint a PNG és a JPEG.
### K: Hol találhatok további támogatást vagy segítséget az Aspose.Tasks szolgáltatással kapcsolatban?
 V: További támogatásért vagy segítségért keresse fel az Aspose.Tasks fórumot, vagy tekintse meg a webhelyen elérhető dokumentációt.[itt](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

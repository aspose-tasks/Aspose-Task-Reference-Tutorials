---
title: MS Project Data mentése Excelbe az Aspose.Tasks programban
linktitle: Adatok mentése Excelbe az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan mentheti a Microsoft Project adatait Excel-fájlokba az Aspose.Tasks for Java segítségével. Egyszerű integráció a Java fejlesztők számára.
weight: 19
url: /hu/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Data mentése Excelbe az Aspose.Tasks programban

## Bevezetés
Az Aspose.Tasks for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal. Ebben az oktatóanyagban lépésről lépésre végigvezetjük az adatok projektfájlból Excel-fájlba mentésének folyamatán.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren. A JDK legújabb verzióját letöltheti és telepítheti az Oracle webhelyéről.
2.  Aspose.Tasks for Java Library: Töltse le az Aspose.Tasks for Java könyvtárat a[letöltési link](https://releases.aspose.com/tasks/java/) és vegye fel a Java projektbe.

## Csomagok importálása
Először is importálnia kell a szükséges csomagokat a Java-kódban az Aspose.Tasks használatához.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Bontsuk fel a megadott példát több lépésre:
## 1. lépés: Határozza meg az adatkönyvtár elérési útját
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"`az adatkönyvtár elérési útjával, ahol a Project fájl található.
## 2. lépés: Töltse be a projektfájlt
```java
Project project = new Project(dataDir + "project5.mpp");
```
Ez a kódsor betölti a "project5.mpp" nevű projektfájlt a megadott adatkönyvtárból.
## 3. lépés: Mentse el a projektet XLSX-ként
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Itt, a`save` metódussal menti a betöltött Project fájlt Excel fájlként "projekt1.xlsx" néven ugyanabban az adatkönyvtárban. Meghatározzuk a`SaveFileFormat.Xlsx` paramétert, hogy XLSX formátumban mentse el.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet adatokat menteni egy Microsoft Project fájlból Excel-fájlba az Aspose.Tasks for Java segítségével. A megadott lépések követésével zökkenőmentesen integrálhatja ezt a funkciót Java-alkalmazásaiba.
## GYIK
### Használhatom az Aspose.Tasks for Java-t a projektadatok programozott kezelésére?
Igen, az Aspose.Tasks for Java kiterjedt funkciókat kínál a projektadatok kezeléséhez, beleértve a projektfájlok olvasását, írását és módosítását.
### Létezik ingyenes próbaverzió az Aspose.Tasks for Java számára?
 Igen, letöltheti az Aspose.Tasks for Java ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Tasks for Java dokumentációját?
Megtalálhatja az Aspose.Tasks for Java dokumentációját[itt](https://reference.aspose.com/tasks/java/).
### Hogyan kaphatok támogatást az Aspose.Tasks for Java-hoz kapcsolódó problémákhoz vagy lekérdezésekhez?
 Támogatást kaphat az Aspose.Tasks fórumon[itt](https://forum.aspose.com/c/tasks/15).
### Vásárolhatok ideiglenes licencet az Aspose.Tasks for Java számára?
 Igen, vásárolhat ideiglenes licencet innen[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

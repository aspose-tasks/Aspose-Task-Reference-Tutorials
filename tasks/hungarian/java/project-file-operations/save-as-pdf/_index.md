---
title: Mentés PDF-ként az Aspose.Tasks alkalmazásban
linktitle: Mentés PDF-ként az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan konvertálhat projektfájlokat PDF-be az Aspose.Tasks for Java segítségével. Egyszerű lépések a hatékony átalakításhoz.
weight: 17
url: /hu/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mentés PDF-ként az Aspose.Tasks alkalmazásban

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a projektek PDF formátumban történő mentésének folyamatán az Aspose.Tasks for Java használatával. Az Aspose.Tasks segítségével hatékonyan konvertálhatja projektfájljait PDF formátumba, így biztosítva a kompatibilitást és az egyszerű megosztást. Merüljünk el a lépésekben:
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse az Aspose.Tasks könyvtárat. A letöltési linket megtalálod[itt](https://releases.aspose.com/tasks/java/).
3. Projektfájl: Készítsen egy projektfájlt (pl. HomeMovePlan.mpp), amelyet PDF-be szeretne konvertálni.

## Csomagok importálása
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## 1. lépés: Olvassa el a bemeneti projektfájlt
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Ügyeljen arra, hogy cserélje ki`"Your Data Directory"` a projektfájlt tartalmazó adatkönyvtár elérési útjával.
## 2. lépés: Mentse el a projektet PDF formátumban
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Ez a kódrészlet PDF-fájlként menti a projektet "Project5.pdf" néven.
## 3. lépés: A tartalom illesztése a cellamérethez
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Itt beállítjuk a PDF mentési beállításait, beleértve a tartalom illesztését, az időskálát és a prezentációs formátumot.
## 4. lépés: A legendák elrejtése
```java
o.setLegendOnEachPage(false);
```
Ez a lépés elrejti a jelmagyarázatokat a PDF minden oldalán.
## 5. lépés: Mentse el a projektet az alkalmazott opciókkal
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Végül ez a kód PDF-fájlba menti a projektet az alkalmazott beállításokkal.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használhatja az Aspose.Tasks for Java használatát projektek PDF formátumban történő mentésére. Ezeket az egyszerű lépéseket követve hatékonyan konvertálhatja projektfájljait az egyszerű megosztás és terjesztés érdekében.
## GYIK
### K: Az Aspose.Tasks kompatibilis a Java összes verziójával?
V: Igen, az Aspose.Tasks támogatja a Java verziókat a JDK 6-tól kezdve.
### K: Testreszabhatom a PDF kimenet megjelenését?
V: Abszolút! Az Aspose.Tasks különféle lehetőségeket kínál a PDF-kimenet testreszabásához az Ön igényei szerint.
### K: Az Aspose.Tasks támogat más fájlformátumokat a konvertáláshoz?
V: Igen, az Aspose.Tasks a fájlformátumok széles skáláját támogatja, beleértve az MPP-t, XML-t, XLSX-et és még sok mást.
### K: Elérhető az Aspose.Tasks próbaverziója?
 V: Igen, ingyenes próbaverziót kaphat az Aspose.Tasks-tól[itt](https://releases.aspose.com/).
### K: Hol kaphatok támogatást az Aspose.Tasks-hoz?
 V: Támogatásért és segítségért látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Konvertálja az MS Projectet SVG-re Java nyelven
linktitle: Mentés SVG-ként az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan mentheti a Microsoft Project fájlokat SVG formátumban Java nyelven az Aspose.Tasks könyvtár használatával. Lépésről lépésre útmutató kódpéldákkal.
type: docs
weight: 18
url: /hu/java/project-file-operations/save-as-svg/
---
## Bevezetés
Az Aspose.Tasks for Java egy hatékony könyvtár a projektmenedzsment fájlokkal való munkavégzéshez, lehetővé téve a fejlesztők számára a projektadatok kezelését, különféle műveletek végrehajtását és hatékony jelentéskészítést. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet projektet menteni SVG-ként az Aspose.Tasks for Java használatával. Az SVG (Scalable Vector Graphics) egy széles körben használt formátum a vektorgrafikák webes megjelenítésére, amely méretezhetőséget és kiváló minőségű megjelenítést biztosít.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
### Java fejlesztői környezet
Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszeren. A JDK letölthető és telepíthető az Oracle webhelyéről.
### Aspose.Tasks for Java Library
 Töltse le és telepítse az Aspose.Tasks for Java könyvtárat a webhelyről. A letöltési linket a mellékelt dokumentációban találja[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először is importálnia kell a szükséges csomagokat a Java programba az Aspose.Tasks funkciókkal való együttműködéshez.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Most bontsuk fel a megadott példát több lépésre:
## 2. lépés: Adja meg az adatkönyvtárat
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"`annak a könyvtárnak az elérési útjával, ahol a projektfájlja található.
## 3. lépés: Töltse be a projektfájlt
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Ez a lépés betölti a "HomeMovePlan.mpp" nevű projektfájlt a megadott adatkönyvtárból.
## 4. lépés: Mentés SVG-ként
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Ez a lépés a betöltött projektet SVG formátumban menti "project5.svg" néven a megadott adatkönyvtárba.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet projektet menteni SVG-ként az Aspose.Tasks for Java segítségével. A megadott lépések követésével hatékonyan konvertálhatja a projektfájlokat SVG formátumba, lehetővé téve a zökkenőmentes integrációt a webalapú alkalmazásokkal vagy vizualizációs eszközökkel.
## GYIK
### Az Aspose.Tasks for Java kompatibilis a Microsoft Project fájlok összes verziójával?
Igen, az Aspose.Tasks for Java támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### Testreszabhatom az SVG kimenet megjelenését?
Igen, testreszabhatja az SVG-kimenet megjelenését olyan paraméterek beállításával, mint a betűtípusok, színek és elrendezési konfigurációk.
### Az Aspose.Tasks for Java használatához licenc szükséges a kereskedelmi használatra?
 Igen, az Aspose.Tasks for Java kereskedelmi használatához érvényes licenc szükséges. Az engedélyt a webhelyről szerezheti be[itt](https://purchase.aspose.com/temporary-license/).
### Kipróbálhatom az Aspose.Tasks for Java programot vásárlás előtt?
 Igen, kérheti az Aspose.Tasks for Java ingyenes próbaverzióját a webhelyről[itt](https://purchase.aspose.com/buy) hogy értékelje jellemzőit és képességeit.
### Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?
 Az Aspose.Tasks for Java-hoz támogatást kaphat, ha ellátogat a fórumba[itt](https://forum.aspose.com/c/tasks/15), ahol kérdéseket tehet fel, és kapcsolatba léphet a közösséggel.
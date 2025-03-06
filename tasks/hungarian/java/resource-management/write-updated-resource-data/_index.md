---
title: Írjon frissített erőforrásadatokat az Aspose.Tasks-ba
linktitle: Írjon frissített erőforrásadatokat az Aspose.Tasks-ba
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan frissítheti könnyedén az MS Project fájljaiban lévő erőforrásadatokat az Aspose.Tasks for Java segítségével.
type: docs
weight: 21
url: /hu/java/resource-management/write-updated-resource-data/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük a Microsoft Project erőforrásadatainak frissítésén az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy hatékony Java API, amely lehetővé teszi a Microsoft Project fájlok kezelését anélkül, hogy a Microsoft Projectet telepítenie kellene a rendszerére.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Tasks a Java könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
3. Java programozási alapismeretek.

## Csomagok importálása

Először is importálnia kell a szükséges csomagokat, hogy működjön az Aspose.Tasks programban a Java-kódban. Adja hozzá a következő importálási utasításokat a Java fájlhoz:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 1. lépés: Állítsa be az adattárat

Határozza meg azt a könyvtárat, ahol az adatfájlok találhatók:

```java
String dataDir = "Your Data Directory";
```

## 2. lépés: Adja meg a bemeneti és kimeneti fájlokat

Határozza meg a bemeneti MS Project fájl és az eredményül kapott frissített fájl elérési útját:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Tesztfájl egy frissítendő rsc-vel
String resultFile = dataDir + "OutputMPP.mpp"; // Fájl tesztprojekt írásához
```

## 3. lépés: Töltse be a projektet

 Töltse be az MS Project fájlt a`Project` tárgy:

```java
Project project = new Project(file);
```

## 4. lépés: Adjon hozzá egy erőforrást és állítsa be az attribútumokat

Adjon hozzá egy új erőforrást a projekthez, és állítsa be az attribútumait, például a normál díjszabást, a túlórák díját és a csoportot:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 5. lépés: Mentse el a projektet

Mentse el a frissített projektet a módosított erőforrásadatokkal:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan lehet frissíteni az MS Project erőforrásadatait az Aspose.Tasks for Java használatával. Az alábbi lépések követésével hatékonyan kezelheti programozottan az MS Project fájljaiban lévő erőforrás-információkat.

## GYIK

### 1. kérdés: Frissíthetek több erőforrást ugyanabban a projektben az Aspose.Tasks for Java használatával?

1. válasz: Igen, frissíthet több erőforrást is, ha végighalad rajtuk, és ennek megfelelően állítja be az attribútumaikat.

### 2. kérdés: Az Aspose.Tasks támogat más fájlformátumokat is az MS Projecten kívül?

2. válasz: Igen, az Aspose.Tasks különféle fájlformátumokat támogat, beleértve az XML-t, MPP-t és egyebeket.

### 3. kérdés: Az Aspose.Tasks kompatibilis a Java különböző verzióival?

3. válasz: Az Aspose.Tasks kompatibilis a Java 6-os és újabb verzióival.

### 4. kérdés: Végezhetek más műveleteket az MS Project fájlokon az Aspose.Tasks segítségével?

4. válasz: Igen, számos műveletet végrehajthat, például olvasást, írást, valamint feladatok, erőforrások és naptárak kezelését.

### 5. kérdés: Hol találhatok további segítséget vagy támogatást az Aspose.Tasks-hoz?

 A5: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) bármilyen segítségért vagy kérdésért.

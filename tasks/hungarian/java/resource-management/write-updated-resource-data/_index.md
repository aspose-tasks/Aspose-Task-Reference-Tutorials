---
date: 2026-01-15
description: Ismerje meg, hogyan adhat hozzá erőforrást a projekthez, frissítheti
  az erőforrás adatait, és mentheti a projektet MPP formátumban az Aspose.Tasks for
  Java segítségével.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Erőforrás hozzáadása a projekthez az Aspose.Tasks for Java használatával
url: /hu/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erőforrás hozzáadása projekthez az Aspose.Tasks for Java használatával

## Bevezetés
Ebben a gyakorlati útmutatóban megtanulja, **hogyan adjon hozzá erőforrást projekthez** programozottan az Aspose.Tasks Java API-val. Lépésről lépésre végigvezetjük egy meglévő MS Project XML fájl betöltésén, egy új erőforrás beszúrásán, annak tulajdonságainak frissítésén, majd végül **a projekt MPP‑ként történő mentésén**. A végére egy tiszta, újrahasználható mintát kap, amelyet bármely Java‑alapú jelentéskészítő vagy automatizálási eszközbe beilleszthet.

## Gyors válaszok
- **Mit jelent a „erőforrás hozzáadása projekthez”?** Új erőforrás bejegyzést (személy, berendezés, anyag) hoz létre egy Microsoft Project fájlban.  
- **Melyik könyvtár kezeli ezt?** Aspose.Tasks for Java – nincs szükség a Microsoft Project telepítésére.  
- **Szükségem van licencre?** Fejlesztéshez ingyenes próba verzió használható; termeléshez kereskedelmi licenc szükséges.  
- **Átkonvertálhatom az XML‑t MPP‑vé?** Igen – töltse be az XML fájlt, és **mentse a projektet MPP‑ként** a `project.save(...)` metódussal.  
- **Milyen Java verzió szükséges?** Java 6 vagy újabb (Java 8+ ajánlott).

## Mi az a „erőforrás hozzáadása projekthez”?
Erőforrás hozzáadása projekthez azt jelenti, hogy egy új sort szúrunk be a Resources (Erőforrások) táblába egy MS Project fájlban. Ez a sor tárolja például a nevet, költségárakat, csoportot és egyedi mezőket, amelyeket a feladatok később hivatkozhatnak.

## Miért használjuk az Aspose.Tasks for Java‑t?
- **Nincs Microsoft Project függőség** – bármely operációs rendszeren vagy CI szerveren működik.  
- **Teljes pontosság** – megőrzi a natív Project funkciókat a formátumok közti konverzió során.  
- **Gazdag API** – lehetővé teszi feladatok, erőforrások, naptárak és egyéb elemek olvasását, írását és manipulálását.

## Előkövetelmények
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. Java Development Kit (JDK) 8 vagy újabb telepítve.  
2. Aspose.Tasks for Java könyvtárral – töltse le [innen](https://releases.aspose.com/tasks/java/).  
3. Alapvető ismeretekkel a Java szintaxisról és a Maven/Gradle projektbeállításról.

## Csomagok importálása
Adja hozzá a szükséges Aspose.Tasks osztályokat a Java forrásfájljához:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 1. lépés: Adatkatalógus beállítása
Határozza meg, hol lesznek a forrás XML és a keletkezett MPP fájlok:

```java
String dataDir = "Your Data Directory";
```

## 2. lépés: Bemeneti és kimeneti fájlok megadása
Adja meg azt az XML fájlt, amelyet **XML‑ról MPP‑re konvertál** szeretne, valamint a cél MPP fájlt, amely tartalmazni fogja az új erőforrást:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## 3. lépés: Projekt betöltése
Hozzon létre egy `Project` objektumot az XML forrásból:

```java
Project project = new Project(file);
```

## 4. lépés: Erőforrás hozzáadása és attribútumok beállítása
Itt **hozzáadjuk az erőforrást a projekthez** és konfiguráljuk a díjszabásait és csoportját:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro tipp:* A `add` hívást egy ciklusban is megismételheti, hogy **több erőforrást frissítsen** egyetlen futtatás során.

## 5. lépés: Projekt mentése
Végül **mentse a projektet MPP‑ként**, hogy a módosítások el legyenek mentve:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Összegzés
Most már tudja, **hogyan adjon hozzá erőforrást projekthez**, frissítse annak tulajdonságait, és **mentse a projektet MPP‑ként** az Aspose.Tasks for Java segítségével. Ez a megközelítés ideális automatizált jelentéskészítő csővezetékekhez, tömeges erőforrásimportáláshoz, vagy bármilyen szituációhoz, ahol MS Project fájlokat kell manipulálni a desktop alkalmazás nélkül.

## Gyakran Ismételt Kérdések

**Q1: Frissíthetek több erőforrást egy projekten belül az Aspose.Tasks for Java használatával?**  
A: Igen, iterálhat a `project.getResources()` gyűjteményen, vagy többször meghívhatja az `add` metódust, minden erőforrás mezőit a szükség szerint beállítva.

**Q2: Az Aspose.Tasks támogat más fájlformátumokat is a MS Project mellett?**  
A: Természetesen – XML, MPP, MPX, Primavera és még sok más formátum támogatott.

**Q3: Az Aspose.Tasks kompatibilis a különböző Java verziókkal?**  
A: A könyvtár Java 6‑tól felfelé működik; a legjobb teljesítmény érdekében a Java 8+ erősen ajánlott.

**Q4: Végezhetek más műveleteket is MS Project fájlokon az Aspose.Tasks segítségével?**  
A: Igen, olvashat és írhat feladatokat, naptárakat, hozzárendeléseket, egyedi mezőket, sőt jelentéseket is generálhat.

**Q5: Hol találok további segítséget vagy támogatást az Aspose.Tasks-hez?**  
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi segítségért és a hivatalos támogatásért.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
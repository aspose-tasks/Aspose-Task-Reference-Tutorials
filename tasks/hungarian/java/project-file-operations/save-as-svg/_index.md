---
date: 2026-03-27
description: Tanulja meg, hogyan exportálhatja az MPP-t SVG-be Java-ban az Aspose.Tasks
  segítségével. Lépésről‑lépésre útmutató, kódrészletek és tippek a projekt gyors
  SVG‑ként való mentéséhez.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan exportáljuk az MPP-t SVG-be Java-ban az Aspose.Tasks használatával
url: /hu/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan exportáljuk az MPP-t SVG-be Java-ban

## Export MPP to SVG – Bevezetés
Ebben az útmutatóban megtanulja, hogyan **exportálja az MPP-t SVG** fájlokba az Aspose.Tasks for Java használatával. A Microsoft Project (MPP) fájl Scalable Vector Graphics (SVG) képpé konvertálása lehetővé teszi, hogy nagy‑minőségű, felbontás‑független diagramokat ágyazzon be közvetlenül weboldalakba, jelentésekbe vagy műszerfalakba. Végigvezetjük a szükséges beállításokon, megmutatjuk a pontos kódot, amelyre szüksége van, és lépésről‑lépésre elmagyarázzuk, hogy magabiztosan **mentse a projektet SVG‑ként** saját alkalmazásaiban.

## Gyors válaszok
- **Mi a “export MPP to SVG” jelentése?**  
  Átalakítja a Microsoft Project fájlt (.mpp) egy SVG képpé, amely bármely böngészőben minőségvesztés nélkül megjeleníthető.  
- **Melyik könyvtár végzi a konverziót?**  
  Az Aspose.Tasks for Java egyetlen soros `save` metódust biztosít a konverzióhoz.  
- **Szükségem van licencre?**  
  Ideiglenes licenc szükséges kereskedelmi felhasználáshoz; ingyenes próba elérhető.  
- **Mik a előfeltételek?**  
  Java JDK 8+ és az Aspose.Tasks for Java JAR.  
- **Mennyi időt vesz igénybe a konverzió?**  
  Általában kevesebb, mint egy másodperc a szokásos projektfájlok esetén.

## Mi az “export MPP to SVG”?
Az MPP‑t SVG‑be exportálni azt jelenti, hogy a projekt ütemezésének vizuális ábrázolását – feladatok, idővonalak és erőforrások – SVG fájlként írjuk ki. Az SVG XML‑alapú, könnyű, és tökéletesen skálázható nagy felbontású kijelzőkön.

## Miért exportáljuk az MPP-t SVG-be az Aspose.Tasks‑szel?
- **Microsoft Project telepítése nem szükséges** – a könyvtár önállóan működik.  
- **Teljes hűség** – diagramok, Gantt‑sávok és mérföldkövek megtartják stílusukat.  
- **Kereszt‑platform** – a kód futtatható Windows, Linux vagy macOS rendszeren.  
- **Egy soros API** – egyetlen hívással menti a projektet SVG‑ként, természetesen illeszkedik a meglévő Java folyamatokba.

## Előfeltételek
- **Java Development Kit (JDK)** – 8-as vagy újabb verzió. Töltse le az Oracle weboldaláról.  
- **Aspose.Tasks for Java** – szerezze be a könyvtárat a hivatalos letöltőoldalon **[here](https://releases.aspose.com/tasks/java/)**.  

## Csomagok importálása
Először importálja a szükséges osztályokat. Az import blokk változatlan marad.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 1. lépés: Adatkönyvtár meghatározása
Adja meg, hol található a forrás MPP fájl, és hová kerül az SVG írásra.

```java
String dataDir = "Your Data Directory";
```

> **Pro tipp:** Használjon abszolút elérési utat vagy a projekt erőforrásmappájához relatív utat a `FileNotFoundException` elkerülése érdekében.

## 2. lépés: MPP fájl betöltése
Hozzon létre egy `Project` példányt a meglévő Microsoft Project fájl betöltésével.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Ez a sor a korábban meghatározott mappából olvassa be a *HomeMovePlan.mpp* fájlt.

## 3. lépés: Projekt mentése SVG‑ként
Most már egyetlen paranccsal **exportálhatja az MPP‑t SVG‑be**.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

A metódus a `project5.svg` fájlt ugyanabba a könyvtárba írja. A kapott SVG megnyitható bármely modern böngészőben, vagy közvetlenül beágyazható HTML‑be.

## Gyakori felhasználási esetek
- **Projekt műszerfalak** – élő Gantt diagramok beágyazása webportálokba anélkül, hogy a kliensnek telepítenie kellene a Microsoft Projectet.  
- **Automatizált jelentéskészítés** – SVG képek generálása futás közben PDF vagy HTML jelentésekhez.  
- **Kereszt‑csapat együttműködés** – vizuális ütemezés megosztása az érintettekkel, akiknek csak egy böngészőre van szükségük a megtekintéshez.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **File not found** | Incorrect `dataDir` path | Verify the directory string ends with a separator (`/` or `\\`). |
| **Blank SVG output** | Project loaded without views | Ensure the MPP file contains a Gantt chart view before saving. |
| **License exception** | No valid license applied | Apply a temporary license using `License.setLicense("path/to/license.xml")` before calling `save`. |

## Gyakran feltett kérdések

**Q: Az Aspose.Tasks for Java kompatibilis-e minden Microsoft Project fájlverzióval?**  
A: Igen, támogatja az MPP, MPT és XML formátumokat a régebbi verzióktól a legújabb Project kiadásokig.

**Q: Testreszabhatom-e az SVG kimenet megjelenését?**  
A: Teljes mértékben. Használja a `SvgOptions`‑t a betűtípusok, színek és elrendezési beállítások megadásához a `save` hívása előtt.

**Q: Az Aspose.Tasks for Java licencet igényel kereskedelmi felhasználáshoz?**  
A: Igen, érvényes licenc szükséges a termeléshez. Ideiglenes licencet szerezhet **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Kipróbálhatom-e az Aspose.Tasks for Java‑t vásárlás előtt?**  
A: Igen, ingyenes próba elérhető **[here](https://purchase.aspose.com/buy)**.

**Q: Hol kaphatok támogatást az Aspose.Tasks for Java‑hoz?**  
A: Látogassa meg a közösségi fórumot **[here](https://forum.aspose.com/c/tasks/15)**, hogy kérdéseket tegyen fel és visszajelzést osszon meg.

## Összegzés
Most már tudja, hogyan **exportálja az MPP‑t SVG‑be** Java‑ban, és hatékonyan **mentse a projektet SVG‑ként** az Aspose.Tasks segítségével. Ez a képesség lehetővé teszi, hogy gazdag projekt‑vizualizációkat integráljon webportálokba, jelentés‑műszerfalakba vagy bármely olyan helyre, ahol skálázható grafikára van szükség. Kísérletezzen a `SvgOptions`‑szel a kimenet finomhangolásához, és egy erőteljes eszközt kap a fejlesztői eszköztárába.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-29
description: Ismerje meg, hogyan változtathatja meg a hónap napjainak számát, és kezelheti
  a többi hétköznap tulajdonságát az Aspose.Tasks for Java-ban. Testreszabhatja a
  hét kezdőnapjait, módosíthatja a projekt naptárát, és elmentheti a projektet XML
  formátumban.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: A hónap napjainak módosítása az Aspose.Tasks hétköznap tulajdonságokkal
url: /hu/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hónap napjainak módosítása az Aspose.Tasks hétköznap tulajdonságokkal

## Bevezetés
Az Aspose.Tasks for Java lehetővé teszi, hogy **módosítsa a hónap napjait** és finomhangolja a többi hétköznap beállítást anélkül, hogy a Microsoft Project telepítve lenne. Akár egy projekt naptárat egy nem szabványos pénzügyi hónaphoz igazítja, akár csak a hét kezdőnapját kell módosítania, ez az útmutató végigvezeti a leggyakoribb forgatókönyveken – a jelenlegi hét kezdőnap lekérdezése, a hét kezdőnap testreszabása, a projekt naptár módosítása, és a projekt XML formátumban való mentése.

## Gyors válaszok
- **Megváltoztathatom a hónap napjainak számát?** Igen, használja a `Prj.DAYS_PER_MONTH` tulajdonságot a `Project` objektumon.  
- **Hogyan testreszabhatom a hét kezdőnapját?** Állítsa be a `Prj.WEEK_START_DAY` értékét egy `DayType` értékre (pl. `DayType.Monday`).  
- **Milyen formátumban exportálhatom a projektet?** A példa XML formátumban menti a fájlt a `SaveFileFormat.Xml` használatával.  
- **Szükséges licenc a termelési használathoz?** Egy érvényes Aspose.Tasks licenc szükséges a nem értékelő telepítésekhez.  
- **Mely IDE-k támogatottak?** Bármely Java IDE, például IntelliJ IDEA, Eclipse vagy NetBeans működik.

## Mi az a „hónap napjainak módosítása” az Aspose.Tasks-ben?
A hónap napjainak módosítása azt jelenti, hogy frissíti egy `Project` példány `Prj.DAYS_PER_MONTH` tulajdonságát. Ez a tulajdonság azt mondja a motornak, hány munkanapot vegyen figyelembe minden hónapban, ami közvetlenül befolyásolja a feladat ütemezését és a költségszámításokat.

## Miért módosítsuk a projekt naptár tulajdonságait?
A projekt naptár testreszabása – például másik hét kezdőnap beállítása vagy a nap perces értékének módosítása – segít:

- Az ütemezések összehangolásában a regionális munkahéthez.  
- Nem szabványos munkaminták modellezésében (pl. 4 napos hetek).  
- Pontos jelentéskészítés biztosításában olyan szerződések esetén, amelyek egyedi naptárakat használnak.

## Előfeltételek
- **Java Development Kit (JDK)** – Telepítse a legújabb JDK-t az Oracle-tól.  
- **Aspose.Tasks for Java könyvtár** – Töltse le a hivatalos oldalról [itt](https://releases.aspose.com/tasks/java/).  
- **Az Ön által választott IDE** – IntelliJ IDEA, Eclipse vagy NetBeans.

## Csomagok importálása
Először importálja a szükséges Aspose.Tasks osztályokat:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 1. lépés: Projektfájl betöltése
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Ez betölti a megadott mappából a meglévő Microsoft Project fájlt (`project.mpp`).

## 2. lépés: Hétköznap tulajdonságok megjelenítése
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Itt lekérdezzük és kiírjuk a jelenlegi hétköznap beállításokat, beleértve a **hét kezdőnapját** és a **hónap napjait**.

## 3. lépés: Hétköznap tulajdonságok beállítása
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Ebben a lépésben **a hónap napjait** 24-re állítjuk, a hét kezdőnapját hétfőre állítjuk, és a nap/heti perceket módosítjuk. Ez bemutatja, hogyan **módosítható a projekt naptár** értékei programozott módon.

## 4. lépés: Projekt mentése
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
A módosított projekt a **projekt mentése XML formátumban** segítségével kerül tárolásra, ami hasznos más eszközökkel való integrációhoz vagy verziókezeléshez.

## 5. lépés: Eredmény megjelenítése
```java
System.out.println("Process completed Successfully");
```
Egy egyszerű megerősítés, hogy a műveletek hibamentesen befejeződtek.

## Hogyan testreszabjuk a hét kezdőnapját
Ha a szervezet vasárnap‑első naptárat használ, cserélje a `DayType.Monday` értéket `DayType.Sunday`-ra. Ugyanazt a tulajdonságot (`Prj.WEEK_START_DAY`) használja, így a módosítás egyszerű.

## Hogyan lekérjük a hét kezdőnapját
Bármikor meghívhatja a `project.get(Prj.WEEK_START_DAY)` metódust, hogy **lekérje a hét kezdőnapjának** információját, ahogy a 2. lépésben látható.

## Hogyan módosítsuk a projekt naptárát
A hét kezdőnapja mellett a `Prj.MINUTES_PER_DAY` és `Prj.MINUTES_PER_WEEK` értékeket is módosíthatja, hogy egyedi munkaidőket vagy műszakmintákat tükrözzenek.

## Gyakori problémák és megoldások
- **Helytelen nap típus érték** – Győződjön meg róla, hogy a `DayType` enumot használja (pl. `DayType.Monday`).  
- **Fájlútvonal hibák** – Ellenőrizze, hogy a `dataDir` a megfelelő fájlelválasztóval (`/` vagy `\`) végződik.  
- **Licenc nincs beállítva** – Ha licencfigyelmeztetést lát, regisztrálja az Aspose.Tasks licencet a `Project` objektum létrehozása előtt.

## Gyakran ismételt kérdések

**K: Kezelheti az Aspose.Tasks for Java a komplex projekt struktúrákat?**  
V: Igen, az Aspose.Tasks for Java átfogó támogatást nyújt a komplex projekt struktúrák könnyű kezeléséhez.

**K: Kompatibilis-e az Aspose.Tasks for Java a Microsoft Project fájlok különböző verzióival?**  
V: Teljes mértékben, az Aspose.Tasks for Java különböző Microsoft Project fájl verziókat támogat, biztosítva a kompatibilitást a platformok között.

**K: Integrálhatom az Aspose.Tasks for Java-t a meglévő Java alkalmazásaimba?**  
V: Igen, az Aspose.Tasks for Java zökkenőmentes integrációs lehetőséget kínál, lehetővé téve, hogy erőteljes projektmenedzsment funkciókkal bővítse Java alkalmazásait.

**K: Biztosít-e az Aspose.Tasks for Java dokumentációt és támogatást?**  
V: Igen, részletes dokumentációt és közösségi támogatást érhet el az Aspose.Tasks for Java-hez a [weboldalon](https://releases.aspose.com/).

**K: Van ingyenes próba verzió az Aspose.Tasks for Java-hoz?**  
V: Igen, letöltheti az Aspose.Tasks for Java ingyenes próba verzióját a [weboldalról](https://reference.aspose.com/tasks/java/), hogy megismerje a funkciókat vásárlás előtt.

---

**Utolsó frissítés:** 2026-03-29  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
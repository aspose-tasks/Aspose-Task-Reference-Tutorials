---
date: 2025-12-23
description: Tanulja meg, hogyan használja az Aspose.Tasks Java-t a projekt ütemezésének
  frissítéséhez, a hét kezdőnapjának beállításához, a hónap napjainak módosításához,
  és a projekt naptár hatékony testreszabásához.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Hétköznapok tulajdonságainak kezelése
url: /hu/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Hétköznapi tulajdonságok kezelése

## Bevezetés
Az Aspose.Tasks for Java (aspose tasks java) egy robusztus API, amely lehetővé teszi a Java fejlesztők számára, hogy a Microsoft Project fájlokkal dolgozzanak anélkül, hogy a Microsoft Project telepítve lenne. Ebben az útmutatóban megtanulja, hogyan **töltsön be egy MPP fájlt**, **állítsa be a hét kezdőnapját**, **változtassa meg a hónap napjainak számát**, és egyébként **testreszabja a projekt naptárát** – mindezek alapvető lépések a projekt ütemezésének frissítéséhez. A végére képes lesz programozottan módosítani a hétköznapi tulajdonságokat, és a változtatásokat a szükséges formátumban menteni.

## Gyors válaszok
- **Mi a fő osztály a projektek kezeléséhez?** `Project` az Aspose.Tasks könyvtárból.  
- **Hogyan változtathatom meg a hét kezdőnapját?** Használja a `project.set(Prj.WEEK_START_DAY, DayType.Monday)` metódust.  
- **Betölthetek egy meglévő .mpp fájlt?** Igen – hozza létre a `Project` példányt a fájl útvonalával.  
- **Melyik metódus menti a projektet XML-ként?** `project.save(path, SaveFileFormat.Xml)`.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba verzió elegendő értékeléshez; a termeléshez licenc szükséges.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következők rendelkezésre állnak:

- **Java Development Kit (JDK)** – a legújabb verzió telepítve.  
- **Aspose.Tasks for Java könyvtár** – töltse le [itt](https://releases.aspose.com/tasks/java/).  
- **IDE** például IntelliJ IDEA, Eclipse vagy NetBeans.  

## Csomagok importálása
A kezdéshez importálja a szükséges Aspose.Tasks osztályokat:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Most lépjünk végig a hétköznapi tulajdonságok kezelésének minden lépésén.

## 1. lépés: MPP fájl betöltése
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Itt **betöltünk egy meglévő .mpp fájlt** (`load mpp file`), hogy megvizsgálhassuk és módosíthassuk a naptárbeállításait.*

## 2. lépés: Aktuális hétköznapi tulajdonságok megjelenítése
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Ez a kód kiírja a jelenlegi **hét kezdőnapját**, **hónap napjainak számát**, **percet naponta**, és **percet hétenként** – a fő elemeket, amelyeket gyakran szükséges **testreszabni a projekt naptárát**.

## 3. lépés: Új hétköznapi tulajdonságok beállítása
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Ebben a lépésben **beállítjuk a hét kezdőnapját** hétfőre, **megváltoztatjuk a hónap napjainak számát** 24-re, és módosítjuk a napi és heti percértékeket. Ezek a beállítások tipikusak, ha **frissíteni kell a projekt ütemezését** egy nem szabványos munkanaptárhoz igazodva.

## 4. lépés: A módosított projekt mentése
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
A módosított projekt XML fájlként kerül mentésre, ami egyszerűvé teszi a megosztást vagy más eszközökbe való importálást.

## 5. lépés: A művelet megerősítése
```java
System.out.println("Process completed Successfully");
```
Egy egyszerű konzolüzenet jelzi, hogy a munkafolyamat hibamentesen befejeződött.

## Gyakori problémák és tippek
- **Helytelen fájl útvonal** – Ellenőrizze, hogy a `dataDir` perjellel végződik-e, vagy használja a `Paths.get(...)`-t a platform‑független útvonalakhoz.  
- **Licenc nincs beállítva** – Egy termelési környezetben hívja meg a `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kódot a `Project` létrehozása előtt.  
- **Váratlan hét kezdőnap** – Győződjön meg róla, hogy a megfelelő `DayType` enum értéket használja (pl. `DayType.Sunday`).  

## Gyakran ismételt kérdések

**Q: Kezelni tudja az Aspose.Tasks for Java a komplex projekt struktúrákat?**  
A: Igen, az Aspose.Tasks for Java átfogó támogatást nyújt a komplex projekt struktúrák könnyű kezeléséhez.

**Q: Kompatibilis-e az Aspose.Tasks for Java a Microsoft Project fájlok különböző verzióival?**  
A: Teljes mértékben, az Aspose.Tasks for Java támogatja a Microsoft Project fájlok különböző verzióit, biztosítva a kompatibilitást a platformok között.

**Q: Integrálhatom az Aspose.Tasks for Java-t a meglévő Java alkalmazásaimba?**  
A: Igen, az Aspose.Tasks for Java zökkenőmentes integrációs lehetőségeket kínál, lehetővé téve, hogy erőteljes projektmenedzsment funkciókkal bővítse Java alkalmazásait.

**Q: Kínál az Aspose.Tasks for Java dokumentációt és támogatást?**  
A: Igen, részletes dokumentációhoz és közösségi támogatáshoz férhet hozzá az Aspose.Tasks for Java-hoz a [weboldalukon](https://releases.aspose.com/).

**Q: Elérhető ingyenes próba verzió az Aspose.Tasks for Java-hoz?**  
A: Igen, letöltheti az Aspose.Tasks for Java ingyenes próba verzióját a [weboldalukról](https://reference.aspose.com/tasks/java/), hogy megismerje a funkciókat vásárlás előtt.

---

**Legutóbb frissítve:** 2025-12-23  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
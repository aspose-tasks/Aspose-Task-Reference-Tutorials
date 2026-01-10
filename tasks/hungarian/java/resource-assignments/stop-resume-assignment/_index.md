---
date: 2026-01-10
description: Tanulja meg, hogyan állíthatja le a feladatkiosztást, kezelheti az erőforrás‑kiosztásokat,
  és megtekintheti az erőforrás‑kiosztási példát az Aspose.Tasks for Java‑ban ezzel
  a lépésről‑lépésre útmutatóval.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan állítsuk le a hozzárendelést és folytassuk az erőforrás‑hozzárendeléseket
  az Aspose.Tasks‑ben
url: /hu/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk le a hozzárendelést és folytassuk a erőforrás‑hozzárendeléseket az Aspose.Tasks-ben

## Bevezetés
Ebben az útmutatóban **meg fogod tanulni, hogyan állítsd le a hozzárendelést** és később folytasd azt az Aspose.Tasks for Java segítségével. Az Aspose.Tasks egy erőteljes Java API, amely lehetővé teszi projektfájlok Java formátumban történő olvasását, a Microsoft Project adatok manipulálását, valamint az erőforrás‑hozzárendelések kezelését anélkül, hogy a Microsoft Project telepítve lenne. Lépésről lépésre végigvezetünk, elmagyarázzuk, miért fontos minden sor, és gyakorlati tippeket adunk, amelyeket valós projektekben alkalmazhatsz.

## Gyors válaszok
- **Mit jelent a „stop assignment” (hozzárendelés leállítása)?** Egy erőforrás‑hozzárendelést ideiglenesen inaktívként jelöl egy adott leállási dátumtól.  
- **Később újraindíthatom ugyanazt a hozzárendelést?** Igen, a ugyanazon hozzárendeléshez egy folytatási dátum beállításával.  
- **Szükségem van a Microsoft Project-re az API használatához?** Nem, az Aspose.Tasks függetlenül működik a Microsoft Projecttől.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb ajánlott.  
- **Hol tölthetem le a könyvtárat?** Az hivatalos Aspose.Tasks Java letöltőoldalról.

## Mi a „hozzárendelés leállítása” az Aspose.Tasks kontextusában?
A hozzárendelés leállítása azt mondja a tervezőnek, hogy hagyja figyelmen kívül a forrásnak a **leállási dátum** utáni munkát a **folytatási dátum** (ha van) előtt. Ez hasznos szabadságok, berendezés leállás, vagy bármely olyan időszak kezelésekor, amikor egy erőforrásnak nem kell aktívnak lennie.

## Miért használjuk az Aspose.Tasks-et az erőforrás‑hozzárendelések kezelésére?
- **Nincs szükség a Microsoft Project-re** – közvetlenül .mpp fájlokkal dolgozhatsz.  
- **Teljes dátumkontroll** – programozottan ellenőrizheted a leállási és folytatási dátumokat, és módosíthatod őket.  
- **Keresztplatformos** – bármely, Java‑t támogató operációs rendszeren futtatható.  
- **Gazdag API** – egy *resource assignment example* (erőforrás‑hozzárendelési példát) biztosít, amelyet testreszabott jelentésekhez bővíthetsz.

## Előkövetelmények
Mielőtt elkezdenénk, győződj meg róla, hogy rendelkezel:

- Java Development Kit (JDK) telepítve a rendszereden.  
- Aspose.Tasks for Java könyvtár letöltve. Letöltheted [itt](https://releases.aspose.com/tasks/java/).  
- Alapvető Java programozási ismeretek.

## Csomagok importálása
Először importáljuk a szükséges csomagokat a Java projektünkbe:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 1. lépés: Projektfájl betöltése
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Itt **beolvassuk a projektfájlt Java** formátumban (`.mpp`) és létrehozunk egy `Project` objektumot, amely hozzáférést biztosít az összes projektadathoz, beleértve az erőforrás‑hozzárendeléseket.

## 2. lépés: Erőforrás‑hozzárendelések bejárása
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Beállítunk egy **minimum dátumot**, hogy kiszűrjük a helykitöltő dátumokat, majd végigiterálunk minden hozzárendelésen. Ez a tipikus *resource assignment example* (erőforrás‑hozzárendelési példa) minta, amelyet akkor használunk, ha meg kell vizsgálnod vagy módosítanod kell a hozzárendeléseket.

## 3. lépés: Leállási és folytatási dátumok ellenőrzése
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

Ebben a blokkban **ellenőrizzük a leállási dátumot** és **a folytatási dátumot** minden hozzárendelésnél. Ha a dátum a `minDate` előtt van, úgy kezeljük, mintha nincs beállítva (`"NA"`); egyébként kiírjuk a tényleges dátumot. Ez a logika elengedhetetlen a **resource assignments (erőforrás‑hozzárendelések) megfelelő kezeléséhez**.

## Gyakori problémák és megoldások
- **Null dátumok** – a `ra.get(Asn.STOP)` `null` értéket adhat vissza. Védd le ezt egy null ellenőrzéssel, mielőtt a `.before(minDate)` metódust hívnád.  
- **Helytelen fájlútvonal** – Győződj meg róla, hogy a `dataDir` végén megfelelő útvonalelválasztó (`/` vagy `\\`) szerepel az operációs rendszerednek megfelelően.  
- **Verzióeltérés** – Használd az Aspose.Tasks for Java legújabb verzióját, hogy elkerüld a hiányzó enum értékeket.

## Gyakran ismételt kérdések
### Használhatom az Aspose.Tasks-et a Microsoft Project telepítése nélkül?
Igen, az Aspose.Tasks lehetővé teszi, hogy a Microsoft Project fájlokkal dolgozz anélkül, hogy a Microsoft Projectnek telepítve kellene lennie a rendszereden.

### Hol találok további dokumentációt?
Részletes dokumentációt [itt](https://reference.aspose.com/tasks/java/) találhatsz.

### Van elérhető ingyenes próba?
Igen, ingyenes próbaverziót [itt](https://releases.aspose.com/) kaphatsz.

### Hogyan kaphatok támogatást, ha problémáim merülnek fel?
Támogatást a közösségtől [itt](https://forum.aspose.com/c/tasks/15) kaphatsz.

### Vásárolhatok ideiglenes licencet?
Igen, ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) vásárolhatsz.

## Gyakran feltett kérdések

**K: Hogyan állíthatok programozottan leállási dátumot egy hozzárendeléshez?**  
V: Használd a `ra.set(Asn.STOP, yourDateObject);` kifejezést, ahol a `yourDateObject` egy `java.util.Date`.

**K: Mi történik, ha a folytatási dátum korábbi, mint a leállási dátum?**  
V: Az API nem kényszeríti a kronológiai sorrendet; azonban a tervező csak a két dátum közül a későbbit követően tekinti a hozzárendelést aktívnak, ezért saját magadnak kell ellenőrizned a dátumokat.

**K: Szűrhetem a hozzárendeléseket csak a leállási dátummal rendelkezőkre?**  
V: Igen, iterálj a `prj.getResourceAssignments()`-en, és ellenőrizd, hogy `ra.get(Asn.STOP) != null`.

**K: Lehet‑e eltávolítani a leállási dátumot, ha már be van állítva?**  
V: Állítsd a leállási dátumot `null`‑ra a `ra.set(Asn.STOP, null);` használatával, majd mentsd a projektet.

**K: Támogatja az Aspose.Tasks más dátum‑kapcsolódó mezőket is, mint a start, finish vagy actual start?**  
V: Teljes mértékben. Az `Asn` enum minden hozzárendelési mezőhöz biztosít konstansokat, például `Asn.START`, `Asn.FINISH` stb.

## Összegzés
Az itt bemutatott lépések követésével most már **tudod, hogyan állítsd le a hozzárendelést**, ellenőrizheted a leállási/folytatási dátumokat, és szükség esetén újraindíthatod a hozzárendelést. Ez a lehetőség lehetővé teszi, hogy **az erőforrás‑hozzárendeléseket** pontosabban kezeld, különösen olyan helyzetekben, mint erőforrás szabadság vagy berendezés leállás. Nyugodtan bővítsd a példát dátumok frissítésére, jelentések generálására vagy saját ütemezési logikád integrálására.

---

**Legutóbb frissítve:** 2026-01-10  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
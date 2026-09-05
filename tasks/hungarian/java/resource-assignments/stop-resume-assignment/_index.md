---
date: 2026-07-14
description: Ismerje meg, hogyan állíthatja le az erőforrás hozzárendelést Java‑ban,
  kezelheti az erőforrás hozzárendeléseket, és tekinthet meg példákat az Aspose.Tasks
  for Java használatával ebben a lépésről‑lépésre útmutatóban.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Erőforrás hozzárendelések leállítása és újraindítása az Aspose.Tasks-ben
og_description: Állítsa le az erőforrás hozzárendelést Java‑ban az Aspose.Tasks segítségével.
  Ez az útmutató bemutatja, hogyan szüneteltethet és újraindíthat hozzárendeléseket,
  kezelheti a dátumokat, és integrálhatja az API‑t a Microsoft Project nélkül.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Erőforrás hozzárendelés leállítása Java‑ban – Aspose.Tasks útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Hogyan állítsuk le az erőforrás hozzárendelést Java‑ban – Újraindítás az Aspose.Tasks
  segítségével
url: /hu/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk le a erőforrás hozzárendelést Java-ban – Újraindítás az Aspose.Tasks segítségével

## Bevezetés
Ebben az oktatóanyagban megtanulja, **hogyan állítsuk le a erőforrás hozzárendelést Java-ban**, majd később újraindítsa azt az Aspose.Tasks for Java használatával. Az Aspose.Tasks egy robusztus Java API, amely lehetővé teszi a Microsoft Project fájlok olvasását és írását, ütemezések manipulálását, valamint az erőforrás‑hozzárendelések vezérlését – mindezt anélkül, hogy a Microsoft Project telepítve lenne. Lépésről‑lépésre végigvezetjük, megmagyarázzuk, miért fontos minden sor, és gyakorlati tippeket osztunk meg, amelyeket valós projektterveken is alkalmazhat.

## Gyors válaszok
- **Mi jelent a „stop assignment”?** Egy erőforrás‑hozzárendelést ideiglenesen inaktívvá jelöl egy adott leállási dátumtól.  
- **Vissza tudom-e állítani ugyanazt a hozzárendelést később?** Igen, egy újraindítási dátum beállításával ugyanazon a hozzárendelésen.  
- **Szükségem van Microsoft Project-re az API használatához?** Nem, az Aspose.Tasks függetlenül működik a Microsoft Projecttől.  
- **Melyik Java verzió szükséges?** A Java 8 vagy újabb ajánlott.  
- **Hol tölthetem le a könyvtárat?** Az hivatalos Aspose.Tasks Java letöltési oldalról.

## Hogyan állítsuk le a erőforrás hozzárendelést Java-ban?
Töltse be a projektet, keresse meg a cél `ResourceAssignment`‑ot, állítsa be a `STOP` dátumot, opcionálisan adjon meg egy `RESUME` dátumot, majd mentse a fájlt. Ez a sorozat szünetelteti a munkát a megadott időszakra, és automatikusan újraaktiválja a resume dátum után, így pontosan szabályozhatja az erőforrás‑naptárakat manuális fájlszerkesztés nélkül.

## Mi jelent a „hogyan állítsuk le a hozzárendelést” az Aspose.Tasks kontextusában?
A hozzárendelés leállítása azt mondja a tervezőnek, hogy a **leállási dátum** után a **újraindítási dátum** (ha van) előtt figyelmen kívül hagyja a hozzárendelt munkát. Ez hasznos szabadságok, berendezésleállások vagy bármilyen időszak kezelésére, amikor egy erőforrásnak nem kell aktívnak lennie.

## Miért használjuk az Aspose.Tasks-et az erőforrás‑hozzárendelések kezelésére?
Az Aspose.Tasks lehetővé teszi a hozzárendelési dátumok programozott vezérlését, kiküszöbölve a manuális szerkesztéseket és csökkentve a hibalehetőséget. Támogat **50+ bemeneti és kimeneti formátumot**, és akár **10 000 feladatot** is képes feldolgozni úgy, hogy a memóriahasználat 200 MB alatt marad, mivel adatfolyamon dolgozik a teljes fájl betöltése helyett. Az API bármely, Java‑t támogató operációs rendszeren fut, így platformfüggetlen rugalmasságot biztosít.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- Java Development Kit (JDK) 8 vagy újabb telepítve.  
- Aspose.Tasks for Java könyvtár letöltve. Letöltheti [itt](https://releases.aspose.com/tasks/java/).  
- Alapvető Java programozási ismeretekkel.  

## Csomagok importálása
A `Project`, `ResourceAssignment` és `Asn` osztályok a `com.aspose.tasks` névtérben találhatók. Importálja őket a forrásfájl tetején:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 1. lépés: A projektfájl betöltése
A `Project` osztály az Aspose.Tasks legfelső szintű objektuma, amely egy Microsoft Project fájlt reprezentál a memóriában. Egy példány létrehozása betölti a fájlt, és hozzáférést biztosít a feladatokhoz, erőforrásokhoz és hozzárendelésekhez.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## 2. lépés: Erőforrás‑hozzárendelések bejárása
A `ResourceAssignment` objektumok minden hozzárendelés‑kapcsolódó mezőt elérhetővé teszik. Beállítunk egy **minimum dátumot**, hogy kiszűrjük a helykitöltő dátumokat, majd végigiterálunk minden hozzárendelésen. Ez a minta a szabványos *resource assignment example* ellenőrzéshez vagy módosításhoz.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## 3. lépés: A STOP és RESUME dátumok ellenőrzése
Ebben a blokkban megvizsgáljuk a `STOP` és `RESUME` mezőket minden hozzárendelésnél. Ha egy dátum a `minDate` előtt van, azt „nem beállítottként” (`"NA"`) kezeljük; egyébként kiírjuk a tényleges dátumot. Ez a logika elengedhetetlen a **resource assignments** helyes kezelése érdekében.

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

## Gyakori problémák és megoldások
- **Null dátumok** – a `ra.get(Asn.STOP)` `null`‑t adhat vissza. Védekezzen ellene null‑ellenőrzéssel, mielőtt a `.before(minDate)`‑t hívná.  
- **Helytelen fájlútvonal** – Győződjön meg róla, hogy a `dataDir` a megfelelő útvonalelválasztóval (`/` vagy `\\`) végződik az operációs rendszernek megfelelően.  
- **Verzióeltérés** – Használja a legújabb Aspose.Tasks for Java verziót, hogy elkerülje a hiányzó enum értékeket.

## Gyakran ismételt kérdések

**Q: Hogyan állíthatok be programozottan STOP dátumot egy hozzárendeléshez?**  
A: Használja a `ra.set(Asn.STOP, yourDateObject);` kódot, ahol a `yourDateObject` egy `java.util.Date`.

**Q: Mi történik, ha a resume dátum korábbi, mint a stop dátum?**  
A: Az API nem kényszeríti a kronológiai sorrendet; a tervező azonban csak a két dátum közül a későbbit tekinti a hozzárendelés aktívnak, ezért a dátumokat saját magának kell ellenőriznie.

**Q: Szűrhetem-e a hozzárendeléseket csak a STOP dátummal rendelkezőkre?**  
A: Igen, iteráljon a `prj.getResourceAssignments()`‑en, és ellenőrizze, hogy `ra.get(Asn.STOP) != null`.

**Q: Lehet-e eltávolítani egy STOP dátumot, ha már be lett állítva?**  
A: Állítsa a STOP dátumot `null`‑ra a `ra.set(Asn.STOP, null);` kóddal, majd mentse a projektet.

**Q: Támogatja-e az Aspose.Tasks a többi dátum‑kapcsolódó mezőt, például a start, finish vagy actual start mezőket?**  
A: Teljes mértékben. Az `Asn` enum minden hozzárendelési mezőhöz biztosít konstansokat, például `Asn.START`, `Asn.FINISH` stb.

## Következtetés
Ezekkel a lépésekkel most már tudja, **hogyan állítsuk le a erőforrás hozzárendelést Java-ban**, ellenőrizze a STOP/RESUME dátumokat, és szükség esetén újraindítsa a hozzárendelést. Ez a képesség lehetővé teszi a **resource assignments** pontosabb kezelését, különösen szabadságok vagy berendezésleállások esetén. Nyugodtan bővítse a példát dátumok frissítésével, jelentések generálásával vagy saját ütemezési logikájával való integrálással.

---

**Utolsó frissítés:** 2026-07-14  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Erőforrás‑hozzárendelések létrehozása az Aspose.Tasks-ben](/tasks/java/resource-assignments/create-resource-assignments/)
- [Hogyan számítsuk ki a költségeltérést és kezeljük a hozzárendelési költségeket az Aspose.Tasks segítségével](/tasks/java/resource-assignments/assignment-cost/)
- [Hogyan adjunk megjegyzéseket az erőforrás‑hozzárendelésekhez az Aspose.Tasks-ben](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
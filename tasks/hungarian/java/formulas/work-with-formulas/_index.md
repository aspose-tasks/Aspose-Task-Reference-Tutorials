---
date: 2026-02-13
description: Tanulja meg, hogyan számítsa ki a napok számát dátumok között, hozzon
  létre egy tesztprojektet, és adjon hozzá egy egyéni mezőt a Microsoft Project fájlok
  manipulálása közben az Aspose.Tasks for Java használatával.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Napok számítása dátumok között az Aspose.Tasks for Java segítségével
url: /hu/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Napok számítása dátumok között az Aspose.Tasks for Java segítségével

## Bevezetés
Ebben a bemutatóban **napok számítása dátumok között** fogod elvégezni egy tesztprojekt létrehozásával, egy egyéni mező hozzáadásával, és a Microsoft Project képletek használatával az Aspose.Tasks Java könyvtárán keresztül. Akár ütemterveket kell generálnod, határidőket számolnod, vagy jelentéseket automatizálnod, az Aspose.Tasks lehetővé teszi a Project adatok programozott manipulálását asztali telepítés nélkül. A útmutató végére egy futtatható példát kapsz, amely definiál egy kiterjesztett attribútumot, beállít egy feladat határidejét, és MPP fájlként menti a projektet.

## Gyors válaszok
- **Miről szól a bemutató?** Tesztprojekt létrehozása, egyéni mező hozzáadása, kiterjesztett attribútum definiálása, és feladat határidő beállítása egy képlettel, amely napok számítását végzi dátumok között.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (legújabb verzió).  
- **Szükségem van licencre?** Egy ingyenes próba verzió elegendő fejlesztéshez; licenc szükséges a termeléshez.  
- **Milyen IDE-t használhatok?** Bármely Java IDE (IntelliJ IDEA, Eclipse, VS Code), amely támogatja a JDK 8+.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc a kód másolásához és futtatásához.

## Mi a “napok számítása dátumok között” az Aspose.Tasks-ben?
A napok számítása dátumok között azt jelenti, hogy egy Project képletet használunk, amely egy dátummezőt (például **Finish**) egy másikból (például **Deadline**) von le, és a numerikus különbséget napokban adja vissza. Ez hasznos a menetrend csúszásának nyomon követésére, a puffert idő mérésére vagy egyedi jelentések készítésére.

## Miért használjuk az Aspose.Tasks-et a napok számításához dátumok között?
- **Teljes API lefedettség** – hozzáférés minden Project, Task és Resource tulajdonsághoz.  
- **Nincs szükség Office telepítésre** – szervereken, CI pipeline-okon és Docker konténerekben is működik.  
- **Keresztplatformos** – Windows, Linux és macOS rendszereken fut ugyanazzal a Java kóddal.  
- **Robusztus képletmotor** – lehetővé teszi számítások definiálását, például `[Deadline] - [Finish]` közvetlenül a projektfájlban.

## Hogyan állítsunk be határidőt egy feladathoz
A határidő beállítása az első lépés, mielőtt kiszámolnád az intervallumot. A határidő a feladat `Tsk.DEADLINE` mezőjében tárolódik, és egy `java.util.Calendar` példány segítségével adható meg.

## Hogyan definiáljunk kiterjesztett attribútumot
A kiterjesztett attribútum az az egyéni mező, amely a képleted eredményét tárolja. Egyszer definiálod, adsz neki egy alias-t a könnyebb olvashatóságért, majd egy képletet csatolsz, amely a dátumok kivonását végzi.

## Előkövetelmények
Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

- **Java Development Kit (JDK) 8+** – letölthető az Oracle weboldaláról vagy az OpenJDK-ból.  
- **Aspose.Tasks for Java** – szerezd be a legújabb JAR‑t a [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) oldalról, és add hozzá a projekt classpath‑éhez vagy Maven/Gradle függőségekhez.

## Csomagok importálása
Először importáljuk a szükséges osztályokat:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Tesztprojekt létrehozása egy egyéni mezővel
Először **létrehozunk egy tesztprojektet** és hozzáadunk egy egyéni mezőt, amely később a képlet eredményét fogja tárolni.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tipp:* `CreateTestProjectWithCustomField()` egy segédmetódus, amely egy minimális ütemtervet épít, és regisztrál egy kiterjesztett attribútumot, amely készen áll a képlet hozzárendelésére.

### 2. lépés: Kiterjesztett attribútum definiálása (Egyéni mező hozzáadása)
Ezután **definiálunk egy kiterjesztett attribútumot** – lényegében az egyéni mezőt – és adunk neki egy barátságos alias-t. Itt történik a **egyéni mező** logikája.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** olvashatóvá teszi a mezőt a Projectben.  
- **Formula** kiszámítja a napok számát egy feladat *Finish* dátuma és a *Deadline* között – a *napok számítása dátumok között* lényege.

### 3. lépés: Határidő beállítása egy feladathoz (Határidő feladat hozzáadása és feladat határidő beállítása)
Most **hozzáadjuk a határidő adatokat** a *Deadline* tulajdonság beállításával egy konkrét feladatra.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- A `Calendar` példány határozza meg a pontos határidő pillanatát.  
- `set(Tsk.DEADLINE, …)` **beállítja a feladat határidejét** a kiválasztott feladatra.

### 4. lépés: Projekt mentése (Microsoft Project fájl manipulálása)
Végül **manipuláljuk a Microsoft Projectet** a változások MPP fájlba mentésével.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Megnyithatod a `SaveFile.mpp` fájlt a Microsoft Projectben, hogy lásd az egyéni mezőt, a képlet eredményét és a határidőt a menetrendben.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Formula not evaluating** | Győződj meg arról, hogy az attribútum `Formula` karakterlánca a helyes mezőneveket használja (pl. `[Deadline]`, `[Finish]`). |
| **Task not found** | Ellenőrizd, hogy a feladat ID (`1` a példában) létezik; a `project.getRootTask().getChildren().size()` segítségével hibakereshetsz. |
| **License exception** | Alkalmazz érvényes Aspose.Tasks licencet minden API hívás előtt (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Tasks-et más programozási nyelvekkel?**  
A: Igen, az Aspose.Tasks API‑kat biztosít .NET, Java és egyéb platformok számára, így **manipulálhatod a Microsoft Project** fájlokat a választott nyelveden.

**Q: Elérhető ingyenes próba verzió az Aspose.Tasks-hez?**  
A: Természetesen. Tölts le egy teljes funkcionalitású próbaverziót a [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Hol találok részletes dokumentációt az Aspose.Tasks-hez?**  
A: A hivatalos dokumentáció a [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) oldalon érhető el.

**Q: Hogyan kaphatok támogatást az Aspose.Tasks-hez?**  
A: Látogasd meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15), ahol kérdéseket tehetsz fel és tapasztalatokat oszthatsz meg a közösséggel.

**Q: Szükségem van ideiglenes licencre a kiértékeléshez?**  
A: Ideiglenes licenc elérhető rövid távú teszteléshez; kérhetsz egyet [itt](https://purchase.aspose.com/temporary-license/).

---

**Utolsó frissítés:** 2026-02-13  
**Tesztelve:** Aspose.Tasks for Java 24.12 (legújabb a kiadás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
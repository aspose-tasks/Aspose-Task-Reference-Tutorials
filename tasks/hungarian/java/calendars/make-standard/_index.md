---
date: 2026-08-13
description: Ismerje meg, hogyan hozhat létre szabványos MS Project naptárat Java-ban
  az Aspose.Tasks használatával. Ez a lépésről‑lépésre útmutató bemutatja, hogyan
  készítsen szabványos MS Project naptárat, állítsa be alapértelmezettként, és mentse
  a fájlt.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Szabványos naptár készítése az Aspose.Tasks-ben
og_description: Hogyan hozzunk létre naptárat Java-ban az Aspose.Tasks segítségével.
  Tanulja meg, hogyan építsen szabványos MS Project naptárat, állítsa be alapértelmezettként,
  és mentse el a projektfájlt percek alatt.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Hogyan hozzunk létre naptárat – szabványos naptár készítése az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Hogyan hozzunk létre naptárat – szabványos naptár készítése az Aspose.Tasks-ben
url: /hu/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre naptárat – szabványos naptár készítése az Aspose.Tasks-ben

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan hozhat létre **naptár** objektumokat a Microsoft Project fájlokhoz az Aspose.Tasks for Java könyvtár használatával. Lépésről lépésre végigvezetünk egy szabványos MS Project naptár létrehozásán, annak alapértelmezett (szabványos) naptárként való beállításán és a projektfájl mentésén. A útmutató végére képes lesz a naptár létrehozását bármely Java‑alapú projektmenedzsment megoldásba integrálni.

## Gyors válaszok
- **Mi jelent a „szabványos naptár”?** Ez az alapértelmezett munkaidő‑definíció, amelyet azok a feladatok használnak, amelyekhez nincs egyedi naptár hozzárendelve.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java – egy tiszta Java API, amely Microsoft Project telepítése nélkül is működik.  
- **Szükségem van licencre?** A fejlesztéshez egy ingyenes próba verzió elegendő; a termelésben való használathoz kereskedelmi licenc szükséges.  
- **Milyen fájlformátum jön létre?** Egy XML‑alapú Microsoft Project fájl (`.xml`).  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alap naptár beállításához.

## Mi az a szabványos naptár a Microsoft Projectben?
A szabványos naptár meghatározza a projekt alapértelmezett munkanapjait és munkaóráit, általában hétfőtől péntekig, 8 ó‑tól 17 ó‑ig. Amikor hozzáad egy szabványos naptárat, minden feladat, amelyhez nincs egyedi naptár rendelve, örökli ezeket a munkaidőket, ezáltal biztosítva a konzisztens ütemezést a projektben.

## Miért használjuk az Aspose.Tasks-et naptár létrehozásához?
Az Aspose.Tasks for Java támogat **50+ bemeneti és kimeneti formátumot**, és akár **10 000 feladatot** tartalmazó projekteket is képes feldolgozni anélkül, hogy a teljes fájlt a memóriába töltené. Ez a tiszta Java könyvtár lehetővé teszi a Project fájlok automatizált létrehozását szervereken, CI csővezetékeken vagy bármely Java alkalmazásban, kiküszöbölve a licencelt Microsoft Project telepítésének szükségességét.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következők rendelkezésre állnak:

### Java Development Kit (JDK) telepítése
Telepítse a legújabb JDK-t az Oracle weboldaláról vagy egy OpenJDK disztribúcióból.

### Aspose.Tasks for Java könyvtár
Töltse le a könyvtárat a [letöltési oldalról](https://releases.aspose.com/tasks/java/). Adja hozzá a JAR-t a projekt osztályútvonalához.

## Csomagok importálása
Ehhez az útmutatóhoz csak egy importálásra van szükségünk:

```java
import com.aspose.tasks.*;
```

## Lépésről‑lépésre útmutató

### 1. lépés: az adatkönyvtár beállítása
Határozza meg, hogy hová legyen mentve a generált projektfájl.

```java
String dataDir = "Your Data Directory";
```

Cserélje le a `"Your Data Directory"`-t a gépén lévő abszolút útvonalra (például `C:/Projects/Output/`).

### 2. lépés: projekt példány létrehozása
`Project` az Aspose.Tasks legfelső szintű objektuma, amely egyetlen Microsoft Project fájlt képvisel a memóriában. Példányosítva egy tárolót kap a naptárak, feladatok, erőforrások és egyéb projektadatok számára.

```java
Project project = new Project();
```

### 3. lépés: a naptár definiálása és szabványossá tétele
`Calendar` az az osztály, amely a munkaidő‑ütemezést modellezi. Egy új, **„My Cal”** nevű naptár hozzáadása és a `makeStandardCalendar` meghívása alapértelmezett naptárként állítja be a teljes projekt számára.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro tip:** A `makeStandardCalendar` metódus automatikusan alapértelmezettként jelöli a megadott naptárat a projektben, ami pontosan az, amire szüksége van, ha **szabványos naptár** funkciót szeretne hozzáadni.

### 4. lépés: a projekt mentése
A SaveFileFormat egy felsorolás, amely meghatározza a projekt mentésekor használandó fájlformátumot.  
Mentse a projektet (beleértve az új naptárat is) egy XML fájlba.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

A fájlnevet vagy formátumot (`SaveFileFormat.Pp`) megváltoztathatja, ha másik Project verziót szeretne.

### 5. lépés: befejezési üzenet megjelenítése
Adjon magának egy vizuális jelzést, hogy a folyamat hibamentesen befejeződött.

```java
System.out.println("Process completed Successfully");
```

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Fájl nem található** | `dataDir` egy nem létező mappára mutat | Hozzon létre mappát, vagy használjon abszolút útvonalat |
| **Licenc kivétel** | Éles környezetben érvényes Aspose.Tasks licenc nélkül fut | Licencfájlt alkalmazzon a következővel: `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Üres naptár** | Elfelejtette hozzáadni a munkaidő‑definíciókat | Használja a `cal1.getWeekDays().add(WeekDay.DayType.Monday)` stb., ha egyedi órákat kell megadni |

## Gyakran ismételt kérdések

**K: Az Aspose.Tasks kompatibilis a Microsoft Project minden verziójával?**  
V: Igen, az Aspose.Tasks széles körű Microsoft Project verziókat támogat, a 2000‑es verzióktól a legújabb kiadásokig.

**K: További testreszabásra van lehetőség a naptár beállításaiban?**  
V: Természetesen! Módosíthatja a munkanapokat, hozzáadhat kivételeket, és meghatározhat konkrét munkaidőket a `WeekDay` és `WorkingTime` osztályok használatával.

**K: Az Aspose.Tasks alkalmas vállalati szintű alkalmazásokra?**  
V: Biztosan. A könyvtár magas teljesítményű, skálázható környezetekre lett tervezve, és átfogó támogatást nyújt nagy méretű Project fájlokhoz.

**K: Az Aspose.Tasks nyújt technikai támogatást fejlesztőknek?**  
V: Igen, az Aspose dedikált fórumokat, jegy‑alapú támogatást és kiterjedt dokumentációt biztosít, hogy gyorsan megoldhassa a felmerülő problémákat.

**K: Kipróbálhatom az Aspose.Tasks-et vásárlás előtt?**  
V: Igen, ingyenes próba verziót tesztelhet a [weboldalon](https://purchase.aspose.com/buy), amely lehetővé teszi az összes funkció értékelését a döntés előtt.

**Utoljára frissítve:** 2026-08-13  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Naptár hozzáadása projekthez az Aspose.Tasks for Java-val](/tasks/java/calendars/create/)
- [Hogyan állítsuk be a projekt naptárát Java‑ban az Aspose.Tasks segítségével](/tasks/java/calendars/properties/)
- [Egyéni naptárkivételek létrehozása az Aspose.Tasks for Java-val](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
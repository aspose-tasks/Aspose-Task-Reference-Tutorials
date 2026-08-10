---
date: 2026-07-29
description: Ismerje meg, hogyan ütemezhet nem munkanapokat egy projekt naptár létrehozásával
  az Aspose.Tasks for Java segítségével, hétköznapi kivételek meghatározásával és
  az ünnepnapok ütemezésének kezelésével.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Nem munkanapok ütemezése – Projekt naptár létrehozása Aspose
og_description: Ütemezze a nem munkanapokat az Aspose.Tasks for Java használatával.
  Ismerje meg, hogyan határozhatja meg a hétköznapokat, adhat hozzá naptárkivételes
  napokat, és kezelheti hatékonyan az ünnepnapok ütemezését.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Nem munkanapok ütemezése – Projekt naptár létrehozása Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Nem munkanapok ütemezése – Projekt naptár létrehozása Aspose
url: /hu/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nem munkanapok ütemezése – Projekt naptár létrehozása Aspose

### Bevezetés
Amikor egy projekthez **nem munkanapok ütemezésére** van szükség, képesnek kell lennie ünnepnapok, különleges műszakok vagy ideiglenes lezárások modellezésére közvetlenül a projekttervben. Az Aspose.Tasks for Java teljes irányítást biztosít a naptárdefiníciók felett, lehetővé téve, hogy olyan kivételeket adjon hozzá, amelyek a valós világ ütemezését tükrözik. Ebben az oktatóanyagról lépésről‑lépésre bemutatjuk, hogyan definiáljunk hétköznapokat a naptárkivételhez, hogy a projekt idővonalai pontosak és megbízhatóak maradjanak. A végére láthatja, hogyan illeszkedik ez egy átfogó **nem munkanapok ütemezése** stratégiába bármely vállalati projektnél.

## Gyors válaszok
- **Mi jelent a “schedule non working days”?**  
  Ez azt jelenti, hogy az Aspose.Tasks segítségével létrehoz egy naptárat, amely meghatározott dátumokat nem‑munkanapként jelöl, automatikusan befolyásolva a feladatok dátumait.  
- **Szükségem van licencre a példa futtatásához?**  
  A fejlesztéshez egy ingyenes próbaverzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Mely IDE-k támogatottak?**  
  IntelliJ IDEA, Eclipse, NetBeans vagy bármely Java‑kompatibilis szerkesztő.  
- **Hozzáadhatok több kivételt ugyanahhoz a naptárhoz?**  
  Igen – hozzáadhat annyi `CalendarException` objektumot, amennyire szüksége van.  
- **Milyen fájlformátumokba menthetem a projektet?**  
  XML, MPP és több más, az Aspose.Tasks által támogatott formátum.

## Mi az a projekt naptár az Aspose.Tasks-ben?
A **projekt naptár** az Aspose.Tasks legfelső szintű objektuma, amely meghatározza a projekt munkanapjait és munkaóráit. Közvetlenül befolyásolja a feladatok kezdő‑/záró dátumait, az erőforrás‑allokációt és az általános ütemezési számításokat. A naptár testreszabásával biztosítható, hogy az ütemterv a valós világ korlátozásait, például a vállalati ünnepnapokat vagy a hétvégi munkavégzési szabályzatot tiszteletben tartsa.

## Miért definiáljunk hétköznapokat a naptárkivételekhez?
A hétköznapok kivételeinek definiálása biztosítja, hogy a projektmotor ezeket a napokat nem‑munkanapként kezelje, megakadályozva, hogy a feladatok automatikusan rájuk ütemeződjenek, és az idővonalat a valós világ korlátozásaival, például ünnepnapokkal, karbantartási időszakokkal vagy szervezeti szintű különleges műszakmintákkal összhangban tartsa.

- **Pontos ütemezés:** A feladatok nem kerülnek ünnepnapokra vagy leállási időszakokra.  
- **Erőforrás‑tervezés:** Az erőforrások csak érvényes munkanapokon kerülnek kiosztásra, elkerülve a túlterhelést.  
- **Megfelelés:** Az ütemtervek automatikusan követik a szervezeti szabályzatokat vagy a jogi ünnepnaptárakat.

## Nem munkanapok ütemezése naptárkivételekkel
Amikor egy **nem munkanapok ütemezését** tartja karban, általában van egy főlista az ünnepnapokról, karbantartási időszakokról vagy egyéb leállási időszakokról. Ezeknek a dátumoknak a `CalendarException` objektumokként való hozzáadása garantálja, hogy minden számítás – legyen az kritikus út elemzés vagy erőforrás‑kiegyenlítés – automatikusan figyelembe vegye ezeket a korlátozásokat. Ez a megközelítés megszünteti a manuális dátumkorrekciókat és csökkenti az ütemezési eltérés kockázatát.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – letöltés a hivatalos [Aspose.Tasks Java letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans vagy bármely Java‑kompatibilis szerkesztő.

## Hogyan ütemezzünk nem munkanapokat naptárkivételekkel
Töltse be a projektet, hozzon létre egy egyéni naptárat, és adjon hozzá `CalendarException` objektumokat, amelyek a kívánt hétköznapokat nem‑munkanapként jelölik. Ez a teljes folyamat néhány egyszerű lépésben elvégezhető, és az eredményül kapott naptár automatikusan befolyásolja az összes feladat ütemezési logikáját.

### Lépésről‑lépésre útmutató

### 1. lépés: Szükséges csomagok importálása
Szükségünk van az Aspose.Tasks alap osztályaira és a Java `GregorianCalendar` osztályára a dátumkezeléshez.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### 2. lépés: Adatkönyvtár meghatározása
Adja meg, hogy a generált projektfájl hová legyen mentve.

```java
String dataDir = "Your Data Directory";
```

### 3. lépés: Projekt példány létrehozása
`Project` a fő objektum, amely minden projektadatot tartalmaz, beleértve a feladatokat, erőforrásokat és naptárakat.

```java
Project project = new Project();
```

### 4. lépés: Naptár definiálása
`Calendar` egy projektben a munkavégzési és nem‑munkavégzési időket tartalmazó ütemezést képviseli.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### 5. lépés: Hétköznapok kivételének definiálása
`CalendarException` egy olyan időszakot jelöl, amely a naptárban nem‑munkanapként van megjelölve.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### 6. lépés: Projekt mentése
Mentse a projektet, beleértve az egyéni naptárat és annak kivételét, egy XML fájlba.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Gyakori problémák és megoldások
| Issue | Solution |
|-------|----------|
| **A kivétel dátumok nem alkalmazódnak** | Győződjön meg arról, hogy a `setEnteredByOccurrences(false)` be van állítva, és a `FromDate/ToDate` értékek helyesek. |
| **A mentett fájl üres** | Ellenőrizze, hogy a `dataDir` egy írható mappára mutat, és a fájlnév `.xml` kiterjesztéssel végződik. |
| **A naptár nem jelenik meg a feladat ütemezésében** | Rendelje hozzá a naptárat a feladatokhoz vagy erőforrásokhoz a `task.setCalendar(cal)` vagy `resource.setCalendar(cal)` használatával. |

## Gyakran feltett kérdések

**Q: Definiálhatok több kivételt különböző hétköznapokra ugyanabban a naptárban?**  
A: Igen. Adjunk hozzá további `CalendarException` objektumokat a `cal.getExceptions()`-hez minden egyes különálló időszak vagy szabály esetén.

**Q: Az Aspose.Tasks for Java kompatibilis különböző Java IDE-kkel?**  
A: Teljes mértékben. A könyvtár működik az IntelliJ IDEA, Eclipse, NetBeans és bármely, a szabványos Java projektekhez támogatott IDE-vel.

**Q: Testreszabhatom a kivételtípusokat a napi kivételeken kívül?**  
A: Igen. Használja a `CalendarExceptionType.Weekly`, `Monthly` vagy `Yearly` típusokat a tervezési igényeihez.

**Q: Hogyan kezelhetem a kivételeket dinamikusan a projekt követelményei alapján?**  
A: Készítse el a kivétel objektumokat programozottan – például olvassa be az ünnepnapok dátumait egy adatbázisból vagy konfigurációs fájlból, és egy ciklusban hozza létre a `CalendarException` példányokat.

**Q: Elérhető próba verzió az Aspose.Tasks for Java-hoz?**  
A: Igen, letölthet egy ingyenes próbaverziót a [Aspose.Tasks Java letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Összegzés
Ezekkel a lépésekkel most már tudja, hogyan **ütemezzen nem munkanapokat** egy projekt naptár létrehozásával és hétköznapok kivételének definiálásával, amely pontosan tükrözi az ünnepnapokat vagy a különleges nem‑munkanap időszakokat. A megfelelő naptárkonfiguráció elengedhetetlen a reális ütemezésekhez, az erőforrás‑allokációhoz és a projekt általános sikeréhez. További felfedezéseket tehet az egyéni naptár feladatokhoz vagy erőforrásokhoz való csatolásával, valamint más kivételtípusok kipróbálásával, hogy átfogó **nem munkanapok ütemezését** építse fel bármely projekthez.

---

**Legutóbb frissítve:** 2026-07-29  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Naptár hozzáadása projekthez az Aspose.Tasks for Java segítségével](/tasks/java/calendars/create/)
- [Naptárkivétel létrehozása Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [Hogyan állítsunk be naptárat és definiáljunk hétköznapokat az MS Projectben az Aspose.Tasks segítségével](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
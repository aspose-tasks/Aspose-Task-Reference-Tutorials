---
date: 2026-08-13
description: Tanulja meg, hogyan adhat hozzá ünnepnapokat a naptárhoz, rendelje hozzá
  a naptárat egy projekthez, és mentse a MS Project fájlt MPP formátumba az Aspose.Tasks
  for Java segítségével.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Naptár frissítése MPP formátumba az Aspose.Tasks segítségével
og_description: Ünnepnapok hozzáadása a naptárhoz, hozzárendelése egy projekthez,
  és a schedule konvertálása MPP formátumba az Aspose.Tasks for Java segítségével.
  Tanulja meg a lépésről‑lépésre automatizálást.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Ünnepnapok hozzáadása a naptárhoz és mentés MPP formátumban az Aspose.Tasks
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Ünnepnapok hozzáadása a naptárhoz és mentés MPP formátumban az Aspose.Tasks
  segítségével
url: /hu/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ünnepnapok hozzáadása a naptárhoz és mentés MPP formátumban az Aspose.Tasks segítségével

## Bevezetés

A modern projektmenedzsmentben gyakran szükség van **add holidays to calendar** fájlok hozzáadására, egy **MS Project calendar** létrehozására, majd a menetrend megosztására natív MPP formátumban. Akár több forrásból származó ütemterveket konszolidálsz, akár örökölt adatokat migrálsz, a naptár programozott generálása kiküszöböli a kézi hibákat és felgyorsítja a szállítást. Ez a bemutató végigvezeti a teljes folyamaton: naptár létrehozása MS Projectben, ünnepnapokkal testreszabása, **assign calendar to project**, és végül **convert project to MPP** az Aspose.Tasks Java API használatával.

## Gyors válaszok
- **Mire terjed ki ez a bemutató?** Ünnepnapok hozzáadása a naptárhoz, annak projekthez rendelése, és az eredmény mentése MPP fájlként az Aspose.Tasks for Java használatával.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a kereskedelmi licenc a termeléshez kötelező.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb (JDK 8+).  
- **Testreszabhatom a naptárat?** Igen – hozzáadhat munkavégzési időket, kivételeket és ünnepnapokat.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap naptár esetén.  

## Mi az a „create calendar MS Project”?

Hozzáadni egy calendar MS Project-et azt jelenti, hogy meghatározzuk a munkanapokat, órákat és kivételeket, amelyek a feladatütemezést vezérlik egy Microsoft Project fájlban. Az Aspose.Tasks segítségével programozottan felépíthető ez a naptár, beállíthatók az ünnepnapok, és beágyazható egy projektbe anélkül, hogy megnyitnánk a MS Project felhasználói felületét.

## Miért használjuk az Aspose.Tasks-et ehhez a feladathoz?

Az Aspose.Tasks-et azért érdemes használni, mert teljes Java kompatibilitást biztosít, nem szükséges a Microsoft Office, és lehetővé teszi natív MPP fájlok közvetlen generálását és mentését kódból. A könyvtár támogatja a naptár összes funkcióját, bármilyen szerverkörnyezetben működik, és 10 000 feladatot is feldolgoz egy másodpercnél gyorsabban.

## Előkövetelmények

1. **Java Development Kit (JDK) 8+** – ellenőrizze, hogy a `java -version` 1.8 vagy újabb verziót jelent.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR fájlt az [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse vagy bármely kedvelt szerkesztő.  
4. **Basic Java knowledge** – ismerje a class-eket, metódusokat és a fájl I/O-t.

## Hogyan adjon hozzá ünnepnapokat a naptárhoz

Az ünnepnapok hozzáadásához létre kell hozni egy új `Calendar` objektumot, lekérni a `Exceptions` gyűjteményét, és `DateException` bejegyzéseket hozzáadni minden egyes ünnepnap dátumához. A `DateException` egyetlen nem munkanapot vagy időintervallumot jelöl a naptárban. Az Aspose.Tasks ezeket a dátumokat nem munkanapként kezeli, biztosítva, hogy a feladatok a meghatározott ünnepnapok körül legyenek ütemezve.

### 1. lépés: szükséges csomagok importálása

Először is, hozza be az Aspose.Tasks osztályokat és a Java segédfüggvényeket a láthatóságba.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 2. lépés: az adatkönyvtár beállítása

Határozza meg, hogy hol lesznek a bemeneti sablon és a kimeneti fájlok. Cserélje le a helyőrzőt a gépén lévő tényleges útvonalra.

```java
String dataDir = "Your Data Directory";
```

### 3. lépés: bemeneti és kimeneti fájlnevek meghatározása

Betöltünk egy meglévő MPP fájlt (vagy egy üres projektet), és az eredményt egy új fájlba írjuk.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 4. lépés: a projekt betöltése és új naptár hozzáadása

A `Project` osztály egy MS Project fájlt reprezentál a memóriában, és hozzáférést biztosít a naptárakhoz, feladatokhoz és erőforrásokhoz.

Hozzon létre egy `Project` példányt a forrásfájlból, és adjon hozzá egy **„Calendar 1”** nevű naptárat.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 5. lépés: a naptár testreszabása (opcionális)

A `Calendar` objektum meghatározza a munkanapokat, órákat és kivételeket egy projekt ütemezéséhez.

Ha konkrét munkavégzési időkre, ünnepnapokra vagy kivételekre van szüksége, hívja meg saját segédmetódusát. A példában a `GetTestCalendar` a helyőrző.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Közvetlenül módosíthatja a `cal1.getWeekDays()`-t, hogy beállítsa a munkavégzési órákat a hét minden napjára, vagy használja a `cal1.getExceptions()`-t a **add holidays to calendar**.

### 6. lépés: a naptár hozzárendelése a projekthez

Adja meg a projektnek, hogy az összes ütemezési számításhoz az újonnan létrehozott naptárat használja.

```java
project.set(Prj.CALENDAR, cal1);
```

### 7. lépés: a projekt mentése MPP formátumban

A `SaveFileFormat` felsorolás határozza meg a kimeneti formátumot, ahol a `Mpp` a natív Microsoft Project formátumot jelöli.

Most **convert project to MPP** a `SaveFileFormat.Mpp` opcióval mentve.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 8. lépés: a sikeres befejezés megerősítése

Egy egyszerű konzol üzenet jelzi, hogy a folyamat hibamentesen befejeződött.

```java
System.out.println("Process completed Successfully");
```

## Gyakori felhasználási esetek

- **Automatizált ütemterv generálás** ismétlődő projektekhez (pl. heti sprintek).  
- **Örökölt CSV vagy Excel naptárak migrálása** egy teljes funkcionalitású MS Project fájlba.  
- **Szerver‑oldali jelentéskészítés**, ahol egy webszolgáltatás kérésre MPP fájlt ad vissza.  

## Hibaelhárítás és gyakori buktatók

| Probléma | Ok | Megoldás |
|----------|----|----------|
| `NullPointerException` on `project.save` | `dataDir` egy nem létező mappára mutat | Győződjön meg arról, hogy a könyvtár létezik, vagy hozza létre programozottan. |
| Calendar not applied to tasks | A feladatok még mindig az alapértelmezett naptárra hivatkoznak | A `Prj.CALENDAR` beállítása után frissítse minden feladat `Task.CALENDAR` értékét is, ha korábban felül lett írva. |
| Output file is 0 KB | Hiányzó írási jogosultság | Futtassa a JVM-et megfelelő fájlrendszer jogosultságokkal, vagy válasszon írható útvonalat. |

## Gyakran feltett kérdések

**Q: Az Aspose.Tasks for Java kompatibilis a különböző MS Project verziókkal?**  
A: Igen, az Aspose.Tasks támogatja az összes Microsoft Project fájlformátumot a Project 2007-től a Project 2024-ig, több mint 10 verziót lefedve.

**Q: Testreszabhatom a naptárakat a projekt specifikus követelményei szerint?**  
A: Teljes mértékben. Meghatározhat munkanapokat, egyedi munkahét beállításokat, hozzáadhat ünnepnapokat, és akár több naptárat is létrehozhat egyetlen projektfájlban.

**Q: Nyújt-e az Aspose.Tasks for Java támogatást a hibaelhárításhoz és segítségnyújtáshoz?**  
A: Igen, segítséget kaphat az Aspose.Tasks közösségi fórumon: [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Elérhető-e ingyenes próba verzió az Aspose.Tasks for Java-hoz?**  
A: Igen, egy teljes funkcionalitású ingyenes próba verzió elérhető: [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java-hoz?**  
A: Ideiglenes licenceket a Aspose weboldalon kérhet: [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Utolsó frissítés:** 2026-08-13  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó bemutatók

- [Naptár hozzáadása projekthez az Aspose.Tasks for Java segítségével](/tasks/java/calendars/create/)
- [Hogyan definiáljunk hétköznapokat MS Project naptárakban – Aspose.Tasks Java](/tasks/java/calendars/)
- [Egyéni naptárkivétel létrehozása az Aspose.Tasks for Java segítségével](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
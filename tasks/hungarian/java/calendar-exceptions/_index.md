---
date: 2026-11-06
description: Könnyedén hozhat létre egyedi naptárkivételket, integrálhatja az MS Project
  naptárát, és kezelheti, definiálhatja, kezelheti és lekérheti a naptárkivételket
  Java projektekben az Aspose.Tasks segítségével. Egyszerűsítse a projektfolyamatokat
  a hatékony projektmenedzsment érdekében.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Naptárkivétel
og_description: Ismerje meg, hogyan hozhat létre naptárkivételt Java-ban az Aspose.Tasks
  használatával. Kezelje a projekt naptárakat, állítson be nem munkanapokat, és módosítsa
  hatékonyan az MS Project naptárakat.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Naptárkivétel létrehozása az Aspose.Tasks for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Hogyan hozhatunk létre naptárkivételt az Aspose.Tasks for Java segítségével
url: /hu/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre naptárkivételes napokat az Aspose.Tasks for Java segítségével

## Bevezetés

`Aspose.Tasks` egy Java könyvtár, amely lehetővé teszi a Microsoft Project fájlok programozott létrehozását, manipulálását és konvertálását. Ebben az útmutatóban megtanulja, hogyan **hozzon létre naptárkivételes napokat** – egyedi nem‑munkaidőszakokat, amelyek felülbírálják a projekt alapértelmezett naptárát. A munka- és nemmunka napok pontos szabályozása elengedhetetlen a pontos ütemterv‑előrejelzéshez, erőforrás‑elosztáshoz és a regionális ünnepek betartásához. A útmutató végére azt is tudni fogja, hogyan **integráljon egy MS Project naptárat** Java‑alkalmazásába, valamint hogyan kérdezze le vagy módosítsa annak kivételeit.

## Gyors válaszok
- **Mit érhetek el?** Egyedi naptárkivételes napok létrehozása, módosítása és lekérdezése Java‑projektekben.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (legújabb stabil kiadás).  
- **Szükségem van licencre?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termelési környezetben.  
- **Dolgozhatok MS Project fájlokkal?** Természetesen – importálhat, szerkeszthet és exportálhat MS Project naptáradatokat.  
- **Szükséges-e valamilyen speciális beállítás?** Csak adja hozzá az Aspose.Tasks JAR‑t az osztályútvonalához, és importálja a megfelelő osztályokat.  

## Hogyan hozzunk létre egyedi naptárkivételes napokat az Aspose.Tasks for Java‑ban?

Az Aspose.Tasks for Java‑ban egyedi naptárkivételes napok létrehozásához töltse be a cél Project‑et, szerezze be annak Calendar‑ját, határozza meg a kivétel kezdő‑ és befejező dátumát a kívánt munkaidővel, opcionálisan állítson be ismétlődési mintát, majd mentse a projektet. Ez a sorrend azonnal hozzáadja a kivételt, és a .mpp fájlba menti.

`Project` osztály az Aspose.Tasks elsődleges objektuma, amely egy teljes Microsoft Project fájlt modellez. A `Project` osztály egy Microsoft Project fájlt képvisel, és hozzáférést biztosít annak tartalmához. A `Calendar` objektum a projekt munka‑ és nemmunkaidőit definiálja. A `Calendar` osztály a munkaidő‑szabályok, köztük a kivételek tárolója. Az `addException()` metódus új naptárkivételt ad a naptárhoz. Az `addException()` egy egyhívásos API, amely regisztrál egy nemmunka időszakot a megadott dátumtartományra.

A célprojekt betöltése a `Project project = new Project("example.mpp")` kóddal, majd a `Calendar` objektum lekérése, és az `addException()` hívása a kívánt dátumtartománnyal és munkaidő‑beállításokkal. Ez a kétlépéses minta azonnal létrehozza az új kivételt, és a projekt mentésekor menti azt. Ismétlődő ünnepekhez állítsa be a `RecurrencePattern`‑t a kivételen a mentés előtt.

Ezzel a módszerrel a **nemmunka napok** pontos beállítása lehetséges, legyen szó egyszeri leállásról vagy éves ünnepekről. A kivétel hozzáadása után meghívhatja a `project.save("updated.mpp")` parancsot a változások lemezre írásához.

### Lépések áttekintése
1. Töltse be a projektfájlt.  
2. Szerezze be vagy hozza létre a `Calendar` példányt.  
3. Határozza meg a kivétel dátumtartományát és munkaidejét.  
4. (Opcionális) Állítsa be az ismétlődést éves ünnepekhez.  
5. Mentse a projektet.

## Naptárkivételes napok kezelése az Aspose.Tasks‑ben
[Ismerje meg, hogyan adhat hozzá és távolíthat el naptárkivételes napokat az Aspose.Tasks for Java‑ban hatékonyan](./add-remove/). Amikor a projektmenedzsmentről van szó, a rugalmasság kulcsfontosságú. Az Aspose.Tasks lehetővé teszi, hogy könnyedén kezelje a naptárkivételes napokat, dinamikus módosításokat végezve a projekt ütemterveiben. Ez az útmutató lépésről‑lépésre vezet, biztosítva, hogy hatékonyan megértse a folyamatot. Fedezze fel, hogyan javíthatja projektmenedzsment folyamatait könnyedén.

## Hétköznapok meghatározása naptárkivételes napokhoz az Aspose.Tasks‑ben
[Ismerje meg a hétköznapok naptárkivételes napokhoz való meghatározásának művészetét Java‑projektekben](./define-weekdays/) az Aspose.Tasks használatával. A pontos projektütemezés részletekre való aprólékos figyelmet igényel. Az Aspose.Tasks segítségével pontosan meghatározhatja a hétköznapokat a naptárkivételes napokhoz, biztosítva, hogy projektjei zökkenőmentesen illeszkedjenek a specifikus ütemtervekhez. Ez az útmutató a tudással felvértez, hogy optimalizálja az ütemezést, és irányítást adjon a projekt ütemtervei felett.

## Események kezelése naptárkivételes napokban az Aspose.Tasks használatával
[Hatékonyan kezelje a naptárkivételes napokat Java‑projektekben](./handle-occurrences/) az Aspose.Tasks for Java‑val. A projektmenedzsment dinamikus folyamat, amely gyakran igényel módosításokat a váratlan események miatt. Az Aspose.Tasks lehetővé teszi, hogy hatékonyan kezelje a naptárkivételes napokat, áramvonalas megközelítést biztosítva a projektmenedzsmenthez. Tanulja meg a projekt bizonytalanságok kezelésének művészetét könnyedén ebben a részletes útmutatóban.

## Naptárkivételes napok lekérdezése az Aspose.Tasks‑szel
[Ismerje meg, hogyan kérdezze le a naptárkivételes napokat az MS Project‑ből az Aspose.Tasks for Java segítségével](./retrieve/). Integrálja zökkenőmentesen a naptárkivételes napokat a projektmenedzsment folyamatába az Aspose.Tasks segítségével. Ez az útmutató lépésről‑lépésre vezeti Önt a naptárkivételes napok lekérdezésének folyamatán, biztosítva a zökkenőmentes és hatékony integrációt projektjeibe. Szabadítsa fel az Aspose.Tasks erejét, hogy javítsa projektmenedzsment képességeit.

## Hogyan integráljuk az MS Project naptárat az Aspose.Tasks‑szel?
Az MS Project naptár integrálása az Aspose.Tasks‑sel magában foglalja a forrás .mpp fájl betöltését a Project osztály segítségével, annak alapértelmezett vagy egyedi Calendar objektumainak elérését, a szükséges módosítások vagy egyesítések végrehajtását a kivételeken, majd a frissített projekt mentését. Ez lehetővé teszi, hogy programozottan dolgozzon MS Project naptárakkal manuális UI‑interakció nélkül.

`Project` osztály az Aspose.Tasks elsődleges objektuma, amely egy teljes Microsoft Project fájlt modellez. Egy meglévő MS Project fájl importálása a `new Project("source.mpp")` használatával; a könyvtár automatikusan betölti az alapértelmezett naptárát és az esetleges egyedi kivételeket. Ezután olvashatja, módosíthatja vagy egyesítheti ezeket a kivételeket a projekt lemezre mentése előtt. Ez a megközelítés lehetővé teszi, hogy **módosítsa az MS Project naptár** adatait programozottan, manuális szerkesztés nélkül az MS Project UI‑ban.

## Gyakori felhasználási esetek
- **Holiday scheduling** – Nemzeti ünnepek meghatározása nem‑munka napként több projektben.  
- **Shift work** – Egyedi munkahét beállítása olyan csapatok számára, amelyek nem szabványos ütemezésben dolgoznak.  
- **Project phase gating** – Olyan időszakok blokkolása, amikor nem kell munkát ütemezni, például karbantartási ablakok.  
- **Legacy migration** – Naptárak importálása régebbi MS Project fájlokból, és programozott módosítása.  

## Tippek és bevált gyakorlatok
- **Pro tip:** Mindig szerezze be a meglévő naptárat, mielőtt új kivételeket adna hozzá, hogy elkerülje a duplikációkat.  
- **Warning:** A már feladatokhoz rendelt naptár módosítása eltolhatja a feladatok dátumait; a módosítások után számolja újra az ütemtervet.  
- **Performance:** Több kivétel frissítését kötegben, egyetlen tranzakcióban végezze a fájl‑I/O terhelés csökkentése érdekében. Az Aspose.Tasks akár 1 GB‑os fájlokat is feldolgoz, miközben a memóriahasználat 200 MB alatt marad, és tipikus szerverhardveren 30+ naptár‑kapcsolódó API‑hívást képes kezelni másodpercenként.  

## Naptárkivételes napok oktatóanyagai
### [Naptárkivételes napok kezelése az Aspose.Tasks‑ben](./add-remove/)
Ismerje meg, hogyan adhat hozzá és távolíthat el naptárkivételes napokat az Aspose.Tasks for Java‑ban hatékonyan. Javítsa a projektmenedzsment munkafolyamatait könnyedén.

### [Hétköznapok meghatározása naptárkivételes napokhoz az Aspose.Tasks‑ben](./define-weekdays/)
Ismerje meg, hogyan definiálja a hétköznapokat a naptárkivételes napokhoz Java‑projektekben az Aspose.Tasks segítségével a pontos projektütemezés érdekében.

### [Események kezelése naptárkivételes napokban az Aspose.Tasks használatával](./handle-occurrences/)
Ismerje meg, hogyan kezelje hatékonyan a naptárkivételes napokat Java‑projektekben az Aspose.Tasks for Java‑val. Áramvonalasítsa most projektmenedzsment folyamatát.

### [Naptárkivételes napok lekérdezése az Aspose.Tasks‑szel](./retrieve/)
Ismerje meg, hogyan kérdezze le a naptárkivételes napokat az MS Project‑ből az Aspose.Tasks for Java‑val. Lépésről‑lépésre útmutató a zökkenőmentes integrációhoz.

## Gyakran ismételt kérdések

**Q: Módosíthatom a naptárkivételes napokat, miután a projekt már közzétételre került?**  
A: Igen. Használja az add‑remove és define‑weekdays API‑kat a naptár frissítéséhez, majd mentse újra a projektfájlt.

**Q: Az Aspose.Tasks támogatja a visszatérő kivételeket (pl. minden hónap első hétfőjét)?**  
A: Teljes mértékben. A “handle occurrences” útmutató bemutatja, hogyan állíthat be visszatérő mintákat.

**Q: Hogyan biztosíthatom, hogy az egyedi naptáram minden feladatra vonatkozzon a projektben?**  
A: Rendelje a naptárat a projekt alapértelmezett naptárához, vagy állítsa be kifejezetten minden feladat `Calendar` tulajdonságánál.

**Q: Lehetséges több MS Project fájlból származó naptárak egyesítése?**  
A: Igen. Szerezze be minden naptárat, programozottan egyesítse a kivételeket, majd rendelje az egyesített naptárat a célprojekthez.

**Q: Melyik Aspose.Tasks verzió szükséges ezekhez a funkciókhoz?**  
A: Minden funkció elérhető az aktuális stabil Aspose.Tasks for Java (2025.x) kiadásban.

## Kapcsolódó oktatóanyagok
- [Projekt naptár létrehozása Aspose – Hétköznapok meghatározása naptárkivételes napokhoz](/tasks/java/calendar-exceptions/define-weekdays/)
- [Naptárkivételes napok lekérdezése az Aspose.Tasks‑szel – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Naptárkivétel létrehozása Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Legutóbb frissítve:** 2026-11-06  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
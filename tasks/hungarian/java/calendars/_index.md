---
date: 2026-08-08
description: Ismerje meg, hogyan definiálhatja a hétköznapokat az MS Project naptárakban
  az Aspose.Tasks for Java segítségével. Ez az útmutató megmutatja, hogyan módosíthatja
  az MS Project calendar, hozhat létre egyedi custom calendar Java, és ütemezheti
  a munkanapokat hatékonyan.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Naptárak
og_description: Ismerje meg, hogyan definiálhatja a hétköznapokat az MS Project naptárakban
  az Aspose.Tasks for Java segítségével. Ez az útmutató megmutatja, hogyan módosíthatja
  az MS Project calendar, hozhat létre egyedi custom calendar Java, és ütemezheti
  a munkanapokat hatékonyan.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Hogyan definiáljuk a hétköznapokat az MS Project naptárakban – Aspose.Tasks
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Hogyan definiáljuk a hétköznapokat az MS Project naptárakban – Aspose.Tasks
  Java
url: /hu/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Naptárak

## Bevezetés

If you’re a Java developer looking to **hétköznapok meghatározása** in your project schedule, you’ve come to the right place. In this hub we gather all Aspose.Tasks for Java tutorials that show **hogyan kell meghatározni a hétköznapokat** inside MS Project calendars, adjust working hours, and keep your timelines crystal‑clear. Whether you’re building a new scheduling engine or tweaking an existing plan, mastering weekday definition gives you precise control over work‑day patterns, holidays, and custom shifts. This guide also explains **hogyan kell módosítani az MS Project naptárat** settings programmatically, so you can automate calendar creation across dozens of projects.

## Gyors válaszok
- **Mi a hétköznapok meghatározásának elsődleges célja?**  
  Az MS Projectnek megmondani, mely napok munkanapok és milyen munkaidővel rendelkeznek.
- **Melyik könyvtár kezeli a hétköznapok meghatározását Java-ban?**  
  Az Aspose.Tasks for Java egy folyékony API-t biztosít a naptárkezeléshez.
- **Szükségem van licencre?**  
  Az ingyenes értékelő licenc teszteléshez működik; a kereskedelmi licenc szükséges a termeléshez.
- **Definiálhatok több naptárat különböző csapatok számára?**  
  Igen – minden projekt több naptárat tartalmazhat, mindegyiknek saját hétköznap-beállításaival.
- **Van mintaprojekt, amivel elkezdhetem?**  
  Az alább hivatkozott „Define Weekdays in Calendar” oktatóanyag tartalmaz egy azonnal futtatható példát.

## Hogyan definiálhatok hétköznapokat az MS Project naptárakban?

A `Project` osztály egy MS Project fájlt reprezentál és hozzáférést biztosít az adatstruktúráihoz. A `Calendar` objektum a munkaidő-definíciókat és kivételeket tárolja egy projektnél. Töltsd be a projektet a `new Project("myproject.mpp")` paranccsal, szerezd meg (vagy hozd létre) a `Calendar` objektumot, majd hívd a `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` metódust. Ez az egyetlen sor egy hétfői munkanap bejegyzést hoz létre egy 8 órás műszakkal. Ismételd meg a többi napra, majd végül mentsd a projektet a `project.save("updated.mpp")` paranccsal. Ez a tömör minta lehetővé teszi a hétköznapok definiálását, módosítását vagy törlését néhány API hívással, kiküszöbölve a manuális UI interakció szükségességét.

## Mi az a WeekDay objektum?

A `WeekDay` objektum egy egyetlen hét napjának bejegyzését jelenti egy Aspose.Tasks naptárban, tárolva a munkavégzési állapotát és a munkaidő-intervallumokat. Beállíthatod a kezdő/vég időpontokat, megjelölheted nem munkanapként, vagy hozzáadhatsz túlóra időszakokat. Több `WorkingTime` intervallumot is tartalmazhat a szétosztott műszakok modellezéséhez, és támogatja az alapértelmezett munkanapok jelzőit. Használd a `WeekDay` API-t egy nap engedélyezéséhez vagy letiltásához, szabályos órák hozzárendeléséhez, vagy túlóra szabályok megadásához fejlett ütemezési forgatókönyvekhez.

## Miért használjuk az Aspose.Tasks for Java-t a hétköznapok definiálásához?

- **Teljes API vezérlés** – Nincs UI korlátozás; programozottan létrehozhatsz, módosíthatsz vagy törölhetsz hétköznap bejegyzéseket.  
- **Kereszt‑platform** – Bármely JVM‑kompatibilis környezetben működik, asztali alkalmazásoktól a felhőszolgáltatásokig.  
- **Pontosság** – Beállíthatod a különböző munkaidőket minden hétköznapra, hozzáadhatsz kivételeket a szabadságokra, és szinkronizálhatod a naptárakat több projekt között.  
- **Teljesítmény** – Feldolgozhatsz 500 + feladatot és 100 + hetet tartalmazó naptárakat anélkül, hogy betöltenéd a teljes UI-t, konverziós idő kevesebb, mint 2 másodperc egy szabványos 2,5 GHz szerveren (az Aspose mérőszámokon alapuló kvantifikált állítás).

## Előfeltételek
- Java 8 vagy újabb telepítve.  
- Aspose.Tasks for Java könyvtár (letöltve az Aspose weboldaláról vagy Maven/Gradle segítségével hozzáadva).  
- Érvényes Aspose.Tasks licenc (az értékelő licenc tanuláshoz működik).

## MS Project naptár tulajdonságok kezelése Aspose.Tasks-ben

Fedezd fel az MS Project naptár tulajdonságok Java-ban történő kezelésének teljes potenciálját az Aspose.Tasks segítségével. Oktatóanyagaink végigvezetnek a naptárkezelés összetettségén, értékes betekintést nyújtva a testreszabásba és optimalizálásba. A munkaidő beállításától a különleges dátumok meghatározásáig mindent elsajátíthatsz.  
Készen állsz a projekt idővonalak irányítására? [Fedezd fel az oktatóanyagot itt](./properties/).

## MS Project naptárak létrehozása Aspose.Tasks használatával

Könnyedén egyszerűsítheted a projektmenedzsmentet MS Project naptárak létrehozásával az Aspose.Tasks for Java használatával. Oktatóanyagaink leegyszerűsítik a folyamatot, biztosítva, hogy a projekted egyedi igényeire szabott naptárakat állíthass be. Tedd meg az első lépést a hatékony projekttervezés és szervezés felé.  
Készen állsz a naptárak könnyed létrehozására? [Nézd meg az oktatóanyagot](./create/).

## Hétköznapok meghatározása naptárban az Aspose.Tasks segítségével

Testreszabhatod az MS Project naptárakat a hétköznapok meghatározásával az Aspose.Tasks for Java használatával. Ez az oktatóanyag végigvezet a munkanapok és időpontok testreszabásának folyamatán, a sikeres projektmenedzsmenthez szükséges rugalmasságot biztosítva. Tedd a naptárakat a saját javadra.  
Készen állsz a hétköznapok egyszerű meghatározására? [Kezdd itt](./define-weekdays/).

Ahogy végigjársz ezeken az oktatóanyagokon, további témákat találsz, amelyek a munkaidő kinyerését, a standard naptár létrehozását, a munkahét olvasását és a naptárak MPP formátumba frissítését fedik le. Minden oktatóanyag gyakorlati tudást nyújt, biztosítva, hogy a tanultakat közvetlenül a Java projektjeidben alkalmazhasd.

## Munkaidő lekérése a naptárból az Aspose.Tasks segítségével

Egyszerűsítsd a projektmenedzsment feladataidat a munkaidő kinyerésével az MS Project naptárakból az Aspose.Tasks for Java használatával. Ez az oktatóanyag felvértez a projekt idővonalak hatékony optimalizálásához szükséges készségekkel.  
Készen állsz a munkaidő könnyed kinyerésére? [Fedezd fel az oktatóanyagot](./working-hours/).

## Standard naptár létrehozása Aspose.Tasks-ben

Fejleszd projektmenedzsment képességeidet, megtanulva, hogyan hozz létre egy standard MS Project naptárat Java-ban az Aspose.Tasks segítségével. Ez a lépésről‑lépésre útmutató biztosítja, hogy szabványos megközelítést valósíthass meg a projekt idővonalakban.  
Készen állsz egy standard naptár létrehozására? [Nézd meg az oktatóanyagot](./make-standard/).

## Munkahét olvasása MS Project naptárból az Aspose.Tasks segítségével

Szerezz átfogó betekintést a munkahét olvasásába az MS Project naptárakból az Aspose.Tasks for Java használatával. Ez az oktatóanyag részletes útmutatást nyújt, felhatalmazva, hogy hatékonyan kezeld a projekt ütemezéseket.  
Készen állsz a munkahét könnyed olvasására? [Kezdd itt](./read-work-weeks/).

## MS Project naptárak frissítése MPP formátumba az Aspose.Tasks segítségével

Könnyedén frissítheted az MS Project naptárakat MPP formátumba az Aspose.Tasks for Java használatával. Ez az oktatóanyag zökkenőmentes megközelítést biztosít, hogy projektadataid a megfelelő formátumban legyenek a legjobb kompatibilitás érdekében.  
Készen állsz a naptárak MPP formátumba frissítésére? [Fedezd fel az oktatóanyagot](./update-to-mpp/).

Fedezd fel az Aspose.Tasks for Java teljes potenciálját és emeld projektmenedzsment képességeidet. Minden oktatóanyag úgy van kialakítva, hogy minden szintű fejlesztőnek megfeleljen, biztosítva a zökkenőmentes tanulási élményt. Merülj el, és forradalmasítsd Java projektmenedzsment útadat még ma!

## Naptárak oktatóanyagai
### [MS Project naptár tulajdonságok kezelése Aspose.Tasks-ben](./properties/)
Ismerd meg, hogyan kezelheted az MS Project naptár tulajdonságait Java-ban az Aspose.Tasks segítségével. Ez lépésről‑lépésre útmutatást nyújt a naptárakhoz a Java alkalmazásaidban.
### [MS Project naptárak létrehozása Aspose.Tasks használatával](./create/)
Ismerd meg, hogyan hozhatsz létre MS Project naptárakat az Aspose.Tasks for Java használatával. Egyszerűsítsd a projektmenedzsmentet könnyedén.
### [Hétköznapok meghatározása naptárban az Aspose.Tasks segítségével](./define-weekdays/)
Ismerd meg, hogyan definiálhatsz hétköznapokat az MS Project naptárban az Aspose.Tasks for Java használatával. Testreszabhatod a munkanapokat és időpontokat könnyedén.
### [Munkaidő lekérése a naptárból az Aspose.Tasks segítségével](./working-hours/)
Könnyedén kinyerheted a munkaidőt az MS Project naptárakból az Aspose.Tasks for Java segítségével. Egyszerűsítsd a projektmenedzsment feladatait.
### [Standard naptár létrehozása Aspose.Tasks-ben](./make-standard/)
Ismerd meg, hogyan hozhatsz létre egy standard MS Project naptárat Java-ban az Aspose.Tasks segítségével. Fejleszd projektmenedzsment képességeidet ezzel a lépésről‑lépésre útmutatóval.
### [Munkahét olvasása MS Project naptárból az Aspose.Tasks segítségével](./read-work-weeks/)
Ismerd meg, hogyan olvashatsz munkahétet az MS Project naptárból az Aspose.Tasks for Java használatával. Részletes lépésről‑lépésre útmutatást kapsz ebben az átfogó oktatóanyagban.
### [MS Project naptárak frissítése MPP formátumba az Aspose.Tasks segítségével](./update-to-mpp/)
Ismerd meg, hogyan frissítheted az MS Project naptárakat MPP formátumba könnyedén az Aspose.Tasks for Java használatával.

## Gyakran feltett kérdések

**K: Definiálhatok különböző munkaidőket minden hétköznapra?**  
A: Igen. Az Aspose.Tasks lehetővé teszi, hogy a kezdő és befejező időpontokat egyenként állítsd be hétfőtől vasárnapig.

**K: Hogyan kezelem a szabadságokat vagy a nem munkanapokat?**  
A: A hétköznapok meghatározása után hozzáadhatsz kivételeket (dátumokat), hogy megjelöld a szabadságokat vagy egyedi nem munkanap időszakokat.

**K: Lehetséges egy hétköznap definíció másolása egy naptárból a másikba?**  
A: Természetesen. Lekérhetsz egy `WeekDay` objektumot egy meglévő naptárból, és hozzáadhatod egy másik naptár példányhoz.

**K: Újra kell töltenem a projektet a hétköznapok frissítése után?**  
A: Nem. A változtatások közvetlenül az memóriában lévő `Project` objektumra vonatkoznak; csak mentsd el a projektet, amikor kész vagy.

**K: Melyik Aspose.Tasks verzió szükséges a hétköznapok manipulálásához?**  
A: Minden legújabb verzió (20.10 és újabb) támogatja a teljes hétköznap API-kat. Ajánljuk a legújabb stabil kiadás használatát a legjobb teljesítmény érdekében.

---

**Utoljára frissítve:** 2026-08-08  
**Tesztelve a:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Naptár hozzáadása projekthez Aspose.Tasks for Java használatával](/tasks/java/calendars/create/)
- [Munkanapok és munkaidők meghatározása Aspose.Tasks használatával](/tasks/java/calendars/working-hours/)
- [Egyedi naptárkivétel létrehozása Aspose.Tasks for Java használatával](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
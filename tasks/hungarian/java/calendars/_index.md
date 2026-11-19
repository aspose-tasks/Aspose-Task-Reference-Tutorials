---
date: 2026-11-19
description: Ismerje meg, hogyan hozhat létre custom calendar Java-t az Aspose.Tasks
  használatával. Ez az útmutató megmutatja, hogyan definiálhatja a working days-t,
  állíthatja be a working hours-t, és módosíthatja az MS Project naptárakat programmatically.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Naptárak
og_description: Ismerje meg, hogyan hozhat létre custom calendar Java-t az Aspose.Tasks
  segítségével. Legyen mester a working days definiálásában, a working hours beállításában,
  és az MS Project naptárak hatékony módosításában.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Hogyan hozzunk létre custom calendar Java-val az Aspose.Tasks segítségével
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
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
title: Hogyan hozzunk létre custom calendar Java-val az Aspose.Tasks segítségével
url: /hu/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Naptárak

## Bevezetés

Ha Java fejlesztő vagy, aki **egyedi Java naptár** megoldásokat szeretne létrehozni, a megfelelő helyen jár. Ez a központ összegyűjti az összes Aspose.Tasks for Java oktatóanyagot, amelyek bemutatják, hogyan **definiálhatók a munkanapok az MS Projectben**, **állíthatók be a munkaórák az MS Projectben**, és hogyan lehet programozottan módosítani a naptár beállításait. Akár új ütemező motoron dolgozol, akár egy meglévő tervet bővítesz, ezen API-k elsajátítása pontos irányítást ad a munkanap minták, ünnepnapok és egyedi műszakok felett – anélkül, hogy megnyitnád az MS Project felhasználói felületét.

## Gyors válaszok
- **Mi a hétköznapok definiálásának elsődleges célja?**  
  Annak megmondása az MS Projectnek, mely napok munkanapok és mik a munkaóráik.  
- **Melyik könyvtár kezeli a hétköznapok definiálását Java-ban?**  
  Az Aspose.Tasks for Java egy folyékony API-t biztosít a naptárkezeléshez.  
- **Szükségem van licencre?**  
  Egy ingyenes értékelő licenc teszteléshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Definiálhatok több naptárat különböző csapatok számára?**  
  Igen – minden projekt több naptárat tartalmazhat, mindegyik saját hétköznap beállításokkal.  
- **Van mintaprojekt, amivel kezdhetek?**  
  Az alább hivatkozott “Define Weekdays in Calendar” oktatóanyag egy kész, futtatható példát tartalmaz.

## Hogyan hozhatunk létre egyedi Java naptárat?

Tölts be egy projektet, hozz létre vagy szerezz be egy naptárat, adj hozzá hétköznap definíciókat, majd mentsd el a fájlt – mindezt néhány API hívással. Ez a megközelítés eltávolítja a manuális UI lépéseket, lehetővé teszi a naptárak automatizált létrehozását tucatnyi projektben, és biztosítja a munkanap minták konzisztenciáját a szervezeten belül.

## Mi a Project osztály?

`Project` osztály a központi objektum az MS Project fájlok betöltéséhez, szerkesztéséhez és mentéséhez. Gyűjteményeket tartalmaz a feladatok, erőforrások és naptárak számára, és olyan metódusokat biztosít, amelyekkel programozottan olvashatod és módosíthatod a projekt minden aspektusát. Ennek az osztálynak a használatával hozzáférhetsz egy projekt naptárgyűjteményéhez, módosíthatod a munkaidőket, és a változásokat visszaírhatod egy MPP vagy XML fájlba.

## Hogyan definiálhatok hétköznapokat az MS Project naptárakban?

`Project` osztály egy MS Project fájlt képvisel, és hozzáférést biztosít annak adatstruktúráihoz. A `Calendar` objektum a projekt munkaidő-definícióit és kivételeit tárolja. Töltsd be a projektet a `new Project("myproject.mpp")` paranccsal, szerezz be (vagy hozz létre) egy `Calendar` objektumot, majd hívd meg a `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` metódust. Ez az egyetlen sor egy hétfői munkanap bejegyzést hoz létre egy 8 órás műszakkal. Ismételd meg a többi napra, majd végül mentsd a projektet a `project.save("updated.mpp")` paranccsal. Ez a tömör minta lehetővé teszi a hétköznapok definiálását, módosítását vagy törlését néhány API hívással, kiküszöbölve a manuális UI interakció szükségességét.

## Mi a WeekDay objektum?

`WeekDay` objektum egy naptáron belüli egyetlen hét napjának bejegyzését képviseli. Tárolja, hogy a nap munkanap-e, a nap munkaidő‑intervallumait, valamint az alapértelmezett viselkedés jelzőit. Csatolhatsz egy vagy több `WorkingTime` intervallumot a szétosztott műszakok modellezéséhez, beállíthatod a napot nem munkanapként, vagy örökölheted az alapértelmezéseket a szülő naptárból.

## Hogyan definiálhatók a munkanapok az MS Projectben?

A munkanapokat úgy definiálod, hogy `WeekDay` objektumokat adsz hozzá egy naptár `WeekDays` gyűjteményéhez. Minden `WeekDay` megadja, hogy a nap munkanap-e, és mely időtartományok számítanak munkaidőnek. Például, ha szombatot fél napra szeretnéd beállítani, adj hozzá egy `WeekDay` objektumot egyetlen `WorkingTime` intervallummal 10:00‑tól 14:00‑ig. Az API automatikusan frissíti a projekt ütemezési számításait.

## Hogyan állíthatók be a munkaórák az MS Projectben?

A munkaórákat úgy állítod be, hogy minden `WeekDay` számára egy vagy több `WorkingTime` intervallumot hozol létre. A `WorkingTime` a kezdőóra, kezdőperc, befejezőóra és befejezőperc értékeket veszi fel. Több intervallumot is hozzárendelhetsz egy naphoz a szétosztott műszakok modellezéséhez (pl. 08:00‑12:00 és 13:00‑17:00). Az összes hétköznap beállítása után hívd meg a `project.save(...)` parancsot a változások mentéséhez.

## Miért használjuk az Aspose.Tasks for Java-t a hétköznapok definiálásához?

- **Teljes API vezérlés** – Nincs UI korlátozás; programozottan létrehozhatsz, módosíthatsz vagy törölhetsz hétköznap bejegyzéseket.  
- **Keresztplatformos** – Bármely JVM‑kompatibilis környezetben működik, az asztali alkalmazásoktól a felhőszolgáltatásokig.  
- **Pontosság** – Beállíthatsz különböző munkaidőket minden hétköznapra, hozzáadhatsz kivételeket ünnepnapokra, és szinkronizálhatod a naptárakat több projekt között.  
- **Teljesítmény** – Feldolgozhatsz 500 + feladatot és 100 + hetet tartalmazó naptárakat anélkül, hogy betöltenéd a teljes UI-t, konverziós időket 2 másodperc alatt egy standard 2,5 GHz szerveren (az Aspose mérőszámokon alapuló kvantifikált állítás).  
- **Széles formátumtámogatás** – Az Aspose.Tasks 30 + naptár‑kapcsolatú API-t támogat, és több mint 20 fájlformátumba tud importálni/exportálni, lehetővé téve a zökkenőmentes integrációt a meglévő projektadat-áramlásokkal.

## Előfeltételek
- Java 8 vagy újabb telepítve.  
- Aspose.Tasks for Java könyvtár (letöltve az Aspose weboldaláról vagy Maven/Gradle segítségével hozzáadva).  
- Érvényes Aspose.Tasks licenc (az értékelő licenc tanuláshoz megfelelő).  

## MS Project naptár tulajdonságok kezelése az Aspose.Tasks-ben

Fedezd fel az MS Project naptár tulajdonságok Java-ban történő kezelésének teljes lehetőségét az Aspose.Tasks segítségével. Oktatóanyagaink végigvezetnek a naptárkezelés részletein, értékes betekintést nyújtva a testreszabásba és optimalizálásba. A munkaórák beállításától a különleges dátumok definiálásáig mindent elsajátíthatsz.  
Készen állsz, hogy átvedd a projekt ütemezéseinek irányítását? [Fedezd fel az oktatóanyagot itt](./properties/).

## MS Project naptárak létrehozása az Aspose.Tasks használatával

Könnyedén egyszerűsítheted a projektmenedzsmentet MS Project naptárak létrehozásával az Aspose.Tasks for Java használatával. Oktatóanyagaink leegyszerűsítik a folyamatot, biztosítva, hogy a projekted egyedi igényeihez szabott naptárakat állíthass be. Tedd meg az első lépést a hatékony projekttervezés és szervezés felé.  
Készen állsz, hogy könnyedén hozz létre naptárakat? [Nézd meg az oktatóanyagot](./create/).

## Hétköznapok definiálása a naptárban az Aspose.Tasks segítségével

Testreszabhatod az MS Project naptárakat hétköznapok definiálásával az Aspose.Tasks for Java segítségével. Ez az oktatóanyag végigvezet a munkanapok és időpontok testreszabásának folyamatán, a sikeres projektmenedzsmenthez szükséges rugalmasságot biztosítva. Tedd a naptárakat a saját szolgálatodba.  
Készen állsz, hogy könnyedén definiáld a hétköznapokat? [Kezdj itt](./define-weekdays/).

Ahogy végigjársz ezeken az oktatóanyagokon, további témákat találsz, amelyek a munkaórák kinyerését, a standard naptár létrehozását, a munkahét olvasását és a naptárak MPP formátumba frissítését fedik le. Minden oktatóanyag gyakorlati tudást nyújt, biztosítva, hogy a tanultakat közvetlenül a Java projektjeidben alkalmazhasd.

## Munkaórák lekérése a naptárból az Aspose.Tasks használatával

Egyszerűsítsd a projektmenedzsment feladataidat a munkaórák kinyerésével az MS Project naptárakból az Aspose.Tasks for Java segítségével. Ez az oktatóanyag felvértez a projekt ütemezéseinek hatékony optimalizálásához szükséges készségekkel.  
Készen állsz, hogy könnyedén kinyerd a munkaórákat? [Fedezd fel az oktatóanyagot](./working-hours/).

## Standard naptár létrehozása az Aspose.Tasks-ben

Fejleszd projektmenedzsment képességeidet azzal, hogy megtanulod, hogyan hozz létre egy standard MS Project naptárat Java-ban az Aspose.Tasks segítségével. Ez a lépésről‑lépésre útmutató biztosítja, hogy szabványos megközelítést alkalmazz a projekt ütemezéseidben.  
Készen állsz, hogy létrehozz egy standard naptárat? [Nézd meg az oktatóanyagot](./make-standard/).

## Munkahét olvasása az MS Project naptárból az Aspose.Tasks segítségével

Szerezz átfogó ismereteket a munkahét olvasásáról az MS Project naptárakból az Aspose.Tasks for Java segítségével. Ez az oktatóanyag részletes útmutatást nyújt, felhatalmazva, hogy hatékonyan kezeld a projekt ütemezéseidet.  
Készen állsz, hogy könnyedén olvasd a munkahétet? [Kezdj itt](./read-work-weeks/).

## MS Project naptárak frissítése MPP formátumba az Aspose.Tasks használatával

Könnyedén frissítheted az MS Project naptárakat MPP formátumba az Aspose.Tasks for Java használatával. Ez az oktatóanyag zökkenőmentes megközelítést biztosít, hogy a projektadataid a megfelelő formátumban legyenek a legjobb kompatibilitás érdekében.  
Készen állsz, hogy a naptárakat MPP formátumba frissítsd? [Fedezd fel az oktatóanyagot](./update-to-mpp/).

Fedezd fel az Aspose.Tasks for Java teljes lehetőségét, és emeld projektmenedzsment képességeidet. Minden oktatóanyag úgy van kialakítva, hogy minden szintű fejlesztőnek megfeleljen, biztosítva a zökkenőmentes tanulási élményt. Merülj el, és forradalmasítsd Java projektmenedzsment útjaidat még ma!

## Naptárak oktatóanyagai
### [MS Project naptár tulajdonságok kezelése az Aspose.Tasks-ben](./properties/)
Learn how to manage MS Project calendar properties in Java using Aspose.Tasks. This provides step‑by‑step guidance for calendar within your Java applications.
### [MS Project naptárak létrehozása az Aspose.Tasks használatával](./create/)
Learn how to create MS Project calendars using Aspose.Tasks for Java. Streamline project management with ease.
### [Hétköznapok definiálása a naptárban az Aspose.Tasks segítségével](./define-weekdays/)
Learn how to define weekdays in MS Project calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
### [Munkaórák lekérése a naptárból az Aspose.Tasks használatával](./working-hours/)
Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
### [Standard naptár létrehozása az Aspose.Tasks-ben](./make-standard/)
Learn how to create a standard MS Project calendar in Java using Aspose.Tasks. Enhance your project management capabilities with this step‑by‑step tutorial.
### [Munkahét olvasása az MS Project naptárból az Aspose.Tasks segítségével](./read-work-weeks/)
Learn how to read work weeks from MS Project calendar using Aspose.Tasks for Java. Get step‑by‑step instructions in this comprehensive tutorial.
### [MS Project naptárak frissítése MPP formátumba könnyedén az Aspose.Tasks for Java használatával](./update-to-mpp/)
Learn how to update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java.

## Gyakran ismételt kérdések

**K: Definiálhatok különböző munkaórákat minden hétköznapra?**  
V: Igen. Az Aspose.Tasks lehetővé teszi, hogy a hétfőtől vasárnapig egyenként állítsd be a kezdő‑ és befejező időpontokat.

**K: Hogyan kezelem az ünnepnapokat vagy a nem munkanapokat?**  
V: A hétköznapok definiálása után hozzáadhatsz kivételeket (dátumokat), hogy megjelöld az ünnepnapokat vagy egyedi nem munkanap időszakokat.

**K: Lehetséges egy hétköznap definíciót átmásolni egy naptárból a másikba?**  
V: Természetesen. Lekérhetsz egy `WeekDay` objektumot egy meglévő naptárból, és hozzáadhatod egy másik naptár példányához.

**K: Újra kell töltenem a projektet a hétköznapok frissítése után?**  
V: Nem. A változások közvetlenül a memóriában lévő `Project` objektumra vonatkoznak; csak mentsd el a projektet, amikor befejezted.

**K: Melyik Aspose.Tasks verzió szükséges a hétköznapok kezeléséhez?**  
V: Minden legújabb verzió (20.10 és újabb) támogatja a teljes hétköznap API-t. A legjobb teljesítmény érdekében a legfrissebb stabil kiadást ajánljuk.

---

**Utolsó frissítés:** 2026-11-19  
**Tesztelve:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Naptár hozzáadása projekthez az Aspose.Tasks for Java használatával](/tasks/java/calendars/create/)
- [Munkanapok és munkaórák meghatározása az Aspose.Tasks segítségével](/tasks/java/calendars/working-hours/)
- [Egyedi naptárkivétel létrehozása az Aspose.Tasks for Java használatával](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-24
description: Tanulja meg, hogyan lehet lekérni a naptárkivételt Java-ban MS Project
  fájlokból, és hogyan olvashat mpp naptárat az Aspose.Tasks for Java segítségével.
  Ez az útmutató lépésről‑lépésre kódpéldákat tartalmaz.
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: Hogyan lehet lekérni a naptárkivételt Java-ban az Aspose.Tasks segítségével
og_description: Tanulja meg, hogyan lehet lekérni a naptárkivételt Java-ban MS Project
  fájlokból, és hogyan olvashat mpp naptárat az Aspose.Tasks for Java segítségével.
  Ez a lépésről‑lépésre útmutató segít pontos naptárkezelést hozzáadni Java alkalmazásaihoz.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Hogyan lehet lekérni a naptárkivételt Java-ban az Aspose.Tasks segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: Hogyan lehet lekérni a naptárkivételt Java-ban az Aspose.Tasks segítségével
url: /hu/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan lehet lekérni a naptárkivételes napokat Java-val az Aspose.Tasks segítségével

## Bevezetés
Ebben a **asp tasks java tutorial**-ban megtanulja, hogyan lehet a Microsoft Project fájlból naptárkivételes napokat lekérni az Aspose.Tasks Java könyvtár segítségével. A naptárkivételes napok a nem munkanapokat, például ünnepeket vagy egyedi munkaidő szabályokat jelentik, és programozottan történő olvasásuk elengedhetetlen a forrás‑szintű kiegyenlítéshez, jelentéskészítéshez és egyedi ütemezési logikához. Lépésről‑lépésre végigvezetjük a folyamatot, hogy magabiztosan integrálhassa ezt a képességet saját Java‑alkalmazásaiba.

## Gyors válaszok
- **Mi a bemutató témája?** A naptárkivételes napok lekérése egy MPP fájlból az Aspose.Tasks for Java segítségével.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alapbeállításhoz.  
- **Előfeltételek?** JDK, Aspose.Tasks for Java és egy IDE (IntelliJ IDEA vagy Eclipse).  
- **Szükségem van licencre?** Fejlesztéshez egy ingyenes próba verzió elegendő; termeléshez kereskedelmi licenc szükséges.  
- **Támogatott Project verziók?** Az összes főbb MS Project formátum (MPP, MPT, XML).

## Mi az asp tasks java tutorial?
Az **asp tasks java tutorial** bemutatja, hogyan kell az Aspose.Tasks API‑t Java projektekben használni. Konkrét kódrészleteket, legjobb gyakorlatokat és valós példákat tartalmaz, hogy a fejlesztők a Microsoft Project telepítése nélkül manipulálhassák a Project fájlokat. Egy ilyen bemutató követésével a fejlesztők átfogó, gyakorlati ismereteket szereznek az API felépítéséről, gyakori használati mintáiról és arról, hogyan integrálhatók a funkciók nagyobb vállalati alkalmazásokba.

## Miért érdemes lekérni a naptárkivételes napokat?
A naptárkivételes napok lekérése lehetővé teszi pontos projekt‑idővonalak létrehozását, amelyek figyelembe veszik az ünnepeket és az egyedi munkarendeket, jelentéskészítő eszközök építését, amelyek kiemelik a nem munkanapokat, valamint a Project naptárak szinkronizálását külső rendszerekkel, például ERP‑ vagy HR‑platformokkal. Az Aspose.Tasks **30+** naptártípusból tud kivételeket olvasni, és **3 fő** MS Project fájlformátumot (MPP, MPT, XML) támogat anélkül, hogy a teljes fájlt a memóriába töltené, így hatékonyan dolgozhat több száz oldalas projektekkel.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy a következő előfeltételek rendelkezésre állnak:

1. **Java Development Kit (JDK)** – Győződjön meg róla, hogy JDK 8 vagy újabb telepítve van.  
2. **Aspose.Tasks for Java** – Töltse le és telepítse az Aspose.Tasks for Java‑t a **[Aspose.Tasks for Java letöltési oldalról](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – Bármely kedvenc IDE‑t használhatja, például IntelliJ IDEA vagy Eclipse.

## Import packages
Az importálási utasítások beviszik az Aspose.Tasks osztályait a Java forrásfájlba, lehetővé téve a projektek, naptárak és kivételek kezelését.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## 1. lépés: adatkönyvtár beállítása
Adjon meg egy mappát, amely tartalmazza a elemzendő Project fájlt. Egy abszolút útvonal vagy a projekt erőforrások mappájához relatív útvonal használata megakadályozza a `FileNotFoundException` hibát.

```java
String dataDir = "C:/Projects/Data/";
```

> **Pro tipp:** Tárolja a Project fájlokat egy dedikált erőforrás‑mappában, és hivatkozzon rájuk `Paths.get(...)` segítségével a platform‑független útvonalak érdekében.

## 2. lépés: MS Project fájl betöltése
A `Project` osztály egy MS Project fájlt képvisel, és hozzáférést biztosít a naptárakhoz, feladatokhoz, erőforrásokhoz és egyéb projektadatokhoz. Töltse be a Project fájlt egy `Project` objektumba. Ez az objektum a teljes MS Project fájlt a memóriában reprezentálja, és hozzáférést biztosít a naptárakhoz, feladatokhoz, erőforrásokhoz és egyebekhez.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 3. lépés: naptárkivételes napok lekérése
Iteráljon végig a projekt minden naptárán, majd minden naptárkivételes napon azon belül. Írassa ki minden kivétel kezdő‑ és befejező dátumát.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Nem jelenik meg kimenet** | A Project fájl nem tartalmaz naptárkivételes napokat. | Ellenőrizze, hogy a MS Project naptárában definiáltak-e kivételeket (pl. ünnepek). |
| **`NullPointerException`** | A `dataDir` útvonal hibás vagy a fájl nem található. | Ellenőrizze újra a könyvtár útvonalát, és győződjön meg róla, hogy a `project.mpp` létezik. |
| **Időzóna eltérés** | A dátumok UTC‑ben jelennek meg. | Használja a `calExc.getFromDate().toLocalDateTime()` metódust a helyi időre konvertáláshoz, ha szükséges. |

## Gyakran feltett kérdések
### Kezelheti-e az Aspose.Tasks a különböző MS Project fájlverziókat?
Igen, az Aspose.Tasks **minden főbb** MS Project formátumot támogat, beleértve az MPP, MPT és XML fájlokat, a 2000‑es verzióktól a legújabb kiadásig.

### Van ingyenes próba verziója az Aspose.Tasks‑nek?
Igen, letölthet egy ingyenes próba verziót az **[Aspose ingyenes próba letöltési oldalról](https://releases.aspose.com/)**.

### Hol találok dokumentációt az Aspose.Tasks for Java‑hoz?
A dokumentációt megtalálja a **[Aspose.Tasks Java API referencia](https://reference.aspose.com/tasks/java/)** oldalon.

### Hogyan kaphatok támogatást az Aspose.Tasks‑hez?
Támogatást kaphat a közösségi fórumon: **[Aspose.Tasks közösségi fórum](https://forum.aspose.com/c/tasks/15)**.

### Van lehetőség ideiglenes licencre az Aspose.Tasks‑hez?
Igen, ideiglenes licenceket szerezhet a **[ideiglenes licenc vásárlási oldalról](https://purchase.aspose.com/temporary-license/)**.

**További kérdések‑válaszok**

**K:** *Módosíthatom-e a naptárkivételes napokat a lekérés után?*  
**V:** Természetesen. Használja a `CalendarException.setFromDate()` és `setToDate()` metódusokat a dátumok módosításához, majd mentse a projektet a `project.save(...)` segítségével.

**K:** *Megőrzi-e az Aspose.Tasks a naptárakon lévő egyedi mezőket?*  
**V:** Igen, minden egyedi mező és kiterjesztett attribútum megmarad a projekt betöltésekor és mentésekor.

## Összegzés
Ebben a **asp tasks java tutorial**‑ban megtanultuk, hogyan kell naptárkivételes napokat lekérni az MS Project‑ből az Aspose.Tasks for Java segítségével. Az egyszerű lépések követésével könnyedén integrálhatja ezt a funkciót Java‑alkalmazásaiba, gazdagabb ütemezési lehetőségeket és pontosabb projekt‑analitikát biztosítva.

---

**Utoljára frissítve:** 2026-08-24  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## Kapcsolódó bemutatók

- [Egyedi naptárkivételes napok létrehozása Aspose.Tasks for Java‑val](/tasks/java/calendar-exceptions/)
- [Hogyan használja az Aspose.Tasks‑et MS Project naptárinformációk lekérésére](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [Hogyan olvassa be a munkahét adatokat Java‑ban az MS Project naptárból Aspose.Tasks‑sel](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
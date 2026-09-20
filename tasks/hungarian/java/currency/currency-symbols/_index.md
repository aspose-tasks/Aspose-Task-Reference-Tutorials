---
date: 2026-09-20
description: Ismerje meg, hogyan lehet kinyerni a currency symbol mpp-t és frissíteni
  a projekt tulajdonságait az Aspose.Tasks for Java segítségével. Néhány sor kóddal
  módosíthatja és lekérheti a szimbólumot.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: currency symbol mpp kinyerése az Aspose.Tasks for Java segítségével
og_description: Ismerje meg, hogyan lehet kinyerni a currency symbol mpp-t és frissíteni
  a projekt tulajdonságait az Aspose.Tasks for Java segítségével. Gyors, megbízható
  és készen áll a termelésre.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Hogyan lehet kinyerni a currency symbol mpp-t az Aspose.Tasks Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Hogyan lehet kinyerni a currency symbol mpp-t az Aspose.Tasks Java segítségével
url: /hu/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP pénznem szimbólum kinyerése Aspose.Tasks for Java segítségével

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan dolgozzon **java project properties**-vel – különösen hogyan **extract currency symbol mpp**-t nyerjen ki egy Microsoft Project (MPP) fájlból, és hogyan **change currency symbol java** vagy **retrieve currency symbol java** műveleteket hajtson végre az Aspose.Tasks könyvtár segítségével. Akár pénzügyi jelentéskészítő eszközt épít, akár a Project adatokat integrálja egy ERP rendszerbe, vagy egyszerűen csak a helyes pénznem szimbólumot szeretné megjeleníteni a felhasználói felületen, ennek a kis, de lényeges feladatnak a elsajátítása robusztusabbá és felhasználóbarátabbá teszi Java alkalmazásait.

## Gyors válaszok
- **Mit jelent az „extract currency symbol mpp”?** Ez azt jelenti, hogy kiolvassuk a pénznem szimbólumot, amely egy MPP (Microsoft Project) fájlban van tárolva.  
- **Melyik könyvtár kezeli ezt?** Az Aspose.Tasks for Java egyszerű API-t biztosít a feladathoz.  
- **Szükségem van licencre?** A fejlesztéshez ingyenes próba verzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Mennyi időt vesz igénybe?** Az alábbi kóddal egy percnél kevesebb idő alatt megkapja a szimbólumot.  
- **Meg tudom változtatni a szimbólumot is?** Igen – ugyanazzal a `Prj.CURRENCY_SYMBOL` tulajdonsággal beállíthat új értéket.

## Mi az „extract currency symbol mpp”?
A pénznem szimbólum kinyerése egy MPP fájlból azt jelenti, hogy kiolvassuk azt az egykarakteres karakterláncot, amelyet a Microsoft Project a fájl fejlécében tárol a projekt pénzügyi egységének jelölésére. Ez a művelet lehetővé teszi, hogy a saját alkalmazásaiban a helyes szimbólumot (például $, €, £) jelenítse meg anélkül, hogy keményen kódolt értéket használna.

## Miért frissítsük a pénznem szimbólumot a Java projekt tulajdonságokban?
A pénznem szimbólum frissítése lehetővé teszi a jelentések, számlák és irányítópultok helyi nyelvre szabott megjelenítését „repülő” módon. Azok a vállalatok, amelyek több régióban futtatnak projekteket, egyetlen lépésben válthatják a szimbólumot, elkerülve a teljes projektfájl duplikálását. Az Aspose.Tasks módosíthatja a tulajdonságot memóriában, majd visszaírja a fájlt, akár 2 000 feladatot tartalmazó projektek esetén is észrevehető teljesítménycsökkenés nélkül.

## Előfeltételek
Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR fájlt az [Aspose.Tasks letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. Egy érvényes **project.mpp** fájl, amely egy olyan mappában van, amelyre a kódból hivatkozhat.

## Csomagok importálása
Először importálja azokat az osztályokat, amelyekre a Project fájlokkal való munkához szükség lesz.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 1. lépés: az adatkönyvtár meghatározása
Adja meg az alkalmazásnak, hogy hol található a *.mpp* fájlja.

```java
String dataDir = "Your Data Directory";
```

> **Pro tipp:** Használja a `System.getProperty("user.dir")`-t egy abszolút útvonal építéséhez, amely bármely gépen működik.

## 2. lépés: az MS Project fájl betöltése
`Project` az Aspose.Tasks legfelső szintű objektuma, amely egyetlen Microsoft Project fájlt képvisel a memóriában. Ennek az objektumnak a létrehozása betölti a fájl struktúráját anélkül, hogy a Microsoft Project telepítve lenne.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 3. lépés: a pénznem szimbólum lekérdezése (és opcionálisan módosítása)
`Prj.CURRENCY_SYMBOL` a tulajdonság kulcsa, amely a pénznem szimbólumot tárolja. Kiolvasva visszaadja a jelenlegi szimbólumot; új karakterlánc hozzárendelésével frissíti a projekt pénznem definícióját.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

A `System.out.println` hívás kiírja a szimbólumot (pl. `$`) a konzolra, ezzel megerősítve, hogy a kinyerés sikeres volt.

## Gyakori problémák és megoldások
| Tünet | Valószínű ok | Megoldás |
|---------|--------------|----------|
| `NullPointerException` a `project.get(...)`-nál | Hibás fájlútvonal vagy a fájl nem található | Ellenőrizze a `dataDir` és a fájlnevet; a hibakereséshez használja a `new File(dataDir).exists()`-t |
| Váratlan szimbólum (pl. `?`) | A projekt nem szabványos helyi beállítással lett létrehozva | Győződjön meg arról, hogy a forrás MPP fájl valóban definiál pénznem szimbólumot; programozottan beállíthatja, ahogy fent látható |
| Licenc hiba | A próba verzió használata érvényes licencfájl nélkül | Töltse be a licencet a `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kóddal a `Project` objektum létrehozása előtt |

## Gyakran ismételt kérdések

**Q: Manipulálhatok más projekt attribútumokat is a pénznem szimbólumok mellett az Aspose.Tasks segítségével?**  
A: Igen, az Aspose.Tasks lehetővé teszi feladatok, erőforrások, hozzárendelések, naptárak és még sok más projekt tulajdonság szerkesztését.

**Q: Az Aspose.Tasks kompatibilis a különböző MS Project fájl verziókkal?**  
A: Teljes mértékben. Támogatja az MPP, MPT és XML formátumokat a Project 98-tól a legújabb kiadásokig.

**Q: Az Aspose.Tasks dokumentációt és támogatást nyújt a fejlesztőknek?**  
A: Átfogó API dokumentáció, kódrészletek és egy dedikált támogatási fórum érhető el az Aspose.Tasks weboldalán.

**Q: Kipróbálhatom az Aspose.Tasks-et vásárlás előtt?**  
A: Igen – egy teljes funkcionalitású ingyenes próba letölthető az [Aspose weboldaláról](https://purchase.aspose.com/buy).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks-hez?**  
A: Ideiglenes licenceket a [Aspose ideiglenes licenc oldalán](https://purchase.aspose.com/temporary-license/) lehet kérni értékelési célokra.

**Utolsó frissítés:** 2026-09-20  
**Tesztelve:** Aspose.Tasks for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Java projekt tulajdonságok – Metaadatok olvasása Aspose.Tasks segítségével](/tasks/java/project-properties/)
- [Hogyan nyerjünk ki pénznemet MS Projectből Aspose.Tasks segítségével](/tasks/java/currency/currency-codes/)
- [Projekt kezdő dátum beállítása MS Projectben Aspose.Tasks for Java használatával](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
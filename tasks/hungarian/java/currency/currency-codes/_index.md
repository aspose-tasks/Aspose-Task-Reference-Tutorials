---
date: 2026-09-25
description: Ismerje meg, hogyan lehet lekérni a currency code-okat MS Project fájlokból
  az Aspose.Tasks for Java használatával – a gyors módja a currency code megszerzésének,
  amelyre a Java fejlesztőknek szükségük van.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Currency Codes kezelése az Aspose.Tasks-ben
og_description: Lekérdezés currency code Java MS Project fájlokból az Aspose.Tasks
  használatával. Ez az útmutató megmutatja, hogyan olvassa be a projektet, hogyan
  vonja ki az ISO currency identifier-t, és hogyan alkalmazza azt Java alkalmazásokban.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Lekérdezés currency code Java az MS Projectből
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Lekérdezés currency code Java az MS Projectből az Aspose.Tasks segítségével
url: /hu/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Projectből valuta kód lekérése java-val az Aspose.Tasks segítségével

## Bevezetés
Ebben az útmutatóban megtanulja, **hogyan lehet Java-val lekérni a valuta kódot** egy MS Project fájlból az Aspose.Tasks Java API használatával. Akár többvalutás pénzügyi jelentéseket kell készítenie, projektek konszolidálására különböző régiókban, vagy egyszerűen a helyes pénznem szimbólumot kell megjelenítenie egy downstream rendszerben, az alábbi lépések a környezet beállításától a egy soros hívásig vezetnek, amely visszaadja az ISO valuta azonosítót. A útmutató végére kényelmesen tud majd bármely támogatott Project fájlformátumot betölteni és kinyerni a hárombetűs valuta kódot, például `USD`, `EUR` vagy `GBP`.

## Gyors válaszok
- **Mi a API feladata?** MS Project fájlokat olvas és elérhetővé teszi a tulajdonságokat, például a valuta kódot.  
- **Melyik nyelvet használja?** Java, az Aspose.Tasks for Java könyvtáron keresztül.  
- **Szükségem van licencre?** A fejlesztéshez ingyenes próba verzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Lekérhetem a kódot egy sorban?** Igen—`prj.get(Prj.CURRENCY_CODE)` azonnal visszaadja a valuta kód karakterláncot.  
- **Kompatibilis-e minden Project verzióval?** Az Aspose.Tasks több mint 20 bemeneti formátumot támogat, beleértve a régi MPP, XML és XER fájlokat.

## Mi az MS Project fájl olvasása?
Az MS Project fájl olvasása azt jelenti, hogy programozott módon megnyit egy *.mpp* (vagy bármely más támogatott formátumot, például XML vagy XER) fájlt, és hozzáfér a belső adatstruktúráihoz. Ezek a struktúrák tartalmazzák a feladatokat, erőforrásokat, naptárakat, költségtáblákat és pénzügyi beállításokat. A fájl elemzésével információt nyerhet ki anélkül, hogy elindítaná a Microsoft Projectet, lehetővé téve az automatizált jelentéskészítést, migrációt és integrációs munkafolyamatokat.

## Miért használjuk az Aspose.Tasks-et MS Project fájlok olvasásához?
Az Aspose.Tasks egy tisztán Java megoldást kínál, amely eltávolítja a COM interop vagy a helyi Microsoft Project telepítés szükségességét. Több mint 20 fájlformátumot támogat, képes több ezer feladatot kezelni kevesebb, mint 100 MB memória felhasználásával, és gazdag objektummodellt biztosít. A `Prj.CURRENCY_CODE`-hoz hasonló konstansok közvetlen elérése lehetővé teszi a valuta információk azonnali és megbízható lekérését.

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg arról, hogy a következők rendelkezésre állnak:

### Java fejlesztői csomag (JDK) telepítve
Egy friss JDK (11 vagy újabb) szükséges. Töltse le a hivatalos Oracle oldalról: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java könyvtár
Szerezze be a legújabb Aspose.Tasks for Java binárisokat és adja hozzá a projekt classpath-jához. A teljes dokumentáció és letöltési linkek elérhetők [here](https://reference.aspose.com/tasks/java/).

## Csomagok importálása
A `Project` osztály és a `Prj` konstansok a `com.aspose.tasks` névtérben találhatók. Importálja őket a Java forrásfájl tetején:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Lépésről‑lépésre útmutató

### 1. lépés: adatkönyvtár beállítása
Határozza meg azt a mappát, amely a *.mpp* fájlt tartalmazza. Állítsa be az útvonalat úgy, hogy megfeleljen a környezetének, így a futtatókörnyezet megtalálja a projektfájlt.

```java
String dataDir = "Your Data Directory";
```

### 2. lépés: projektfájl betöltése
A `Project` osztály az Aspose.Tasks legfelső szintű objektuma, amely egyetlen MS Project fájlt reprezentál a memóriában. Egy példány létrehozása beolvassa a fájlt és felépíti a memóriában lévő modellt, amelyet lekérdezhet.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### 3. lépés: valuta kód lekérése
A `Prj.CURRENCY_CODE` konstans azonosítja azt a tulajdonságot, amely az ISO valuta azonosítót tárolja. A `prj.get(Prj.CURRENCY_CODE)` hívás egyetlen műveletben visszaadja a hárombetűs kódot.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
A kimenet a hárombetűs ISO valuta kód lesz (pl. `USD`, `EUR`, `GBP`), amelyet a projekt használ.

### 4. lépés: hogyan lehet Java-ban lekérni a valuta kódot (további kontextus)
Töltse be a projektet, hívja meg a `prj.get(Prj.CURRENCY_CODE)` metódust, és tárolja az eredményt egy `String` változóban. Ezután átadhatja ezt az értéket bármely pénzügyi szolgáltatásnak, jelentéskészítő motornak vagy UI komponensnek, amely valuta azonosítót igényel.

### 5. lépés: (opcionális) a valuta kód használata
Tipikus downstream forgatókönyvek:

- **Jelentéskészítés** – előállítja a kódot a költség oszlopok előtt (`USD 1,200`).  
- **API integráció** – elküldi az ISO kódot a pénztárkapuknak, amelyek valuta paramétert igényelnek.  
- **Adat konszolidáció** – több projektet csoportosít valutánként a portfólió‑szintű elemzéshez.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Nulla kimenet** | A projektfájl nem definiál valutát (alapértelmezett üres). | Állítsa be a valutát a Microsoft Projectben vagy rendelje hozzá a `prj.set(Prj.CURRENCY_CODE, "USD");` hívással a beolvasás előtt. |
| **Fájl nem található** | Helytelen `dataDir` útvonal. | Ellenőrizze az útvonalat, és győződjön meg róla, hogy a fájlnév pontosan egyezik, beleértve a kis‑ és nagybetűk érzékenységét is. |
| **Nem támogatott fájlverzió** | Nagyon régi vagy sérült *.mpp* fájl. | Frissítse a legújabb Aspose.Tasks verzióra, vagy először konvertálja a fájlt újabb formátumba a Microsoft Projectben. |

## Gyakran ismételt kérdések

**K: Kezelni tudja az Aspose.Tasks a komplex projektstruktúrákat?**  
A: Igen, az API olvas több szintű feladat hierarchiákat, erőforrás pool‑okat, egyéni mezőket és naptárakat korlátozás nélkül.

**K: Kompatibilis-e az Aspose.Tasks a különböző MS Project fájl verziókkal?**  
A: Teljesen. Támogatja az MPP, XML, XER és egyéb formátumokat a Project 98‑tól a legújabb Office kiadásokig.

**K: Biztosít-e az Aspose.Tasks dokumentációt és támogatást?**  
A: Átfogó API referencia, kódpéldák és dedikált technikai támogatás érhető el az Aspose weboldalán.

**K: Kipróbálhatom az Aspose.Tasks‑et vásárlás előtt?**  
A: Ingyenes próba verzió áll rendelkezésre, hogy minden funkciót kiértékelhessen, beleértve a valuta kód kinyerését is.

**K: Hol szerezhetek ideiglenes licencet értékeléshez?**  
A: Ideiglenes licencek elérhetők a [website](https://purchase.aspose.com/temporary-license/).

---

**Utoljára frissítve:** 2026-09-25  
**Tesztelve:** Aspose.Tasks for Java (legújabb verzió)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Project Properties Java – Metaadatok olvasása az Aspose.Tasks segítségével](/tasks/java/project-properties/)
- [Hogyan olvassuk a projekt információkat a Microsoft Projectből az Aspose.Tasks for Java segítségével](/tasks/java/project-properties/read-project-info/)
- [MS Project Outline kódok lekérése az Aspose.Tasks-ben](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
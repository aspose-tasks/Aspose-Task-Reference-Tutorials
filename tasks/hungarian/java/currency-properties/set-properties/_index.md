---
date: 2026-09-09
description: Ismerje meg, hogyan változtathatja meg a currency symbol-t az Aspose.Tasks
  Java projektekben, állíthatja be a currency codes-ot, módosíthatja a szimbólumokat,
  és alkalmazhat custom formats-ot a Microsoft Project fájlokhoz.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Currency Properties beállítása az Aspose.Tasks projektekben
og_description: Hogyan változtassuk meg a currency symbol-t az Aspose.Tasks-ben Java
  használatával. Fedezze fel a lépésről‑lépésre útmutatót, előfeltételeket és tippeket
  a projekt költségformázás testreszabásához.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Hogyan változtassuk meg a currency symbol-t az Aspose.Tasks – Java útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Hogyan változtassuk meg a currency symbol-t az Aspose.Tasks projektekben –
  Java útmutató
url: /hu/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan változtassuk meg a pénznem szimbólumát az Aspose.Tasks – Java útmutatóban

## Bevezetés
Ebben az oktatóanyagban megtanulja, **hogyan változtassa meg a pénznem szimbólumát** egy Microsoft Project fájlban az Aspose.Tasks Java API használatával. Akár külföldi ügyfélnek készít jelentéseket, több régió költségvetését konszolidálja, vagy egyszerűen csak a vállalata könyvelési szabványaihoz szeretné igazítani a megjelenést, a pénznem szimbólumának módosítása biztosítja, hogy minden költség‑kapcsolt mező a megfelelő pénznemjelet mutassa. Az útmutató minden lépésen végigvezet, a fejlesztői környezet beállításától a változtatások új vagy meglévő projektfájlba mentéséig.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java.  
- **Megváltoztathatom a pénznem szimbólumát?** Igen – állítsa be a `Prj.CURRENCY_SYMBOL` értéket, és válassza a `CurrencySymbolPositionType`‑t.  
- **Mely fájlformátumok támogatottak?** XML, MPP és sok más a `SaveFileFormat`‑on keresztül.  
- **Szükség van licencre a fejlesztéshez?** Egy ingyenes próba verzió teszteléshez elegendő; a termeléshez licenc szükséges.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alapbeállításhoz.

## Hogyan változtassuk meg a pénznem szimbólumát az Aspose.Tasks használatával Java‑ban?
Töltse be a célprojektet (vagy hozzon létre egy újat), állítsa be a kívánt pénznem‑tulajdonságokat, majd mentse a fájlt. A teljes művelet három API‑hívásból áll: egy `Project` objektum létrehozása vagy betöltése, a pénznemkód, szimbólum és pozíció hozzárendelése, végül a `project.save` meghívása. Ez a megközelítés friss projektekre és meglévő fájlokra egyaránt működik, Microsoft Project telepítése nélkül.

## Miért használjuk az Aspose.Tasks‑et a pénznem módosításához?
Az Aspose.Tasks **teljes API‑lefedettséget biztosít 30+ pénznem‑kapcsolt tulajdonságra**, lehetővé téve a kód, szimbólum, tizedesjegyek és pozicionálás egy helyen történő definiálását. A könyvtár több száz oldalas Project fájlokat egy másodpercnél gyorsabban dolgoz fel tipikus szerverhardveren, és Windows, Linux, valamint macOS rendszereken működik további függőségek nélkül.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK) 8 vagy újabb** – az API legalább JDK 8‑at igényel.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR‑t a [Aspose.Tasks letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA vagy bármely Java‑t támogató szerkesztő.  
4. **Írási jogosultsággal rendelkező mappa** – ahová a generált projektfájlt menteni fogja.

## Csomagok importálása
Az alábbi osztályok biztosítják a projekt‑tulajdonságokhoz, fájlkezeléshez és pénznem‑beállításokhoz való hozzáférést.  

`Project` – egy Microsoft Project fájlt reprezentál a memóriában.  
`Prj` – konstansokat tartalmaz a projekt‑szintű tulajdonságokhoz, beleértve a pénznem mezőket is.  
`CurrencySymbolPositionType` – felsorolja a pénznem szimbólum lehetséges pozícióit (előtte vagy utána az összegnek).  

Ezek az importok szükségesek, mielőtt a kód bármilyen projektet manipulálna.

## Lépés‑ről‑lépésre útmutató

### 1. lépés: Az adatkönyvtár meghatározása
Válasszon egy mappát, amely a forrásfájlokat tartalmazza, és ahová a kimenetet írni fogja. Győződjön meg arról, hogy a könyvtár létezik, és a Java folyamatnak írási jogosultsága van.

### 2. lépés: Új projektpéldány létrehozása
A `Project` osztály az Aspose.Tasks legfelső szintű objektuma, amely egyetlen Project fájlt reprezentál a memóriában. Példányosítása egy üres projektet hoz létre, amely készen áll a konfigurálásra.

### 3. lépés: Pénznem‑tulajdonságok beállítása
Itt állítja be a pénznemkódot, a tizedesjegyek számát, magát a szimbólumot és a szimbólum pozícióját.  

- **Pénznemkód** – hárombetűs ISO 4217 kód, például `AUD` vagy `USD`.  
- **Tizedesjegyek** – általában 2 a legtöbb pénznemnél.  
- **Pénznem szimbólum** – a mennyiségekkel megjelenő karakter vagy karakterlánc, pl. `$` vagy `€`.  
- **Szimbólum pozíció** – a `CurrencySymbolPositionType.Before` a szimbólumot a szám elé helyezi; az `After` a szám után.

Ezek a beállítások minden költség‑kapcsolt mezőre (erőforrás‑árak, feladat‑költségvetések stb.) hatással vannak a projektben.

> **Pro tipp:** Ha egy meglévő fájl pénznemét szeretné módosítani, töltse be a `new Project("file.mpp")` paranccsal, mielőtt alkalmazná a fenti beállításokat.

### 4. lépés: A frissített projekt mentése
Írja vissza a projektet a lemezre a kívánt formátummal. Az XML formátum ember‑olvasható, míg a `SaveFileFormat.MPP` teljes kompatibilitást biztosít a Microsoft Project‑tel.

### 5. lépés: Siker ellenőrzése
Nyomtasson ki egy rövid üzenetet vagy naplóbejegyzést, hogy tudja, a művelet hibamentesen befejeződött. Ez különösen hasznos automatizált folyamatokban.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **`NullPointerException` on `project.save`** | `dataDir` nem érvényes útvonal vagy nincs írási jogosultsága. | Győződjön meg arról, hogy a könyvtár létezik, és a Java folyamatnak van írási hozzáférése. |
| **A pénznem szimbólum nem jelenik meg** | A szimbólum pozíciója helytelenül van beállítva a területi beállításokhoz. | Használja a `CurrencySymbolPositionType.Before` értéket, ha a szimbólumnak az összeg előtt kell állnia. |
| **A projektfájl nem nyílik meg az MS Projectben** | Régebbi formátumban mentés, amely nem kompatibilis a beállításokkal. | Mentse a `SaveFileFormat.MPP` formátummal a legújabb MS Project verziókkal való teljes kompatibilitás érdekében. |

## Gyakran feltett kérdések

**Q: Beállíthatok több pénznemet egyetlen projektben az Aspose.Tasks használatával?**  
A: Igen, a projekt‑szintű pénznem definiálása után különböző pénznem‑beállításokat rendelhet egyes erőforrásokhoz vagy feladatokhoz a megfelelő költségmezők módosításával.

**Q: Az Aspose.Tasks kompatibilis a Microsoft Project különböző verzióival?**  
A: Teljes mértékben. A könyvtár támogatja a Project 2000‑tól a legújabb kiadásokig terjedő MPP fájlokat, valamint az XML‑et és egyéb csereformátumokat.

**Q: Az Aspose.Tasks támogatja az egyedi pénznemformátumokat?**  
A: Igen, definiálhat egyedi szimbólumokat, tizedesjegyeket és pozicionálást a regionális követelményeknek megfelelően, és ezek a beállítások a mentett fájlban maradnak.

**Q: Integrálhatom az Aspose.Tasks‑et más Java keretrendszerekkel?**  
A: Természetesen. Az API tisztán Java, így zökkenőmentesen működik Spring, Hibernate, Maven, Gradle és más ökoszisztémákkal.

**Q: Hol találok további segítséget vagy példákat?**  
A: Látogassa meg a [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi támogatásért, vagy tekintse meg a hivatalos dokumentációt a részletes API‑referenciákért.

## Következtetés
Most már tudja, **hogyan változtassa meg a pénznem szimbólumát** az Aspose.Tasks projektekben Java‑val, hogyan állítsa be a pénznemkódot, a tizedesjegyeket, és alkalmazzon egyedi szimbólumot. Ezek a lehetőségek lehetővé teszik, hogy regionális specifikus költségjelentéseket generáljon, a projekt költségvetéseket a helyi könyvelési szabványokhoz igazítsa, és a Microsoft Project fájlokat globális csapatok között konzisztensen tartsa.

---

**Utolsó frissítés:** 2026-09-09  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Kapcsolódó oktatóanyagok

- [java projekt tulajdonságok – Pénznem szimbólum kinyerése MPP-ből az Aspose.Tasks for Java használatával](/tasks/java/currency/currency-symbols/)
- [Pénznem tulajdonságok olvasása Java-ban az Aspose.Tasks projektek segítségével](/tasks/java/currency-properties/read-properties/)
- [Pénznem kódok kezelése Java-ban az Aspose.Tasks használatával](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
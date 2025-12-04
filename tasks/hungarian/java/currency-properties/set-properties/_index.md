---
date: 2025-12-04
description: Ismerje meg, hogyan állíthatja be a pénznemet az Aspose.Tasks Java projektekben,
  beleértve a pénznem és a pénznem szimbólum Java‑ban történő módosítását. Kezelje
  könnyedén a Microsoft Project fájlokat.
language: hu
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Hogyan állítsuk be a pénznemet az Aspose.Tasks projektekben – Java útmutató
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a pénznemet az Aspose.Tasks projektekben – Java útmutató

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **állítsa be a pénznemet** egy Microsoft Project fájlban az Aspose.Tasks Java API használatával. Akár a *valuta* megváltoztatására van szüksége nemzetközi csapatok számára, akár a *valuta szimbólum* módosítására Java-ban, az alábbi lépések világos magyarázatokkal és azonnal futtatható kóddal vezetik végig a folyamaton.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Tasks for Java.  
- **Megváltoztathatom a valuta szimbólumát?** Igen – használja a `CurrencySymbolPositionType` és a `Prj.CURRENCY_SYMBOL`.  
- **Mely fájlformátumok támogatottak?** XML, MPP és sok más a `SaveFileFormat` segítségével.  
- **Szükség van licencre a fejlesztéshez?** Egy ingyenes próba verzió teszteléshez elegendő; licenc szükséges a termeléshez.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alap beállításhoz.

## Mi a „valuta” egy Project fájlban?
A projekt valutája meghatározza, hogyan jelennek meg a költségértékek – kód (pl. `AUD`), tizedesjegyek száma, szimbólum (`$`) és a szimbólum pozíciója. Ezeknek a tulajdonságoknak a beállítása biztosítja, hogy minden költséggel kapcsolatos mező (erőforrás díjak, feladat költségvetések stb.) a megfelelő pénzügyi formátumot tükrözze a felhasználók számára.

## Miért használja az Aspose.Tasks-t a valuta módosításához?
- **Nincs szükség Microsoft Project telepítésre** – fájlok kezelése bármely szerveren.  
- **Teljes API lefedettség** – minden valuta‑kapcsolódó mező elérhető a `Prj` konstansokon keresztül.  
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken bármely Java‑kompatibilis IDE-vel.  
- **Magas teljesítmény** – nagy projektfájlok gyors és megbízható feldolgozása.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK)** – 8 vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR-t a [Aspose.Tasks letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA vagy bármely kedvelt szerkesztő.  
4. **Írási jogosultsággal rendelkező mappa** – ahová a generált projektfájl mentésre kerül.

## Csomagok importálása
Először importálja az osztályokat, amelyek hozzáférést biztosítanak a projekt tulajdonságaihoz és a fájlkezeléshez.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Adatkönyvtár meghatározása
Adja meg a mappát, amely a forrásfájlokat tartalmazza, és ahová a kimenet írásra kerül.

```java
String dataDir = "Your Data Directory";
```

### 2. lépés: Új Project példány létrehozása
Hozzon létre egy új `Project` objektumot. Ez az objektum egy memóriában lévő Microsoft Project fájlt képvisel.

```java
Project project = new Project();
```

### 3. lépés: Valuta tulajdonságok beállítása
Itt állítjuk be a **valuta beállításának** részleteit, mint a kód, a számjegyek, a szimbólum és a szimbólum pozíciója.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tipp:** Ha egy meglévő projektnél szeretne **valutát változtatni**, egyszerűen töltse be a fájlt a `new Project("file.mpp")` paranccal, mielőtt az előző beállításokat alkalmazná.

### 4. lépés: Frissített projekt mentése
Írja vissza a projektet a lemezre a kívánt formátumban. Ebben a példában az XML formátumot használjuk, de választhatja a `SaveFileFormat.MPP`-t is.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 5. lépés: Siker megerősítése
Írjon ki egy barátságos üzenetet, hogy tudja, a művelet hibamentesen befejeződött.

```java
System.out.println("Process completed Successfully");
```

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **`NullPointerException` on `project.save`** | `dataDir` nem érvényes útvonal, vagy nincs írási jogosultsága. | Győződjön meg róla, hogy a könyvtár létezik, és a Java folyamatnak van írási joga. |
| **Currency symbol not showing** | A szimbólum pozíciója helytelenül van beállítva az Ön területi beállításaihoz. | Használja a `CurrencySymbolPositionType.Before` értéket, ha a szimbólumnak az összeg előtt kell megjelenni. |
| **Project file does not open in MS Project** | Régebbi formátumban mentés, amely nem kompatibilis beállításokkal. | Mentse a `SaveFileFormat.MPP` használatával a legújabb MS Project verziókkal való teljes kompatibilitás érdekében. |

## Gyakran ismételt kérdések

**Q: Beállíthatok több valutát egyetlen projektben az Aspose.Tasks használatával?**  
A: Igen, az Aspose.Tasks lehetővé teszi több valuta kezelését egy projektfájlban, a valuta tulajdonságok erőforrás‑ vagy feladat‑alapú beállításával.

**Q: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?**  
A: Teljes mértékben. A könyvtár támogatja a Project 2000‑től a legújabb kiadásokig terjedő MPP fájlokat, valamint az XML‑et és más formátumokat is.

**Q: Az Aspose.Tasks támogatja az egyedi valutaformátumokat?**  
A: Igen, definiálhat egyedi szimbólumokat, tizedesjegyeket és elhelyezést, hogy megfeleljen bármely regionális követelménynek.

**Q: Integrálhatom az Aspose.Tasks-t más Java könyvtárakkal vagy keretrendszerekkel?**  
A: Természetesen. Az API tisztán Java, így zökkenőmentesen működik a Spring, Hibernate, Maven, Gradle és más ökoszisztémákkal.

**Q: Hol találok további támogatást vagy segítséget az Aspose.Tasks-hez?**  
A: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi segítségért, vagy tekintse meg a hivatalos dokumentációt a részletes API hivatkozásokért.

## Következtetés
Most már tudja, **hogyan állítsa be a valutát**, hogyan **változtassa meg a valuta** értékeket, és hogyan **változtassa meg a valuta szimbólumot Java‑stílusban** az Aspose.Tasks for Java segítségével. Ezek a lehetőségek lehetővé teszik a költségadatok testreszabását globális csapatok számára, helyspecifikus jelentések generálását, és a projektfájlok konzisztens tartását a határokon át.

---

**Legutóbb frissítve:** 2025-12-04  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
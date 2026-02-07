---
date: 2026-02-07
description: Tanulja meg, hogyan állíthatja be a pénznemkódot Java-ban az Aspose.Tasks
  projektekben, hogyan változtathatja meg a pénznem szimbólumát, és hogyan alkalmazhat
  egy egyéni pénznemformátumot a Microsoft Project fájlokhoz.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: valuta kód Java – Hogyan állítsuk be az Aspose.Tasks projektekben
url: /hu/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a pénznemkódot az Aspose.Tasks-ben – Java útmutató

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan állítsa be a pénznemkódot Java-ban egy Microsoft Project fájlhoz az Aspose.Tasks Java API használatával. Akár a *valuta* megváltoztatására van szüksége nemzetközi csapatok számára, akár a *valuta szimbólum* módosítására, vagy egy **egyedi pénznemformátum** alkalmazására, az alábbi lépések világos magyarázatokkal és azonnal futtatható kóddal vezetik végig a folyamaton.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java.  
- **Megváltoztathatom a valuta szimbólumát?** Igen – használja a `CurrencySymbolPositionType` és a `Prj.CURRENCY_SYMBOL` értékeket.  
- **Mely fájlformátumok támogatottak?** XML, MPP és sok más a `SaveFileFormat` segítségével.  
- **Szükség van licencre a fejlesztéshez?** Egy ingyenes próba a teszteléshez elegendő; a termeléshez licenc szükséges.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alapbeállításhoz.

## Hogyan állítsuk be a pénznemkódot Java-ban az Aspose.Tasks-ben
Egy projekt pénzneme határozza meg, hogyan jelennek meg a költségértékek – kód (pl. `AUD`), a tizedesjegyek száma, a szimbólum (`$`) és a szimbólum pozíciója. Ezeknek a tulajdonságoknak a beállítása biztosítja, hogy minden költséggel kapcsolatos mező (erőforrás díjak, feladat költségvetések stb.) a megfelelő pénzügyi formátumot tükrözze a felhasználók számára.

## Miért használjuk az Aspose.Tasks-et a valuta módosításához?
- **Microsoft Project telepítés nélkül** – fájlok kezelése bármely szerveren.  
- **Teljes API lefedettség** – minden pénznemhez kapcsolódó mező elérhető a `Prj` konstansokon keresztül.  
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken bármely Java‑kompatibilis IDE-vel.  
- **Magas teljesítmény** – nagy projektfájlok gyors és megbízható feldolgozása.  
- **Egyedi pénznemformátum támogatása** – meghatározhatja a szimbólumokat, a tizedesjegyek számát és a pozíciót a regionális szabványoknak megfelelően.

## Előkövetelmények
1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR-t a [Aspose.Tasks letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA vagy bármely kedvelt szerkesztő.  
4. **Írható mappa** – ahová a generált projektfájl mentésre kerül.

## Csomagok importálása
Először importálja azokat az osztályokat, amelyek hozzáférést biztosítanak a projekt tulajdonságaihoz és a fájlkezeléshez.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Adatkönyvtár meghatározása
Adja meg azt a mappát, amely a forrásfájlokat tartalmazza, és ahová a kimenet írásra kerül.

```java
String dataDir = "Your Data Directory";
```

### 2. lépés: Új Project példány létrehozása
Hozzon létre egy új `Project` objektumot. Ez az objektum egy memóriában létező Microsoft Project fájlt képvisel.

```java
Project project = new Project();
```

### 3. lépés: Pénznem tulajdonságok beállítása
Itt állítjuk be a **pénznem** részleteit, mint a kód, a tizedesjegyek száma, a szimbólum és a szimbólum pozíciója.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tipp:** Ha egy meglévő fájl **projekt pénznemét** szeretné megváltoztatni, egyszerűen töltse be a `new Project("file.mpp")` paranccsal, mielőtt alkalmazná a fenti beállításokat.

### 4. lépés: A frissített projekt mentése
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
| **`NullPointerException` a `project.save` során** | `dataDir` nem érvényes útvonal, vagy nincs írási jogosultsága. | Győződjön meg arról, hogy a könyvtár létezik, és a Java folyamatnak van írási joga. |
| **A valuta szimbólum nem jelenik meg** | A szimbólum pozíciója helytelenül van beállítva az Ön területi beállításaihoz. | Használja a `CurrencySymbolPositionType.Before` értéket, ha a szimbólumnak az összeg előtt kell állnia. |
| **A projektfájl nem nyílik meg az MS Projectben** | Régebbi formátumban mentés, amely nem kompatibilis a beállításokkal. | Mentse `SaveFileFormat.MPP` használatával a legújabb MS Project verziókkal való teljes kompatibilitás érdekében. |

## Gyakran Ismételt Kérdések

**K: Beállíthatok több pénznemet egyetlen projektben az Aspose.Tasks használatával?**  
V: Igen, az Aspose.Tasks lehetővé teszi több pénznem kezelését egy projektfájlban, a pénznem tulajdonságok erőforrás- vagy feladatszintű beállításával.

**K: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?**  
V: Teljesen. A könyvtár támogatja a Project 2000-től a legújabb kiadásokig terjedő MPP fájlokat, valamint az XML és egyéb formátumokat.

**K: Az Aspose.Tasks támogatja az egyedi pénznemformátumokat?**  
V: Igen, meghatározhat egyedi szimbólumokat, tizedesjegyek számát és pozíciót, hogy megfeleljen bármely regionális követelménynek.

**K: Integrálhatom az Aspose.Tasks-et más Java könyvtárakkal vagy keretrendszerekkel?**  
V: Természetesen. Az API tiszta Java, így zökkenőmentesen működik a Spring, Hibernate, Maven, Gradle és más ökoszisztémákkal.

**K: Hol találok további támogatást vagy segítséget az Aspose.Tasks-hez?**  
V: Látogassa meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15) a közösségi segítségért, vagy tekintse meg a hivatalos dokumentációt a részletes API hivatkozásokért.

## Összegzés
Most már tudja, **hogyan állítsa be a pénznemkódot Java-ban**, hogyan **változtassa meg a valuta** értékeket, és hogyan **cserélje le a valuta szimbólumát** az Aspose.Tasks for Java segítségével. Ezek a lehetőségek lehetővé teszik a költségadatok testreszabását globális csapatok számára, helyi specifikus jelentések generálását, és a projektfájlok határokon átívelő konzisztenciáját.

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
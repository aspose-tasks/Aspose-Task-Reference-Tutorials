---
date: 2026-02-10
description: Tanulja meg, hogyan szerezze meg a pénznem értékeket, olvassa be az MS
  Project fájlt, és konvertálja a projektfájlt Java-ban az Aspose.Tasks segítségével.
  Lépésről‑lépésre útmutató a pénznem számjegyeinek kinyeréséhez.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan nyerhetünk ki pénznemet az MS Projectből az Aspose.Tasks segítségével
url: /hu/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan szerezhetünk pénznemet a MS Projectből az Aspose.Tasks segítségével

## Introduction
Ha kíváncsi vagy arra, **hogyan szerezhetünk pénznem** információt egy Microsoft Project fájlból, jó helyen jársz. Ebben az átfogó útmutatóban megtanulod, **hogyan dolgozzunk ms project currency** értékekkel az Aspose.Tasks Java könyvtár segítségével. Akár jelentéskészítő eszközt, migrációs segédeszközt építesz, vagy egyszerűen csak a **java project file** pénznem beállításait kell beolvasnod, ez az útmutató minden lépésen végigvezet – a *.mpp* fájl betöltésétől a pénznemjegyek kinyeréséig. A végére magabiztosan fogod kezelni a ms project currency adatokat saját alkalmazásaidban.

## Quick Answers
- **Melyik könyvtár olvassa a MS Project fájlokat?** Aspose.Tasks for Java.  
- **Hány kódsor szükséges a pénznemjegyek lekéréséhez?** Csak három tömör sor a projekt betöltése után.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba működik teszteléshez; a termeléshez kereskedelmi licenc szükséges.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb (bármely JDK, amely futtatja az Aspose.Tasks‑t).  
- **Lekérhetek más Project tulajdonságokat is?** Igen – az Aspose.Tasks teljes Project mezők halmazát teszi elérhetővé (pl. kezdő dátum, költségárak, stb.).

## What is ms project currency?
`ms project currency` a numerikus pontosságra (tizedesjegyek száma) utal, amelyet a Microsoft Project a pénzügyi értékek megjelenítésekor használ. A Project fájlban **CURRENCY_DIGITS** tulajdonságként van tárolva, és meghatározza, hogy az összegek egész számokként, egy‑tizedes, két‑tizedes stb. formában jelennek meg.

## Why use Aspose.Tasks for handling ms project currency?
- **Microsoft Project telepítése nem szükséges** – közvetlenül *.mpp* fájlokkal dolgozhatsz bármilyen Java‑t támogató platformon.  
- **Erős típusbiztonság** – az API erősen típusos értékeket ad vissza, csökkentve a feldolgozási hibákat.  
- **Teljesítmény‑optimalizált** – nagy projekteket gyorsan betölthetsz, és csak a szükséges mezőket nyerheted ki.  
- **Keresztplatformos** – Windows, Linux vagy macOS rendszeren futtatható módosítás nélkül.

## Prerequisites
Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

1. **Java fejlesztői környezet** – JDK 8 vagy újabb telepítve és konfigurálva.  
2. **Aspose.Tasks for Java** – töltsd le a legújabb JAR‑t a hivatalos oldalról: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Alap Java ismeretek** – kényelmesen kell tudnod Java projektet létrehozni, külső könyvtárakat hozzáadni, és egy `main` metódust futtatni.  

## Import Packages
Először importáld a szükséges osztályokat.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Define Data Directory
Add meg a mappát, amely a **java project file** (`*.mpp`) fájlt tartalmazza.  
```java
String dataDir = "Your Data Directory";
```
Cseréld le a `"Your Data Directory"` értéket az abszolút vagy relatív útra, ahol a `project.mpp` található.

## Step 2: Load the MPP File  
Most megmutatjuk, **hogyan töltsünk be mpp** fájlokat az Aspose.Tasks segítségével.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Győződj meg róla, hogy a fájlnév pontosan egyezik; ellenkező esetben `IOException` lesz dobva.

## Step 3: Retrieve Currency Digits  
A projekt betöltése után a **ms project currency** jegyek kinyerése egyetlen sorban megoldható:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
A hívás egy `Integer`‑t ad vissza, amely a tizedesjegyek számát jelzi (pl. `2` a centekhez). Az érték a konzolra kerül kiírásra, de tovább is tárolható egy változóban további feldolgozáshoz.

## Common Issues & Tips
- **File not found** – ellenőrizd a `dataDir` útvonalat, és győződj meg róla, hogy a fájlnév helyes, beleértve a `.mpp` kiterjesztést is.  
- **Unsupported file version** – az Aspose.Tasks a Project 2000‑2024 formátumokat támogatja; a régebbi vagy sérült fájlok konvertálást igényelhetnek.  
- **License not set** – fejlesztés során egy próba működik, de termeléshez érvényes licencet kell alkalmazni az értékelő vízjelek elkerülése érdekében.

## Frequently Asked Questions

**Q: Képes az Aspose.Tasks más Project attribútumok kezelésére is a pénznemjegyek mellett?**  
A: Igen, az Aspose.Tasks széles körű funkcionalitást kínál a Project fájlok különböző aspektusainak, például feladatok, erőforrások és egyéni mezők manipulálására.

**Q: Alkalmas-e az Aspose.Tasks vállalati szintű alkalmazásokra?**  
A: Teljes mértékben, az Aspose.Tasks úgy lett tervezve, hogy megfeleljen a vállalati szintű projektek igényeinek, magas teljesítményt és skálázhatóságot biztosítva.

**Q: Támogatja-e az Aspose.Tasks a keresztplatformos fejlesztést?**  
A: Igen, az Aspose.Tasks for Java‑t bármely, a Java Runtime Environment‑et támogató platformon használhatod (Windows, Linux, macOS).

**Q: Próbálhatom-e ki az Aspose.Tasks‑t vásárlás előtt?**  
A: Igen, letölthetsz egy ingyenes próba verziót [innen](https://releases.aspose.com/).

**Q: Hol kaphatok támogatást az Aspose.Tasks‑hez?**  
A: Támogatást a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) találhatsz.

## Conclusion
Most már tudod, **hogyan szerezhetünk pénznem** jegyeket egy MS Project fájlból az Aspose.Tasks for Java segítségével. A folyamat egyszerű: töltsd be a projektet, hívd meg a `project.get(Prj.CURRENCY_DIGITS)` metódust, és használd az eredményt az alkalmazásodban. Nyugodtan fedezd fel a többi projekt tulajdonságot ugyanazzal a mintával, és integráld ezt a logikát nagyobb jelentéskészítő vagy migrációs megoldásokba.

---

**Last Updated:** 2026-02-10  
**Tesztelve:** Aspose.Tasks for Java (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-04
description: Ismerje meg, hogyan olvashatja ki a pénznem tulajdonságait Java-ban MS
  Project fájlokból az Aspose.Tasks for Java használatával. Kövesse ezt a lépésről‑lépésre
  útmutatót a pénznemkód, szimbólum, számjegyek és pozíció programozott kinyeréséhez.
language: hu
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Valuta tulajdonságok olvasása Java-val az Aspose.Tasks projektekben
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pénznem tulajdonságok olvasása Java-val az Aspose.Tasks projektekben

## Bevezetés
Ebben az útmutatóban **Java-val olvasod a pénznem tulajdonságokat** a Microsoft Project fájlokból az Aspose.Tasks for Java API használatával. Az Aspose.Tasks lehetővé teszi, hogy .mpp fájlokkal dolgozz anélkül, hogy a Microsoft Project telepítve lenne, így ideális automatizált jelentéskészítéshez, adatátvitelhez vagy Java‑alapú vállalati alkalmazásokba való integrációhoz. A útmutató végére képes leszel közvetlenül egy projektfájlból kinyerni a pénznemkódot, szimbólumot, a tizedesjegyek számát és a szimbólum pozícióját.

## Gyors válaszok
- **Mit jelent a “read currency properties java”?** Ez a pénznem‑hez kapcsolódó metaadatok (kód, szimbólum, számjegyek, pozíció) Java kóddal történő lekérdezését jelenti egy MS Project fájlból.  
- **Szükségem van licencre a kipróbáláshoz?** Az Aspose.Tasks ingyenes próbaverziója elérhető; kereskedelmi licenc szükséges a termelésben való használathoz.  
- **Melyik JDK verzió szükséges?** Java 8 vagy újabb.  
- **Módosíthatom a pénznem beállításait a lekérdezés után?** Igen, az Aspose.Tasks lehetővé teszi a pénznem tulajdonságok olvasását és írását is.  
- **Kompatibilis minden .mpp verzióval?** Az API támogatja a Microsoft Project 2003‑2021 között létrehozott fájlokat.

## Mi az a pénznem tulajdonságok olvasása Java-val?
A pénznem tulajdonságok Java‑ban történő olvasása azt jelenti, hogy hozzáférünk a projekt‑szintű beállításokhoz, amelyek meghatározzák, hogyan jelennek meg a pénzügyi értékek egy Microsoft Project fájlban. Ezek a beállítások tartalmazzák az ISO pénznemkódot (pl. **USD**), a szimbólumot (**$**), a tizedesjegyek számát, valamint azt, hogy a szimbólum az összeg előtt vagy után jelenik‑e meg.

## Miért olvasd a pénznem tulajdonságokat Java-val az Aspose.Tasks segítségével?
- **Microsoft Project telepítése nélkül** – az API bármely, Java‑t támogató platformon működik.  
- **Gyors, beágyazott kinyerés** – ideális nagy mennyiségű projektfájl kötegelt feldolgozásához.  
- **Teljes kontroll** – a lekért értékeket egyedi jelentésekkel kombinálhatod vagy ERP rendszerekbe integrálhatod.  
- **Keresztverziós támogatás** – .mpp fájlokkal működik a Project 2003‑tól a legújabb 2021‑es kiadásig.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

1. **Java Development Kit (JDK)** – Java 8 vagy újabb, telepítve és a `PATH`‑ban konfigurálva.  
2. **Aspose.Tasks for Java JAR** – töltsd le a legújabb könyvtárat [itt](https://releases.aspose.com/tasks/java/), és add hozzá a projekt osztályútvonalához.  

## Csomagok importálása
Kezdjük az Aspose.Tasks névtér importálásával, amely a projektkezeléshez szükséges:

```java
import com.aspose.tasks.*;
```

## 1. lépés: A projekt könyvtár beállítása
Határozd meg azt a mappát, amelyik a `.mpp` fájlt tartalmazza, amelyet elemezni szeretnél. Az útvonal változóban való tárolása újrahasználhatóvá teszi a kódot:

```java
String dataDir = "Your Data Directory";
```

*Csere `"Your Data Directory"` a projekt.mpp fájl helyét mutató abszolút vagy relatív útvonalra.*

## 2. lépés: Projektolvasó példány létrehozása
Töltsd be a Microsoft Project fájlt egy `Project` objektumba. Ez az objektum hozzáférést biztosít az összes projekt tulajdonsághoz, beleértve a pénznem beállításokat is:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Ha a fájl más néven szerepel, módosítsd a `"project.mpp"` értéket ennek megfelelően.*

## 3. lépés: Pénznem tulajdonságok megjelenítése
Most lekérheted az egyes pénznem attribútokat a `Prj` enumerációval, és kiírhatod az eredményeket a konzolra. Az API objektumokat ad vissza, amelyeket stringgé konvertálhatsz a megjelenítéshez:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Ami megjelenik majd:**  
- **Pénznemkód** – ISO‑4217 kód, például `USD`, `EUR`, `JPY`.  
- **Pénznemjegyek** – általában `2` a legtöbb pénznemnél, `0` a japán jen esetén.  
- **Pénznemszimbólum** – a jelentésekben megjelenő karakter (`$`, `€`, `¥`).  
- **Pénznemszimbólum pozíciója** – `0` a **összeg előtt**, `1` a **összeg után**.

## 4. lépés: Feldolgozás befejezése
Jelezd, hogy a kinyerés sikeresen befejeződött. Ez az egyszerű üzenet hasznos, ha a kód egy nagyobb kötegelt feladat részeként fut:

```java
System.out.println("Process completed Successfully");
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **FileNotFoundException** | `dataDir` útvonal helytelen vagy a fájlnév el van gépelve. | Ellenőrizd a könyvtár‑stringet, és győződj meg róla, hogy a `.mpp` fájl a megadott helyen létezik. |
| **NullPointerException on `project.get(...)`** | A projektfájl nem tartalmaz pénznem információt (valószínűtlen) vagy a tulajdonság‑kulcs hibás. | Használd a `project.contains(Prj.CURRENCY_CODE)` ellenőrzést a lekérdezés előtt. |
| **LicenseException** | Érvényes Aspose.Tasks licenc hiányában futtatod a kódot termelési környezetben. | Alkalmazz licencfájlt a `License license = new License(); license.setLicense("Aspose.Tasks.lic");` kóddal a `Project` objektum létrehozása előtt. |

## Gyakran feltett kérdések

**K: Az Aspose.Tasks kompatibilis-e a Microsoft Project minden verziójával?**  
V: Az Aspose.Tasks támogatja a Microsoft Project 2003‑2021 által generált .mpp fájlokat, lefedve a régebbi és a legújabb formátumokat is.

**K: Módosíthatom a pénznem tulajdonságokat az Aspose.Tasks segítségével?**  
V: Igen, a pénznem beállítások olvasása és írása egyaránt lehetséges. Használd a `project.set(Prj.CURRENCY_CODE, "EUR");` parancsot, majd mentsd a projektet.

**K: Az Aspose.Tasks alkalmas kereskedelmi felhasználásra?**  
V: Teljes mértékben. Ez egy kereskedelmi könyvtár; licencet vásárolhatsz [itt](https://purchase.aspose.com/buy).

**K: Van ingyenes próbaverzió?**  
V: Igen, teljes funkcionalitású próba elérhető [itt](https://releases.aspose.com/).

**K: Hol kaphatok segítséget vagy támogatást az Aspose.Tasks-hez?**  
V: A hivatalos Aspose.Tasks fórum a legjobb hely a segítségkéréshez – látogasd meg [itt](https://forum.aspose.com/c/tasks/15).

## Következtetés
Most már megtanultad, hogyan **Java-val olvasd a pénznem tulajdonságokat** egy MS Project fájlból az Aspose.Tasks for Java segítségével. Ez a képesség lehetővé teszi, hogy a pénznem metaadatait egyedi jelentésekbe, pénzügyi elemzésekbe vagy integrációs folyamatokba építsd be, anélkül, hogy a Microsoft Projectre támaszkodnál. Nyugodtan kísérletezz a tulajdonságok módosításával vagy más projektattribútumokkal való kombinálásával, hogy gazdagabb megoldásokat hozz létre.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
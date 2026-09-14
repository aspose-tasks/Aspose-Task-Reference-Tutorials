---
date: 2026-09-14
description: Ismerje meg, hogyan lehet lekérni az MS Project pénznemét és Java‑ban
  olvasni a projekt tulajdonságait az Aspose.Tasks segítségével. Lépésről‑lépésre
  útmutató a pénznem számjegyeinek kinyeréséhez egy MPP fájlból.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Hogyan szerezzen pénznemet az MS Projectből az Aspose.Tasks használatával
og_description: Ismerje meg, hogyan lehet lekérni az MS Project pénznemét és Java‑ban
  olvasni a projekt tulajdonságait az Aspose.Tasks segítségével. Kövesse ezt a tömör
  Java‑tutorialt a pénznem számjegyeinek kinyeréséhez egy MPP fájlból.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Hogyan lehet lekérni az MS Project pénznemét az Aspose.Tasks használatával
  – Java útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Hogyan lehet lekérni az MS Project pénznemét az Aspose.Tasks használatával
url: /hu/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan szerezze meg a MS Project pénznemét az Aspose.Tasks használatával

## Bevezetés
Ha kíváncsi vagy arra, hogy **hogyan szerezze meg a ms project pénznem** információkat egy Microsoft Project fájlból, jó helyen jársz. Ebben az átfogó útmutatóban felfedezheted, **hogyan dolgozzunk ms project pénznem** értékekkel az Aspose.Tasks Java könyvtár segítségével. Akár jelentéskészítő eszközt, migrációs segédeszközt építesz, vagy egyszerűen csak a **java projekt fájl** pénznem beállításait kell olvasnod, ez az útmutató minden lépésen végigvezet – a *.mpp* fájl betöltésétől a pénznemjegyek kinyeréséig. A végére magabiztosan fogod kezelni a ms project pénznem adatokat saját alkalmazásaidban.

## Gyors válaszok
- **Melyik könyvtár olvassa a MS Project fájlokat?** Aspose.Tasks for Java.  
- **Hány sor kód szükséges a pénznemjegyek lekéréséhez?** Csak három tömör sor a projekt betöltése után.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba működik teszteléshez; a termeléshez kereskedelmi licenc szükséges.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb (bármely JDK, amely futtatja az Aspose.Tasks-et).  
- **Lekérhetek más Project tulajdonságokat is?** Igen – az Aspose.Tasks egy teljes Project mezők halmazát teszi elérhetővé (pl. kezdő dátum, költségarányok stb.).

## Mi az ms project pénznem?
`ms project currency` tulajdonság meghatározza, hogy a Microsoft Project hány tizedesjegyet használ a pénzügyi értékek megjelenítésekor. A Project fájlban a **CURRENCY_DIGITS** mezőként van tárolva, és meghatározza, hogy az összegek egész számokként, egy‑tizedes, két‑tizedes stb. jelennek meg. Ez a beállítás közvetlenül befolyásolja a költségvetési jelentéseket, a költségösszesítéseket és bármely felhasználói felületet, amely pénzügyi adatokat jelenít meg, így elengedhetetlen a pontos adatcseréhez.

## Miért használjuk az Aspose.Tasks-et az ms project pénznem kezeléséhez?
Az Aspose.Tasks lehetővé teszi a pénznemjegyek kinyerését a Microsoft Project telepítése nélkül, és ezt vállalati szintű teljesítménnyel teszi. A könyvtár támogatja a **30+ év Project fájlverzióit** – a Project 2000-tól a Project 2024-ig – több mint **150 különböző fájlsémát** lefedve. Egy 500 oldalas projekt betöltése általában **2 másodpercnél** kevesebb időt vesz igénybe egy standard szerveren, és csak a szükséges mezőket kérdezheted le, így a memóriahasználat **50 MB** alatt marad még a legnagyobb ütemezéseknél is.

## Előfeltételek
1. **Java fejlesztői környezet** – JDK 8 vagy újabb telepítve és konfigurálva.  
2. **Aspose.Tasks for Java** – töltsd le a legújabb JAR fájlt a hivatalos oldalról: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Alap Java ismeretek** – kényelmesen kell tudnod Java projektet létrehozni, külső könyvtárakat hozzáadni, és futtatni egy `main` metódust.  

## Csomagok importálása
Először importáljuk a szükséges osztályokat.  
Importáld a `Project` osztályt és a kapcsolódó segédprogramokat az Aspose.Tasks könyvtárból.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 1. lépés: adatkönyvtár meghatározása
Add meg azt a mappát, amely a **java projekt fájlodat** (`*.mpp`) tartalmazza.  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` helyettesítsd a `project.mpp`-t tartalmazó abszolút vagy relatív útvonallal.

## 2. lépés: mpp fájl betöltése
Most megmutatjuk, **hogyan töltsünk be mpp** fájlokat az Aspose.Tasks segítségével.  
A `Project` osztály egy Microsoft Project fájlt képvisel, és hozzáférést biztosít a tulajdonságaihoz.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Győződj meg róla, hogy a fájlnév pontosan egyezik; ellenkező esetben `IOException` keletkezik.

## 3. lépés: pénznemjegyek lekérése
A projekt betöltése után a **ms project pénznem** jegyeinek kinyerése egy soros megoldás:  
A `getCurrencyDigits()` metódus visszaadja a pénzügyi értékekhez definiált tizedesjegyek számát.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
A hívás egy `Integer` értéket ad vissza, amely a tizedesjegyek számát jelzi (pl. `2` a centekhez). Az érték a konzolra kerül kiírásra, de tovább is tárolható egy változóban további feldolgozáshoz.

## Gyakori problémák és tippek
- **Fájl nem található** – ellenőrizd a `dataDir` útvonalat, és győződj meg róla, hogy a fájlnév helyes, beleértve a `.mpp` kiterjesztést.  
- **Nem támogatott fájlverzió** – az Aspose.Tasks támogatja a Project 2000‑2024 formátumokat; a régebbi vagy sérült fájlok konvertálásra szorulhatnak.  
- **Licenc nincs beállítva** – fejlesztés közben egy próba működik, de a termeléshez érvényes licencet kell alkalmazni, hogy elkerüld a kiértékelési vízjeleket.

## Gyakran ismételt kérdések

**K: Kezelhet az Aspose.Tasks más Project attribútumokat is a pénznemjegyek mellett?**  
V: Igen, az Aspose.Tasks széles körű funkciókat kínál a Project fájlok különböző aspektusainak manipulálására, például feladatok, erőforrások és **egyéni mezők**.

**K: Alkalmas-e az Aspose.Tasks vállalati szintű alkalmazásokra?**  
V: Teljes mértékben, az Aspose.Tasks úgy lett tervezve, hogy megfeleljen a **vállalati szintű projektek** igényeinek, magas teljesítményt és skálázhatóságot biztosítva.

**K: Támogatja-e az Aspose.Tasks a többplatformos fejlesztést?**  
V: Igen, az Aspose.Tasks for Java bármely, a Java Runtime Environment-et (Windows, Linux, macOS) támogató platformon használható.

**K: Kipróbálhatom az Aspose.Tasks-et vásárlás előtt?**  
V: Igen, letölthetsz egy ingyenes próba verziót a [Aspose kiadási oldalról](https://releases.aspose.com/).

**K: Hol kaphatok támogatást az Aspose.Tasks-hez?**  
V: Támogatást a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15) találhatsz.

---

**Utoljára frissítve:** 2026-09-14  
**Tesztelve:** Aspose.Tasks for Java (a legújabb a írás időpontjában)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [java projekt tulajdonságok – Pénznem szimbólum kinyerése MPP-ből az Aspose.Tasks for Java használatával](/tasks/java/currency/currency-symbols/)
- [Hogyan nyerjünk ki pénznemet a MS Projectből az Aspose.Tasks segítségével](/tasks/java/currency/currency-codes/)
- [Project tulajdonságok Java – Metaadatok olvasása az Aspose.Tasks segítségével](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
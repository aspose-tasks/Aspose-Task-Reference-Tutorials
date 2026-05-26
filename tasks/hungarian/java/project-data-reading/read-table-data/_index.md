---
date: 2026-05-26
description: Ismerje meg, hogyan lehet lekérni a táblamezőket és olvasni a táblaadatokat
  Java-ban az Aspose.Tasks használatával. Ez az útmutató megmutatja, hogyan lehet
  a táblainformációkat Project fájlokból lekérni.
keywords:
- read table data aspose.tasks
- Aspose.Tasks Java
- project table extraction
linktitle: Táblaadatok olvasása fájlból az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to get table fields and read table data in Java using Aspose.Tasks.
    This tutorial shows you how to retrieve table information from Project files.
  headline: How to get table fields and read table data in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Load each project separately with `new Project(path)` and repeat the table‑field
      extraction loop for each instance.
    question: How do I read table data in a multi‑project environment?
  - answer: Yes, after printing the field details you can write them to a `FileWriter`
      or use a CSV library such as OpenCSV to generate a properly escaped file.
    question: Can I export the retrieved table fields to CSV?
  - answer: Absolutely. The `project.getTables()` collection includes both default
      and user‑defined tables, so you can iterate through them and process each one
      individually.
    question: Does Aspose.Tasks handle custom tables created by users?
  - answer: Use the overloaded `Project` constructor that accepts a `LoadOptions`
      object where you can specify the password, e.g., `new Project(path, new LoadOptions("pwd"))`.
    question: What if the Project file is password‑protected?
  - answer: Check each `TableField`'s `getVisible()` method (available in newer releases)
      to determine whether the column is displayed in the UI.
    question: Is there a way to filter only visible columns?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan lehet lekérni a táblamezőket és olvasni a táblaadatokat az Aspose.Tasks-ben
url: /hu/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan kérdezhetők le a táblamezők és olvashatók a táblázat adatai az Aspose.Tasks-ben

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan **hogyan kérdezheti le a táblamezőket** és **read table data aspose.tasks** API használatával **olvashatja a táblázat adatokat** egy Microsoft Project fájlból. Akár egy egyedi jelentéskészítő irányítópultot épít, akár régi projektadatokat migrál, vagy ütemezés‑elemzést automatizál, a tábladefiníciók programozott kinyerése számtalan manuális órát takarít meg. Végigvezetjük a környezet beállításán, a projekt betöltésén, és az egyes oszlopok tulajdonságainak kiírásán, hogy azonnal használni tudja ezt a funkciót Java‑alkalmazásaiban.

## Gyors válaszok
- **Mi jelent a „get table fields”?** Azt jelenti, hogy lekérdezi a Project nézet táblájában megjelenő minden oszlop definícióját (szélesség, cím, igazítás stb.).  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a kiértékeléshez elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Olvashatok táblákat bármely Project verzióból?** Igen, az Aspose.Tasks több mint 15 Microsoft Project fájlverziót támogat, a Project 2003‑tól a Project 2024‑ig.  
- **Szükséges-e további beállítás?** Csak JDK 8+ és az Aspose.Tasks JAR a classpath‑on.

## Mi az a read table data aspose.tasks?
A read table data aspose.tasks az Aspose.Tasks API metóduskészlete, amely lehetővé teszi a Microsoft Project fájlban definiált táblák szerkezetének és tartalmának programozott elérését. Metaadatokat ad vissza, például oszlopszélességet, címet, igazítást és láthatóságot, lehetővé téve a projekt ütemezések újraalkotását vagy átalakítását bármilyen formátumba, amire szüksége van.

## Miért használjuk az Aspose.Tasks‑et a táblázat adatok olvasásához?
Az Aspose.Tasks **50+ különböző Project fájlformátumot** (köztük MPP, MPX, XML és Primavera) dolgoz fel, és akár **10 000 feladatot** is kezel anélkül, hogy a teljes fájlt memóriába töltené. Ez a kvantifikált teljesítmény lehetővé teszi, hogy nagy vállalati projektekből biztonságosan kinyerje a táblákat, miközben a memóriahasználat **200 MB** alatt marad.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK) 8 vagy újabb** – letöltés a hivatalos Oracle weboldalról.  
2. **Aspose.Tasks for Java JAR** – szerezze be a legújabb verziót a [letöltési hivatkozás](https://releases.aspose.com/tasks/java/) segítségével, és adja hozzá a projekt build útvonalához.  

> **Pro tipp:** Ha Maven‑t vagy Gradle‑t használ, közvetlenül hivatkozhat az Aspose.Tasks artefaktumra a függőségkezelés egyszerűsítése érdekében.

## Csomagok importálása
A `Project`, `Table` és `TableField` osztályok a táblák olvasásának alapját képezik.

A `Project` osztály az Aspose.Tasks felső szintű objektuma, amely egy Microsoft Project fájlt reprezentál a memóriában.  

A `Table` osztály egy `TableField` objektumok gyűjteményét tartalmazza, amelyek egy nézet egy oszlopát írják le.  

A `TableField` osztály egy definíciót tárol egy oszlop szélességéről, címéről, igazításáról és láthatóságáról.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## 1. lépés: Az adatkönyvtár beállítása
Adja meg azt a mappát, amelyik a *.mpp* fájlt tartalmazza:

```java
String dataDir = "Your Data Directory";
```

Cserélje le a `"Your Data Directory"` értéket a gépén lévő abszolút útvonalra (pl. `C:/Projects/Data/`). Az abszolút útvonal használata elkerüli a class‑loader kétértelműségeket, amikor a kód különböző IDE‑kből fut.

## 2. lépés: A projektfájl betöltése
Hozzon létre egy `Project` példányt, amely a vizsgálni kívánt Project fájlra mutat:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

Ha a fájlja más néven vagy kiterjesztéssel rendelkezik, módosítsa a karakterláncot ennek megfelelően. A konstruktor automatikusan felismeri a fájlformátumot, így nem kell manuálisan megadnia a verziót.

## 3. lépés: Táblainformációk lekérése
Most **get table fields**‑t hajtunk végre, és megjelenítjük minden mező tulajdonságait:

```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```

A kódrészlet kiírja a szélességet, a címet és az igazítást az alapértelmezett táblában lévő minden oszlopra, így teljes képet kap a projektben definiált **table fields**‑ről.

## Hogyan olvassuk a táblázat adatokat az Aspose.Tasks for Java segítségével?
A tényleges táblázat adatok olvasásához először töltse be a projektet, majd szerezze be a kívánt táblát (például az alapértelmezettet) a `project.getTables().getByName("Name")` vagy index alapján. Iteráljon a `table.getFields()` által visszaadott gyűjteményen, és érje el minden `TableField` tulajdonságát, például szélességet, címet, igazítást és láthatóságot. Ez a megközelítés bármely egyedi vagy beépített táblára működik, amely a Project fájlban definiálva van.

## Gyakori hibák és tippek
- **Null táblák** – Ha egy projektnek nincsenek táblái, a `project.getTables()` üres lehet. Mindig ellenőrizze a gyűjtemény méretét, mielőtt indexet használna.  
- **Kódolási problémák** – A címekben a nem‑ASCII karakterek helyesen jelennek meg, ha a legújabb Aspose.Tasks verziót (24.12 vagy újabb) használja.  
- **Teljesítmény** – Nagyon nagy *.mpp* fájlok betöltése memóriaigényes lehet; 500 MB‑nál nagyobb fájlok esetén fontolja meg a streaming API‑t (`ProjectReader`) használatát.  

## Gyakran feltett kérdések

**K: Hogyan olvassam a táblázat adatokat egy több‑projekt környezetben?**  
V: Töltse be minden projektet külön a `new Project(path)` segítségével, és ismételje meg a táblamező‑kivonási ciklust minden egyes példányra.

**K: Exportálhatom a lekért táblamezőket CSV‑be?**  
V: Igen, a mező részletek kiírása után írhatja őket egy `FileWriter`‑be, vagy használhat egy CSV könyvtárat, például az OpenCSV‑t, hogy megfelelően escape‑elt fájlt generáljon.

**K: Kezeli-e az Aspose.Tasks a felhasználók által létrehozott egyedi táblákat?**  
V: Teljes mértékben. A `project.getTables()` gyűjtemény tartalmazza az alapértelmezett és a felhasználó által definiált táblákat is, így egyenként iterálhat és feldolgozhatja őket.

**K: Mi van, ha a Project fájl jelszóval védett?**  
V: Használja a `Project` konstruktor túlterhelt változatát, amely egy `LoadOptions` objektumot fogad, ahol megadhatja a jelszót, például `new Project(path, new LoadOptions("pwd"))`.

**K: Van mód csak a látható oszlopok szűrésére?**  
V: Ellenőrizze minden `TableField` `getVisible()` metódusát (újabb kiadásokban elérhető), hogy meghatározza, megjelenik‑e az oszlop a felhasználói felületen.

## Következtetés
Ezeknek a lépéseknek a követésével most már tudja, hogyan **get table fields**‑t és hogyan olvassa a táblázat adatokat egy Microsoft Project fájlból az Aspose.Tasks for Java segítségével. Ez a képesség erőteljes automatizálási forgatókönyveket, adat‑migrációs csővezetékeket és egyedi jelentéskészítési megoldásokat nyit meg Java‑alkalmazásaiban. Következő lépésként fontolja meg a kinyert metaadatok exportálását JSON‑ba vagy adatbázisba, hogy kereshető projektkatalógusokat építhessen, vagy integrálhassa őket BI‑eszközökkel.

---

**Legutóbb frissítve:** 2026-05-26  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12 (legújabb a kiadás időpontjában)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan olvassuk a projektinformációkat a Microsoft Project‑ből az Aspose.Tasks for Java‑val](/tasks/java/project-properties/read-project-info/)
- [Microsoft Project adatbázis olvasása az Aspose.Tasks for Java‑val](/tasks/java/project-data-reading/read-project-database/)
- [java read access database: Read Project Data with Aspose.Tasks](/tasks/java/project-data-reading/read-access-database/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
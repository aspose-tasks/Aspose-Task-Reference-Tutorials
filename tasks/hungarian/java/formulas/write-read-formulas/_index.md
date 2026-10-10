---
date: 2026-10-10
description: Tanulja meg, hogyan hozhat létre egyedi mezőt az Aspose-ban Java nyelven,
  alkalmazzon dupla feladatköltség képletet, és mentse el a projektfájlt az Aspose.Tasks
  segítségével. Tartalmazza a MS Project képletek olvasását.
keywords:
- create custom field aspose
- double task cost formula
- add custom field formula
- calculate task cost
lastmod: 2026-10-10
linktitle: Egyedi mező képlet példa – Projektfájl mentése
og_description: Tanulja meg, hogyan hozhat létre egyedi mezőt az Aspose-ban Java nyelven,
  alkalmazzon dupla feladatköltség képletet, és mentse el a projektfájlt az Aspose.Tasks
  segítségével. Tartalmazza a MS Project képletek olvasását.
og_image_alt: 'Guide: create custom field aspose and save project file with Aspose.Tasks
  Java'
og_title: Hogyan hozzunk létre egyedi mezőt az Aspose-ban és mentsük el a projektfájlt
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  headline: How to create custom field aspose and save project file
  type: TechArticle
- description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  name: How to create custom field aspose and save project file
  steps:
  - name: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
    text: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
  - name: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
    text: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of MS Project versions, from older
      .mpp formats to the latest releases, covering over 30 file format variations.
    question: Is Aspose.Tasks compatible with all versions of MS Project?
  - answer: Absolutely. The API is designed for seamless integration; just add the
      Aspose.Tasks JAR to your project’s classpath and start using the `Project` class.
    question: Can I integrate Aspose.Tasks into my existing Java project?
  - answer: The library supports most native MS Project formula syntax, including
      arithmetic, logical, and built‑in functions. Complex custom functions may require
      workarounds, but common calculations like **double task cost formula** work
      out of the box.
    question: Are there any limitations to the types of formulas I can create?
  - answer: Yes, the library runs on any platform that supports Java, including Windows,
      Linux, and macOS, and can handle projects up to 2 GB without loading the entire
      file into memory.
    question: Does Aspose.Tasks support multi‑platform deployment?
  - answer: Visit the [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)
      for community help, or open a support ticket if you have a commercial license.
    question: How can I get technical support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- custom field
- Aspose.Tasks
- Java project automation
title: Hogyan hozzunk létre egyedi mezőt az Aspose-ban és mentsük el a projektfájlt
url: /hu/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre egyedi mezőt az Aspose segítségével és mentsük a projektfájlt

## Bevezetés
Ezen az oktatóanyagon keresztül egy **custom field formula example** láthat, amely bemutatja, hogyan **save project file**, hogyan írjon és olvasson MS Project képleteket, és hogyan alkalmazzon **double task cost formula**-t az Aspose.Tasks for Java segítségével. A végére megérti, miért erősek az egyedi mezők, hogyan ágyazhat be számításokat közvetlenül egy projektbe, és hogyan tarthatja meg ezeket a változásokat a későbbi jelentéskészítéshez. Az elsődleges fókusz a **create custom field aspose**-on van, hogy automatizálhassa a költségszámításokat bármely MS Project‑alapú munkafolyamatban.

## Gyors válaszok
- **Mi csinál a „save project file”?** A memóriában lévő összes változást visszaírja egy .mpp fájlba a lemezen.  
- **Hozzáadhatok egyedi mező képleteket?** Igen – létrehozhat egy egyedi mezőt és hozzárendelhet egy képletet, például „double task cost”.  
- **Szükségem van licencre a kód futtatásához?** Egy ingyenes próba verzió elegendő a kiértékeléshez; a termeléshez kereskedelmi licenc szükséges.  
- **Melyik IDE a legjobb?** Bármely Java IDE (IntelliJ IDEA, Eclipse, VS Code) le fogja fordítani a példát.  
- **Az API kompatibilis a legújabb MS Project verzióval?** Az Aspose.Tasks támogatja az összes legújabb .mpp formátumot.

## Mi az a „save project file” az Aspose.Tasks-ben?
A projektfájl mentése azt jelenti, hogy a `Project` objektum aktuális állapotát — beleértve a feladatokat, erőforrásokat és bármely egyedi képletet — egy fizikai Microsoft Project fájlba (`.mpp`) menti. Ez a művelet elengedhetetlen az adatok módosítása után, például egyedi mező hozzáadása vagy feladatköltségek változtatása esetén. A `save` hívás a teljes projektstruktúrát a lemezre írja, így a változások elérhetők a downstream jelentéskészítő eszközök számára.

## Miért adjunk hozzá egy egyedi mezőt és hozzunk létre egy egyedi mező képletet?
Egy egyedi mezőt akkor adunk hozzá, amikor olyan információt kell tárolni, amelyet a beépített mezők nem fednek le. Egy képlet – például egy **double task cost** – csatolása automatizálja a számításokat, megszünteti a kézi frissítéseket, és garantálja, hogy minden alkalommal, amikor az alapköltség változik, a származtatott érték azonnal frissül. Ez a megközelítés csökkenti a hibákat és konzisztensnek tartja az ütemezési adatokat a csapatok között.

## Előfeltételek
Before diving into this tutorial, ensure you have the following prerequisites:

1. **Java Development Kit (JDK)** – Java 8 vagy újabb telepítve a gépén.  
2. **Aspose.Tasks for Java** – Töltse le és telepítse a [Aspose.Tasks Java letöltési oldalról](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Válassza ki a kedvenc Java fejlesztői környezetét (IntelliJ IDEA, Eclipse, VS Code, stb.).  

## Csomagok importálása
A `Project`, `ExtendedAttribute` és a kapcsolódó osztályok a `com.aspose.tasks` névtérben találhatók. Importálja őket a forrásfájl elején, hogy a fordító fel tudja oldani a típusokat.

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 1. lépés: adatkönyvtár beállítása
Adja meg azt a mappát, ahol a MS Project fájljai találhatók. Itt fogja betölteni a forrásfájlt, és később **save project file**-t végrehajtani.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## 2. lépés: projektfájl betöltése
A `Project` osztály egy Microsoft Project fájlt képvisel a memóriában, hozzáférést biztosít a feladatokhoz, erőforrásokhoz és egyedi mezőkhöz. A fájl betöltése manipulálható objektummodellt ad.

```java
Project project = new Project(dataDir + "project.mpp");
```

## 3. lépés: egyedi mező hozzáadása és egyedi mező képlet létrehozása
Ebben a lépésben **hozzáadunk egy egyedi mezőt** “Double Costs” néven, és **létrehozzuk az egyedi mező képletet**, amely a feladat `[Cost]` értékét 2-vel szorozza, ezzel megvalósítva a **double task cost formula**-t. A `setFormula` metódus közvetlenül a projektfájlba ágyazza be a számítást.

```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## 4. lépés: feladat hozzáadása és költség beállítása
Hozzon létre egy új feladatot, majd állítson be egy alapköltséget `100`-ra. Amikor a projekt mentésre kerül, az egyedi mező automatikusan `200`-at fog mutatni a korábban definiált képletnek köszönhetően.

```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## 5. lépés: projektfájl mentése
A `save` metódus az frissített projektet, beleértve az új egyedi mezőt és annak kiszámított értékeit, a `saved.mpp` fájlba írja. Ez megőrzi a **create custom field aspose** változtatásokat minden downstream felhasználó számára.

```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Képlet nem alkalmazva** | Az egyedi mező nem lett hozzáadva a projekt `ExtendedAttributes` gyűjteményéhez. | Győződjön meg arról, hogy a `project.getExtendedAttributes().add(attr);` végrehajtásra kerül a mentés előtt. |
| **Fájl nem található** | Helytelen `dataDir` útvonal. | Ellenőrizze, hogy a könyvtár karakterlánc útvonalelválasztóval (`/` vagy `\\`) végződik. |
| **A költség 0-ként jelenik meg** | A feladat költsége nincs beállítva a mentés előtt. | Hívja meg a `task.set(Tsk.COST, ...)`-t a `project.save` előtt. |

## Gyakran feltett kérdések
**K: Az Aspose.Tasks kompatibilis minden MS Project verzióval?**  
V: Igen, az Aspose.Tasks széles körű MS Project verziókat támogat, a régebbi .mpp formátumoktól a legújabb kiadásokig, több mint 30 fájlformátum változatot lefedve.

**K: Integrálhatom az Aspose.Tasks-et a meglévő Java projektembe?**  
V: Természetesen. Az API-t úgy tervezték, hogy zökkenőmentes integrációt biztosítson; csak adja hozzá az Aspose.Tasks JAR-t a projekt osztályútvonalához, és kezdje el használni a `Project` osztályt.

**K: Vannak korlátozások a létrehozható képletek típusaira?**  
V: A könyvtár a legtöbb natív MS Project képlet szintaxist támogatja, beleértve az aritmetikai, logikai és beépített függvényeket. Összetett egyedi függvényekhez esetleg megoldásokra lehet szükség, de a gyakori számítások, például a **double task cost formula**, alapból működnek.

**K: Az Aspose.Tasks támogatja a többplatformos telepítést?**  
V: Igen, a könyvtár bármely Java‑t támogató platformon fut, beleértve a Windows, Linux és macOS rendszereket, és képes akár 2 GB méretű projekteket kezelni anélkül, hogy a teljes fájlt a memóriába töltené.

**K: Hogyan kaphatok technikai támogatást az Aspose.Tasks-hez?**  
V: Látogassa meg a [Aspose.Tasks közösségi fórumot](https://forum.aspose.com/c/tasks/15) a közösségi segítségért, vagy nyisson egy támogatási jegyet, ha kereskedelmi licence van.

## Összegzés
Ebben a **custom field formula example**-ben bemutattuk, hogyan **save project file**, **add a custom field**, és **create a double task cost formula**, amely automatikusan megduplázza a feladat költségét. A lépések követésével automatizálhatja a számításokat, gazdagíthatja projektadatait, és biztosíthatja, hogy minden változás megmaradjon a jövőbeni jelentéskészítés és elemzés számára. A **create custom field aspose** technika hatékony módja a MS Project kiterjesztésének manuális táblázatmunka nélkül.

---

**Utoljára frissítve:** 2026-10-10  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre MPP fájlt – Üres projekt létrehozása és mentése MPP formátumban az Aspose.Tasks segítségével](/tasks/java/project-configuration/create-save-mpp/)
- [Hogyan hozzunk létre projektet aspose.tasks – Új feladat attribútumainak beállítása](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Kiterjesztett feladat attribútumok olvasása Aspose.Tasks for Java segítségével](/tasks/java/task-properties/extended-task-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
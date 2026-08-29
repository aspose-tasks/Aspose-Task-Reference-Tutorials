---
date: 2026-08-29
description: Tanulja meg, hogyan adjon feladatot egy projekthez Java-ban, hozzon létre
  feladatlistát, és állítson be alapvonalat a Microsoft Project nélkül az Aspose.Tasks
  használatával.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Feladat alapvonal létrehozása az Aspose.Tasks-ben
og_description: Tanulja meg, hogyan adjon feladatot egy projekthez Java-ban, és állítson
  be alapvonalat az Aspose.Tasks használatával. Ez az útmutató lépésről‑lépésre bemutatja
  a kódot, anélkül, hogy a Microsoft Project-re lenne szükség.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Hogyan adjon feladatot egy projekthez Java-ban, és állítson be alapvonalat
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Hogyan adjon feladatot egy projekthez Java-ban, és állítson be alapvonalat
url: /hu/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk feladatot a projekthez Java-ban és állítsunk be alapvonalat

## Bevezetés
Ebben az útmutatóban **add task to project** programozott módon fogsz hozzáadni, generálsz egy Microsoft Project feladat‑alapvonalat, és elmented a fájlt – mindezt anélkül, hogy valaha megnyitnád a Microsoft Projectet. Az Aspose.Tasks for Java egy tiszta Java API‑t biztosít, amely bármely platformon működik, így tökéletes automatizált build pipeline‑okhoz, jelentési szolgáltatásokhoz vagy bármely szerver‑oldali megoldáshoz, amely .mpp fájlok manipulálására van szüksége.

## Gyors válaszok
- **Mit csinál az Aspose.Tasks?** A Java API‑t biztosít Microsoft Project fájlok létrehozásához, olvasásához és szerkesztéséhez, anélkül, hogy a Microsoft Projectre lenne szükség.  
- **Szükségem van a Microsoft Project telepítésére?** Nem, a könyvtár teljesen függetlenül működik.  
- **Melyik Java verzió szükséges?** JDK 8 vagy újabb.  
- **Beállíthatok alapvonalat egyetlen feladathoz?** Igen – hívja a `setBaseline`‑t egy olyan listán, amely csak a kívánt feladatokat tartalmazza.  
- **Szükséges licenc a termeléshez?** Igen, egy kereskedelmi licenc eltávolítja a kiértékelési korlátokat és feloldja az összes funkciót.

## Mi az a feladat‑alapvonal?
A feladat‑alapvonal rögzíti a feladat eredetileg tervezett kezdő‑dátumát, befejező‑dátumát és munkamennyiségét abban a pillanatban, amikor a menetrendet először mentik. Ez a pillanatkép referencia‑pontként szolgál, lehetővé téve a projektmenedzserek számára, hogy a tényleges előrehaladást és költségeket összehasonlítsák a kiindulási tervvel, valamint a teljesítményelemzéshez szükséges eltéréseket számítsák ki.

## Miért használjuk az Aspose.Tasks‑t feladat hozzáadásához a projekthez Java‑ban?
Létrehozhat, módosíthat és alapvonalat állíthat feladatokhoz asztali telepítés nélkül, ami teljesen automatizált munkafolyamatokat tesz lehetővé. Az Aspose.Tasks támogat **50+ bemeneti és kimeneti formátumot**, és képes **százszámú feladatot** tartalmazó projekteket kezelni, miközben a memóriahasználat 200 MB alatt marad, így ideális felhőszolgáltatásokhoz és CI/CD pipeline‑okhoz.

## Előfeltételek
1. **Java Development Kit (JDK)** – telepítse a JDK 8 vagy újabb verziót.  
2. **Aspose.Tasks for Java** – töltse le a könyvtárat a [download link](https://releases.aspose.com/tasks/java/) címről.

## Csomagok importálása
A Aspose.Tasks használatának megkezdéséhez a Java projektben importálja a szükséges csomagokat:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 1. lépés: projektobjektum létrehozása
A `Project` osztály az Aspose.Tasks felső‑szintű objektuma, amely egy Microsoft Project fájlt reprezentál a memóriában. Példányosítva egy üres projektet kap, amelyet feladatokkal, erőforrásokkal és naptárakkal tölthet fel.

```java
Project project = new Project();
```
Itt egy új `Project` objektumot példányosítunk – ez a MS Project fájlt jelenti, amely a feladatlistánkat tartalmazza.

## 2. lépés: feladat hozzáadása a projekthez
A `Task` osztály egy egyedi munkatételt reprezentál a projekt ütemezésében. Minden `Task` rendelkezhet saját időtartammal, kezdő‑dátummal és erőforrás‑kiosztásokkal.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
A `getRootTask()` használatával elérjük a projekt hierarchia gyökerét, és **add task to Microsoft Project**. A `"Task"` karakterlánc a feladat neve; bármilyen leírással helyettesítheti.

## 3. lépés: alapvonal beállítása a megadott feladatokhoz
A `BaselineType` egy felsorolás, amely meghatározza, melyik alapvonal‑helyet (Baseline, Baseline1 … Baseline10) szeretné írni. Feladatlistát átadva csak a kiválasztott elemekre állíthat be alapvonalat.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
A **set baseline without MS Project** érdekében hozzon létre egy listát a beállítani kívánt feladatokról (itt `myList`), és adja át a `setBaseline`‑nek. Töltse fel a `myList`‑et a hozzáadott feladatokkal, ha csak szelektív alapvonalra van szüksége.

## 4. lépés: alapvonal beállítása a teljes projektre
A `setBaseline` a kiválasztott alapvonal‑értékeket minden feladatra a projektben írja.  
Ha egyetlen hívással szeretné az egész projektet alapvonalra állítani, egyszerűen hívja meg a `setBaseline`‑t a kívánt `BaselineType`‑szal.

```java
project.setBaseline(BaselineType.Baseline);
```
Ez a hívás a **minden feladatra** a kiválasztott alapvonal‑értékeket írja a projektben, biztosítva az eredeti ütemezés teljes pillanatképét.

## Hogyan adjunk feladatot a Microsoft Projecthez az Aspose.Tasks használatával
A `add()` egy új gyermekfeladatot hoz létre a megadott szülőfeladat alatt, és visszaadja az újonnan létrehozott `Task` objektumot.  
Feladatot úgy adhat hozzá, hogy a szülő `Task` objektumon (általában a gyökérfeladaton) meghívja a `add()`‑t. A metódus egy új `Task` példányt ad vissza, amelyet tovább konfigurálhat – időtartam, kezdő‑dátum, erőforrások vagy egyéni mezők – mielőtt elmenti a projektfájlt.

## Hogyan állítsunk be alapvonalat MS Project nélkül
Az Aspose.Tasks lehetővé teszi az alapvonal létrehozását teljesen kódból. Válasszon egy `BaselineType`‑t (pl. `BaselineType.Baseline`), és hívja meg a `setBaseline`‑t. Ezt megismételheti a `Baseline1`‑`Baseline10` segítségével, hogy több revíziós alapvonalat tartson fenn, mindezt a Microsoft Project megnyitása nélkül.

## Gyakori problémák és megoldások
- **Az alapvonal nem jelenik meg:** Győződjön meg róla, hogy a `project.save("output.mpp")` hívást a baseline beállítása után végrehajtja (a mentési lépés itt rövidség kedvéért kihagyva).  
- **A feladatlista üresnek tűnik:** Ellenőrizze, hogy a feladatokat a megfelelő szülőhöz adja-e hozzá (`getRootTask()` vagy egy al‑feladathoz).  
- **Verzióeltérés hibák:** Használja a legújabb Aspose.Tasks JAR‑t a kompatibilitás biztosításához az újabb .mpp formátumokkal.

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Tasks for Java‑t Microsoft Project telepítése nélkül?**  
A: Igen, az Aspose.Tasks önállóan működik, és nem igényel Microsoft Projectet a gépen.

**Q: Az Aspose.Tasks for Java kompatibilis a Microsoft Project különböző verzióival?**  
A: Teljes mértékben. A könyvtár támogatja a 2007‑től a legújabb 2024‑es kiadásokig terjedő projektfájlokat.

**Q: Manipulálhatom a projekt erőforrásait az Aspose.Tasks for Java‑val?**  
A: Igen, programozottan hozzáadhat, frissíthet és törölhet erőforrásokat, akárcsak a feladatokat.

**Q: Az Aspose.Tasks for Java támogatja a feladatfüggőségek beállítását?**  
A: Igen, a `TaskLink` osztály segítségével definiálhat előre‑utó kapcsolatrendszereket.

**Q: Elérhető technikai támogatás az Aspose.Tasks for Java‑hoz?**  
A: Igen, segítséget kaphat a [support forum](https://forum.aspose.com/c/tasks/15) oldalon, ahol az Aspose munkatársai és a közösség válaszol a kérdésekre.

## Összegzés
Ezekkel a lépésekkel megtanulta, hogyan **add task to project** Java‑ban, hogyan hozzon létre egy feladatlistát, és hogyan **set baseline without MS Project** az Aspose.Tasks segítségével. Ez a megközelítés egyszerűsíti a projekt‑automatizálást, megszünteti az asztali Project telepítések szükségességét, és teljes programozott irányítást biztosít az ütemezés minden aspektusa felett.

---

**Utolsó frissítés:** 2026-08-29  
**Tesztelve ezzel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre projektet aspose.tasks – Új feladat attribútumok beállítása](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Hogyan állítsuk be az alapvonal időtartamát az Aspose.Tasks for Java-ban](/tasks/java/task-baselines/task-baseline-duration/)
- [Feladatok létrehozása Aspose Java – Feladat tulajdonságok](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
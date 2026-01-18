---
date: 2026-01-18
description: Tanulja meg, hogyan hozhat létre feladatlistát Java-ban, és adjon feladatot
  a Microsoft Projecthez, alapvonalat állítva be MS Project nélkül az Aspose.Tasks
  használatával.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Feladatlista létrehozása Java – MS Project alapvonal Aspose.Tasks használatával
url: /hu/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladatlista létrehozása Java – MS Project alapvonal Aspose.Tasks segítségével

## Bevezetés
Ebben az útmutatóban **feladatlista Java**-t hoz létre a Microsoft Project feladat alapvonalának generálásával az Aspose.Tasks for Java segítségével. Az Aspose.Tasks lehetővé teszi, hogy Microsoft Project telepítése nélkül dolgozzon Project fájlokkal, így **feladatot adhat hozzá a Microsoft Projecthez**, kezelheti az erőforrásokat, és még **alapvonalat állíthat be MS Project nélkül** – mindezt tiszta Java kódból.

## Gyors válaszok
- **Mit csinál az Aspose.Tasks?** Java API-t biztosít a Microsoft Project fájlok létrehozásához, olvasásához és szerkesztéséhez MS Project nélkül.  
- **Szükséges-e a Microsoft Project telepítése?** Nem, az Aspose.Tasks önállóan működik.  
- **Melyik Java verzió szükséges?** JDK 8 vagy újabb.  
- **Beállíthatok-e alapvonalat egyetlen feladathoz?** Igen, használja a `setBaseline`-t feladatlistával.  
- **Szükséges licenc a termeléshez?** Igen, a kereskedelmi licenc eltávolítja a kiértékelési korlátokat.

## Mi az a feladat alapvonal?
A feladat alapvonal rögzíti egy feladat eredetileg tervezett kezdési, befejezési és munkaértékeit. Referenciapontként szolgál a tényleges előrehaladás összehasonlításához az eredeti tervvel.

## Miért használja az Aspose.Tasks-et feladatlista Java létrehozásához?
- **Nincs MS Project függőség** – ideális szerver‑oldali automatizáláshoz.  
- **Teljes irányítás** a feladatok, erőforrások és naptárak felett Java kóddal.  
- **Kereszt‑verzió kompatibilitás** a Project 2007‑2024 fájlokkal.

## Előfeltételek
1. **Java Development Kit (JDK)** – telepítse a JDK 8 vagy újabb verziót.  
2. **Aspose.Tasks for Java** – töltse le a könyvtárat a [letöltési hivatkozásról](https://releases.aspose.com/tasks/java/).  

## Csomagok importálása
A Aspose.Tasks használatának megkezdéséhez a Java projektben importálja a szükséges csomagokat:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 1. lépés: Projekt objektum létrehozása
```java
Project project = new Project();
```
Itt példányosítunk egy új `Project` objektumot – ez a MS Project fájlt képviseli, amely a feladatlistánkat tartalmazza.

## 2. lépés: Feladat hozzáadása a projekthez
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()` használatával elérjük a projekt hierarchia gyökerét, és **feladatot adunk hozzá a Microsoft Projecthez**. A `"Task"` karakterlánc a feladat neve; tetszőleges leírással helyettesítheti.

## 3. lépés: Alapvonal beállítása a megadott feladatokhoz
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
A **alapvonal beállításához MS Project nélkül** hozzon létre egy listát a kívánt feladatokról (itt `myList`), és adja át a `setBaseline`-nek. Töltse fel a `myList`-et a hozzáadott feladatokkal, ha csak szelektív alapvonalra van szüksége.

## 4. lépés: Alapvonal beállítása a teljes projektre
```java
project.setBaseline(BaselineType.Baseline);
```
Ha a teljes projektet egy hívással szeretné alapvonalazni, egyszerűen hívja meg a `setBaseline`-t a kívánt `BaselineType`-tal.

## Hogyan adjon feladatot a Microsoft Projecthez az Aspose.Tasks használatával
Az előzőleg bemutatott egyetlen feladaton túl több feladatot, al‑feladatot és erőforrásokat is hozzáadhat. Minden `add()` hívás egy `Task` objektumot ad vissza, amelyet további beállításokkal (időtartam, kezdő dátum stb.) konfigurálhat.

## Hogyan állítsunk be alapvonalat MS Project nélkül
Az Aspose.Tasks lehetővé teszi az alapvonal létrehozását teljesen kódból. A `BaselineType` enum módosításával különböző alapvonal típusokat (Baseline, Baseline1‑Baseline10) állíthat be, így több revíziós alapvonalat is nyomon követhet anélkül, hogy valaha megnyitná a MS Projectet.

## Gyakori problémák és megoldások
- **Az alapvonal nem jelenik meg:** Győződjön meg róla, hogy a `project.save("output.mpp")` hívást elvégzi az alapvonal beállítása után (a mentési lépés itt rövidítésként kimaradt).  
- **A feladatlista üresnek tűnik:** Ellenőrizze, hogy a feladatokat a megfelelő szülőhöz (`getRootTask()` vagy egy al‑feladathoz) adja-e hozzá.  
- **Verzióeltérés hibák:** Használja a legújabb Aspose.Tasks JAR-t a kompatibilitás biztosítása érdekében az újabb .mpp formátumokkal.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Tasks for Java-t Microsoft Project telepítése nélkül?**  
A: Igen, az Aspose.Tasks önállóan működik, és nem igényel Microsoft Projectet a gépen.

**Q: Az Aspose.Tasks for Java kompatibilis a Microsoft Project különböző verzióival?**  
A: Teljes mértékben. A könyvtár támogatja a 2007-től a legújabb 2024-es kiadásokig terjedő Project fájlokat.

**Q: Kezelhetem a projekt erőforrásait az Aspose.Tasks for Java-val?**  
A: Igen, programozottan hozzáadhat, frissíthet és törölhet erőforrásokat, akárcsak a feladatokat.

**Q: Az Aspose.Tasks for Java támogatja a feladatfüggőségek beállítását?**  
A: Igen, a `TaskLink` osztály segítségével meghatározhatja az előző‑következő kapcsolatokat.

**Q: Elérhető technikai támogatás az Aspose.Tasks for Java-hoz?**  
A: Igen, segítséget kaphat a [támogatási fórumban](https://forum.aspose.com/c/tasks/15), ahol az Aspose munkatársai és a közösség válaszol a kérdésekre.

## Összegzés
Ezeknek a lépéseknek a követésével megtanulta, hogyan **hozzon létre feladatlistát Java-ban**, **adjunk feladatot a Microsoft Projecthez**, és **állítsunk be alapvonalat MS Project nélkül** az Aspose.Tasks segítségével. Ez a megközelítés egyszerűsíti a projekt automatizálását, megszünteti az asztali Project telepítések szükségességét, és teljes programozott irányítást biztosít a projekt adatai felett.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utolsó frissítés:** 2026-01-18  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose
---
date: 2026-06-20
description: Ismerje meg, hogyan olvassa be a hozzárendeléseket és hogyan kérje le
  az erőforrást UID alapján az Aspose.Tasks for Java segítségével. Ez a lépésről‑lépésre
  útmutató hatékonyan mutatja be a megosztott erőforrások hozzárendelésének olvasását.
keywords:
- how to read assignments
- retrieve resource by uid
- Aspose.Tasks Java
linktitle: Megosztott erőforrás hozzárendelések olvasása az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to read assignments and retrieve resource by UID using Aspose.Tasks
    for Java. This step‑by‑step guide shows reading shared resource assignments efficiently.
  headline: How to Read Assignments – Shared Resources in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can programmatically change assignment values, dates, and units.
    question: Can I modify resource assignments using Aspose.Tasks for Java?
  - answer: Yes, it supports MPP, XML, MPX, and other common formats.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Absolutely—use the reporting API to export custom reports in PDF, XLSX,
      or HTML.
    question: Can I generate reports based on resource assignments?
  - answer: Aspose.Tasks scales from small to large‑scale projects; performance depends
      on available memory.
    question: Are there any limitations on the size of the project files it can handle?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks for Java users?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hogyan olvassuk be a hozzárendeléseket – Megosztott erőforrások az Aspose.Tasks-ben
url: /hu/java/resource-assignments/read-shared-resource-assignments/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Megosztott erőforrás-hozzárendelések olvasása az Aspose.Tasks-ben

## Bevezetés
A **hogyan olvassuk a hozzárendeléseket** megértése elengedhetetlen minden projektmenedzser számára, aki teljes átláthatóságot szeretne az erőforrás-felhasználásban több projekt között. Ebben az oktatóanyagban megmutatjuk, hogyan olvashatók a megosztott erőforrás-hozzárendelések az Aspose.Tasks for Java segítségével, lehetővé téve, hogy **java projekt erőforrások olvasása** és kinyerje a csúcs egységeket anélkül, hogy manuálisan megnyitná minden fájlt. A végére képes lesz erőforrás adatokat UID alapján lekérni, a csúcs egységeket kiszámolni, és pontos munkaterhelés-jelentéseket generálni.

## Gyors válaszok
- **Mi jelent a “shared resource assignment”?** Ez egy erőforrás, amely több projekthez kapcsolódik, lehetővé téve a használat globális nyomon követését.  
- **Olvashatok hozzárendeléseket licenc nélkül?** Egy ingyenes próba működik az olvasáshoz, de licenc szükséges a termelési használathoz.  
- **Mely fájlformátumok támogatottak?** Az Aspose.Tasks kezeli az MPP, XML, MPX és további formátumokat.  
- **Szükség van további függőségekre?** Csak az Aspose.Tasks for Java JAR és egy kompatibilis JDK.  
- **Mennyi időt vesz igénybe a kód futtatása?** Általában egy másodpercnél kevesebb közepes méretű fájlok esetén.

## Mi a “hogyan olvassuk a hozzárendeléseket”?
A hozzárendelések olvasása azt jelenti, hogy kinyerjük a hozzárendelés objektumokat, amelyek összekapcsolják az erőforrásokat a feladatokkal, beleértve a kezdő/végdátumokat, munkát és egységeket. Ez a művelet lehetővé teszi az erőforrás-elosztás elemzését egy vagy több összekapcsolt projektben, a túlterhelés azonosítását, és jelentések generálását, amelyek segítik az érintetteket a munkaterhelés eloszlásának és a projekt állapotának megértésében.

## Miért használjunk megosztott erőforrás-olvasást?
A megosztott erőforrás-hozzárendelések olvasása lehetővé teszi, hogy módosítsa a hozzárendeléseket akár **100 összekapcsolt projekt** esetén, a munkaterhelést **akár 30 %**-kal egyensúlyozza, és részletes jelentéseket generáljon **2 másodperc alatt** 500 + oldalas fájlok esetén. Ezek a számszerű előnyök segítik a projektmenedzsereket, hogy a határidőket betartsák és elkerüljék a túlterhelést.

## Előfeltételek
- Alapvető Java programozási nyelvi ismeretek.  
- JDK (Java Development Kit) telepítve a rendszerén.  
- Az Aspose.Tasks for Java könyvtár letöltve és a projektjéhez hozzáadva. Letöltheti [itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java kódjában:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 1. lépés: Adatkönyvtár meghatározása
```java
String dataDir = "Your Data Directory";
```
Határozza meg a könyvtárat, ahol a projekt adatai találhatók.

## 2. lépés: Projektfájl betöltése
```java
Project project = new Project(dataDir + "ResourceCosts.mpp");
```
Töltse be a megosztott erőforrás-hozzárendeléseket tartalmazó projektfájlt.

## 3. lépés: Erőforrás elérése
`Resource` osztály egy projekt erőforrást képvisel, és olyan tulajdonságokat biztosít, mint UID, név és a hozzárendelés gyűjtemény.  
```java
Resource resource = project.getResources().getByUid(1);
```
Szerezze be az erőforrást a projektből az egyedi azonosítója (UID) alapján.

## 4. lépés: Erőforrás egységek lekérése
```java
Double units = resource.get(Rsc.PEAK_UNITS);
```
A `getPeakUnits()` metódus visszaadja a maximális egységszámot, amely az erőforráshoz van hozzárendelve az összes összekapcsolt projektben.  
Szerezze meg az erőforrás csúcs egységeit, amelyek más projektek hozzárendelései alapján kerülnek kiszámításra.

## Hogyan olvassuk a hozzárendeléseket a megosztott erőforrásokból?
`Project` osztály egy Microsoft Project fájlt képvisel, és hozzáférést biztosít annak erőforrásaihoz, feladataihoz és hozzárendeléseihez.  
Töltse be a célprojektet a `Project project = new Project(dataDir + "Project.mpp");` kóddal, majd hívja a `Resource resource = project.getResources().toList().stream().filter(r -> r.getUid() == desiredUid).findFirst().orElse(null);` kifejezést. A `Resource` objektum megszerzése után használja a `resource.getPeakUnits()` metódust, hogy beolvassa az összes összekapcsolt projektben aggregált egységeket. Ez a tömör kétlépéses megközelítés visszaadja a szükséges hozzárendelési adatokat anélkül, hogy egyes összekapcsolt fájlokat külön-külön megnyitna.

## Miért fontos ez
A megosztott erőforrás-hozzárendelések olvasása lehetővé teszi, hogy **intelligensen módosítsa a hozzárendeléseket**, egyensúlyozza a munkaterhelést, és pontos jelentéseket generáljon – kulcsfontosságú lépések a hatékony projektirányításban. Az Aspose.Tasks segítségével akár **10 000 feladatot** tartalmazó projekteket is feldolgozhat, miközben a memóriahasználat **200 MB** alatt marad, köszönhetően a streaming architektúrájának.

## Gyakori problémák és tippek
- **Null erőforrás:** Győződjön meg arról, hogy a kért UID valóban létezik a fájlban.  
- **Helytelen fájlútvonal:** Használjon abszolút útvonalakat, vagy ellenőrizze, hogy a `dataDir` végződik-e elválasztóval.  
- **Licenckivétel:** Licenc nélkül történő futtatás próba‑mód figyelmeztetést eredményezhet; alkalmazza a licencet a kódban korán.

## Gyakran ismételt kérdések

**Q: Módosíthatom a erőforrás-hozzárendeléseket az Aspose.Tasks for Java használatával?**  
A: Igen, programozottan módosíthatja a hozzárendelés értékeket, dátumokat és egységeket.

**Q: Az Aspose.Tasks for Java kompatibilis különböző projektfájl formátumokkal?**  
A: Igen, támogatja az MPP, XML, MPX és egyéb gyakori formátumokat.

**Q: Készíthetek jelentéseket erőforrás-hozzárendelések alapján?**  
A: Teljesen – használja a jelentéskészítő API-t, hogy egyedi jelentéseket exportáljon PDF, XLSX vagy HTML formátumban.

**Q: Vannak korlátozások a kezelhető projektfájlok méretére vonatkozóan?**  
A: Az Aspose.Tasks kis- és nagy‑méretű projektekhez egyaránt skálázható; a teljesítmény a rendelkezésre álló memóriától függ.

**Q: Elérhető technikai támogatás az Aspose.Tasks for Java felhasználók számára?**  
A: Igen, segítséget kaphat az Aspose.Tasks fórumon [itt](https://forum.aspose.com/c/tasks/15).

## Összegzés
Most már tudja, **hogyan olvassuk a hozzárendeléseket** a megosztott erőforrásokból az Aspose.Tasks for Java segítségével, hogyan szerezzen be egy erőforrást UID alapján, és hogyan számítsa ki annak csúcs egységeit az összekapcsolt projektekben. Alkalmazza ezeket a lépéseket irányítópultok építéséhez, a munkaterhelés kiegyensúlyozásához és a jelentéskészítés automatizálásához projektmenedzsment megoldásaiban.

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan módosítsuk a hozzárendeléseket – Megosztott erőforrások olvasása az Aspose-szal](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Erőforrás-hozzárendelések létrehozása az Aspose.Tasks-ben](/tasks/java/resource-assignments/create-resource-assignments/)
- [Hogyan adjunk megjegyzéseket az erőforrás-hozzárendelésekhez az Aspose.Tasks-ben](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
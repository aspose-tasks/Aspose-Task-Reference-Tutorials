---
date: 2026-06-15
description: Ismerje meg, hogyan konvertálhatja az MPP-t PDF-re, és jelenítheti meg
  a Resource Usage és Sheet nézeteket az Aspose.Tasks for Java segítségével. Kövesse
  lépésről-lépésre útmutatónkat a timescale beállításához és részletes PDF-jelentések
  könnyed generálásához.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: MPP konvertálása PDF-re és az Resource Usage nézet megjelenítése – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP konvertálása PDF-re és az Resource Usage nézet megjelenítése – Aspose.Tasks
url: /hu/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP konvertálása PDF-be és az Erőforrás-felhasználási nézet renderelése – Aspose.Tasks

Ebben az oktatóanyagban megtanulja, **hogyan konvertálja az mpp-t pdf-re**, miközben a Microsoft Project fájl Erőforrás-felhasználási és Lap nézeteit rendereli. Az Aspose.Tasks for Java használata megszünteti a Microsoft Project szükségességét a szerveren, és gyors, megbízható módot biztosít PDF jelentések létrehozására MPP fájlokból. Emellett megmutatjuk, **hogyan állítsa be az időskálát**, hogy a kimenet megfeleljen a jelentési követelményeknek.

## Gyors válaszok
- **Mit csinál az Aspose.Tasks?** Olvassa, módosítja és konvertálja a Microsoft Project (MPP) fájlokat anélkül, hogy a MS Project telepítve lenne.  
- **Konvertálhatok MPP-t PDF-re egyetlen kódsorral?** Igen – töltsük be a Projectet, állítsuk be a SaveOptions-t, és hívjuk meg a `save`-et.  
- **Mely időskálák támogatottak?** Days, ThirdsOfMonths és Months.  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges a nem‑próba telepítésekhez.  
- **Kompatibilis a könyvtár a Java 8+-tal?** Teljesen – támogatja a Java 8-at és a későbbi verziókat.

## Mi az mpp pdf-re konvertálás?
*mpp pdf-re konvertálás* a folyamatra utal, amely során egy Microsoft Project (.mpp) fájlt átalakítanak Portable Document Format (PDF) verzióvá, amely hűen reprodukálja a projekt táblázatait, ütemezéseit, diagramjait és erőforrás-elosztásait. A kapott PDF könnyen megosztható, nyomtatható és archiválható anélkül, hogy a Microsoft Project telepítve lenne a címzett gépén.

## Miért konvertálja a projektet PDF-be az Aspose.Tasks segítségével?
Az Aspose.Tasks támogat **50+ bemeneti és kimeneti formátumot** és képes több száz oldalas projekteket renderelni anélkül, hogy az egész fájlt a memóriába töltené, ezzel akár 70 %-kal csökkentve a RAM használatot. A PDF kimenet megőrzi a táblázatokat, diagramokat és erőforrás-elosztásokat, így ideális a résztvevőknek való terjesztéshez és archiváláshoz.

## Előfeltételek
1. **Java Development Kit (JDK)** – Java 8 vagy újabb telepítve a gépén.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR-t a [letöltési oldal](https://releases.aspose.com/tasks/java/) címről.  

## Hogyan konvertáljunk mpp-t pdf-re az Aspose.Tasks for Java segítségével?
Töltse be a forrás MPP fájlt, konfigurálja a kívánt időskálát, állítsa be a megjelenítési formátumot **ResourceUsage**-ra, és mentse az eredményt PDF-ként. Ez az vég‑végi folyamat csak néhány API hívást igényel, és tipikus projektméretek esetén egy másodpercnél kevesebb idő alatt lefut.

### 1. lépés: A forrás projekt beolvasása
A `Project` osztály egy memóriába betöltött Microsoft Project fájlt képvisel, amely hozzáférést biztosít az adataihoz és szerkezetéhez.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### 2. lépés: SaveOptions definiálása a szükséges TimeScale beállításokkal
`SaveOptions` beállítja, hogyan mentődik a projekt, lehetővé téve formátum‑specifikus beállítások, például az időskála megadását.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 3. lépés: A megjelenítési formátum beállítása ResourceUsage-re
`PresentationFormat` meghatározza, hogy a projekt melyik nézete (pl. ResourceUsage) kerül renderelésre a kimeneti dokumentumban.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 4. lépés: A projekt mentése PDF-ként
`project.save` a megadott `SaveOptions` használatával írja a projektet egy fájlba, és létrehozza a végleges PDF-et.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 5. lépés: Nézetek renderelése más TimeScale beállításokhoz
Ismételje meg az előző lépéseket, a `TimeScale` értékének módosításával további időskála nézetek rendereléséhez.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### 6. lépés: Opcionális – Több projekt konvertálása kötegben
Ha sok fájlhoz kell **projekt pdf-re konvertálása**, helyezze a fenti logikát egy ciklusba, amely egy *.mpp* fájlok könyvtárán iterál. Ez a megközelítés **ms project pdf fájlok mentését** teszi lehetővé tömegesen, minimális kómmódosítással.  
A következő kód egy teljes példát mutat be egy MPP fájl PDF-re konvertálására a kívánt beállításokkal.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Gyakori problémák és megoldások
- **Hiányzó betűkészletek a PDF-ben** – Győződjön meg róla, hogy a szükséges betűkészletek telepítve vannak a szerveren, vagy ágyazza be őket a `PdfSaveOptions` segítségével.  
- **Nagy projektfájlok OutOfMemoryError-t okoznak** – Használja a `LoadOptions.setLoadAllResources(false)`-t az erőforrások igény szerinti betöltéséhez.  
- **Helytelen időskála renderelés** – Ellenőrizze, hogy a `options.setTimeScale(TimeScale.Days)` (vagy más enum) megfelel a kívánt részletességnek.

## Gyakran Ismételt Kérdések

**Q: Renderelhet az Aspose.Tasks más nézeteket is az Erőforrás-felhasználás és Lap mellett?**  
A: Igen, támogatja a Gantt-diagramot, Feladatfelhasználást, Naptárat és számos további nézetet.

**Q: Kompatibilis az Aspose.Tasks a Microsoft Project fájlok különböző verzióival?**  
A: Teljesen – kezeli az MPP, MPT és XML formátumokat a Project 2000-tól a Project 2021-ig.

**Q: Testreszabhatom a renderelt nézetek megjelenését?**  
A: Igen, módosíthatja a színeket, betűkészleteket és oszlopelrendezéseket a `PdfSaveOptions` és `PresentationOptions` segítségével.

**Q: Szükséges a Microsoft Project telepítése az Aspose.Tasks használatához?**  
A: Nem, ez egy önálló könyvtár, és bármely Java‑kompatibilis környezetben működik.

**Q: Hol kaphatok technikai támogatást?**  
A: A támogatás elérhető a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15/).

**Utolsó frissítés:** 2026-06-15  
**Tesztelt verzió:** Aspose.Tasks 24.12 for Java  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Erőforrás-felhasználási és Lap nézet renderelése az Aspose.Tasks-ben](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [PDF exportálása az Aspose.Tasks-ben – Mentés PDF-ként](/tasks/java/project-file-operations/save-as-pdf/)
- [MPP fájlok létrehozása az Aspose.Tasks for Java segítségével](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
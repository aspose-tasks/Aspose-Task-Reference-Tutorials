---
date: 2026-05-20
description: Ismerje meg, hogyan exportálhatja a projektet PDF-be, csökkentheti a
  lábléc hézagát, és mentheti a projektet képként az Aspose.Tasks for Java használatával.
  Optimalizálja MS Project elrendezését könnyedén.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Projekt exportálása PDF-be és a feladatlista és a lábléc közötti hézag
  csökkentése az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Projekt exportálása PDF-be és a feladatlista és a lábléc közötti hézag csökkentése
  az Aspose.Tasks-ben
url: /hu/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt exportálása PDF-be és a feladatlista és lábléc közötti rés szűkítése az Aspose.Tasks-ben

## Bevezetés  
Ebben az útmutatóban megtudja, **hogyan exportálja a projektet PDF-be**, miközben csökkenti a nem kívánt helyet a feladatlista és a lábléc között a Microsoft Project fájlokban. A útmutató végére képes lesz tiszta PDF-eket, PNG képeket és HTML oldalakat generálni kompakt elrendezéssel az Aspose.Tasks for Java segítségével. Lépésről lépésre végigvezetjük a folyamatot, és meg fogja érteni, miért fontos ez a professzionális jelentéskészítésben.

## Gyors válaszok  
- **Mit jelent a „projekt exportálása PDF-be”?** Átalakít egy MPP fájlt PDF dokumentummá, megőrizve a feladatokat, ütemterveket és a formázást.  
- **Miért csökkentse a lábléc részt?** A kisebb rés szorosabb, professzionálisabb megjelenésű jelentéseket eredményez, különösen nyomtatott vagy weben megtekintett dokumentumok esetén.  
- **Menthetem a projektet képként is?** Igen – az Aspose.Tasks támogatja a PNG, JPEG és más képfájlformátumokat.  
- **Szükségem van speciális licencre?** Elérhető egy ingyenes próba, a termelési használathoz kereskedelmi licenc szükséges.  
- **Melyik Java verzió szükséges?** A Java 8 vagy újabb verzió működik a jelenlegi Aspose.Tasks könyvtárral.  

## Mi a „projekt exportálása PDF-be”?  
A projekt PDF-be exportálása átalakítja a belső MPP struktúrát egy hordozható dokumentummá, amely bármely eszközön megnyitható a Microsoft Project nélkül. Ideális állapotjelentések, érintett felek frissítéseinek vagy projekttervek archiválásának megosztásához. Megőrzi az eredeti elrendezést, színeket és feladat-hierarchiát, biztosítva, hogy a PDF azonos legyen a forrásfájllal.

## Miért csökkentse a lábléc részt?  
Az alapértelmezett lábléc rés felesleges üres helyet adhat hozzá, ami oldaltördelési problémákat és egyensúlyhiányt okoz. A rés csökkentése biztosítja, hogy a tartalom hatékonyan használja ki az oldalt, így a végső PDF vagy kép olvashatóbb lesz. A szorosabb elrendezés csökkenti az összes oldalszámot, ami alacsonyabb nyomtatási költségeket és jobb képernyőnavigációt eredményez.

## Hogyan csökkentse a feladatlista és a lábléc közötti részt?  
`setReduceFooterGap` egy Boolean tulajdonság, amely az exportálás során szabályozza a lábléc távolságát.  
Az Aspose.Tasks egy `setReduceFooterGap(true)` opciót biztosít a kép, PDF és HTML mentési műveletekhez. Ennek a jelzőnek az engedélyezése azt mondja a motornak, hogy tömörítse a helyet az utolsó feladatsor és az oldal lábléce között. Ha true-ra van állítva, a renderelő automatikusan levágja a margót anélkül, hogy bármely feladat adatot levágna, így tisztább oldalelrendezést eredményez.

## Projekt mentése képként az Aspose.Tasks segítségével  
`ImageSaveOptions` beállítja, hogyan renderelődik egy projekt képfájlba.  
Az `ImageSaveOptions` osztály lehetővé teszi, hogy egy ütemterv pillanatfelvételét PNG, JPEG vagy BMP formátumban exportálja. Ha engedélyezi a `setReduceFooterGap(true)`-t is, a létrehozott kép a kompakt PDF elrendezést tükrözi, tiszta vizuális anyagot biztosítva prezentációkhoz vagy műszerfalakhoz.

## Java projekt exportálása PDF-be  
A következő szakaszok egy teljes **java project export** munkafolyamatot mutatnak be, az MPP fájl betöltésétől három különböző formátumban való mentésig.

## Előkövetelmények
Mielőtt elkezdenénk, győződjön meg arról, hogy rendelkezik a következő előkövetelményekkel:
1. Java Development Kit (JDK) – 8-as vagy újabb verzió.  
2. Aspose.Tasks for Java Library – töltse le [innen](https://releases.aspose.com/tasks/java/).  

## Csomagok importálása  
Before diving into the coding part, let's import the necessary packages:

```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 1. lépés: Adja meg az adatkönyvtár útvonalát  
```java
String dataDir = "Your Data Directory";
```  
Győződjön meg róla, hogy a "Your Data Directory" helyére a tényleges adatkönyvtár útvonalát helyettesíti, ahol a Microsoft Project fájl (`HomeMovePlan.mpp` ebben a példában) található.

## 2. lépés: Olvassa be az MPP fájlt  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Ez a kódsor beolvassa a `HomeMovePlan.mpp` nevű Microsoft Project fájlt.

## 3. lépés: ImageSaveOptions beállítása (Projekt mentése képként)  
`ImageSaveOptions` beállítja, hogyan renderelődik egy projekt képfájlba.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Állítsa be a kép mentési opciókat, a `ReduceFooterGap` értékét `true`-ra állítva csökkentse a feladatlista és a lábléc közötti részt.

## 4. lépés: Mentés képként  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Mentse a projektet képként a beállított opciókkal.

## 5. lépés: PdfSaveOptions beállítása (Projekt exportálása PDF-be)  
`PdfSaveOptions` meghatározza a projekt PDF formátumba exportálásának beállításait.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Határozza meg a PDF mentési opciókat, biztosítva, hogy a `ReduceFooterGap` értéke `true` legyen.

## 6. lépés: Mentés PDF-be  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Mentse a projektet PDF-be a beállított opciókkal.

## 7. lépés: HtmlSaveOptions beállítása  
`HtmlSaveOptions` szabályozza a projekt HTML-re konvertálását, beleértve a stílus- és elrendezési beállításokat.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Adja meg a HTML mentési opciókat, a `ReduceFooterGap` értékét `true`-ra állítva.

## 8. lépés: Mentés HTML-ként  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Mentse a projektet HTML fájlként a beállított opciókkal.

## Általános felhasználási esetek és tippek  
- **Érintett felek jelentése:** Exportáljon PDF-be a csökkentett lábléc réssel, hogy a jelentések tömörek és nyomtatóbarátok legyenek.  
- **Műszerfal pillanatképek:** Használja a kép exportot, ha gyors vizuális anyagra van szükség a Power BI vagy Confluence számára.  
- **Webes közzététel:** A HTML export megőrzi az interaktivitást, és közvetlenül beágyazható intranet portálokba.  
- **Pro tipp:** Nagyon nagy projektek esetén növelje az `ImageSaveOptions`-ban a `Resolution` értékét 300 dpi-re a tisztaság megőrzése érdekében, miközben továbbra is élvezheti a csökkentett rés előnyeit.

## Gyakran ismételt kérdések (továbbiak)

**Q: Hogyan befolyásolja a lábléc rés csökkentése az oldaltördelést?**  
A: Csökkenti az egyes oldalak alján lévő üres helyet, lehetővé téve, hogy több feladat férjenek el egy oldalon, és csökkenti az összes oldalszámot.

**Q: Alkalmazhatom ugyanazt a rés‑csökkentő beállítást csak egyetlen oldalra?**  
A: Igen, a `setRenderToSinglePage(true)` beállítással az `ImageSaveOptions`-ban szabályozhatja az oldaltördelést, miközben továbbra is csökkenti a részt.

**Q: Elérhető a `setReduceFooterGap` opció más kimeneti formátumokhoz is?**  
A: Jelenleg támogatott PNG, PDF és HTML exportokhoz. Más formátumok esetén manuálisan kell a elrendezést módosítani.

**Q: Mi van, ha a projektem egyéni mezőket tartalmaz – megmaradnak?**  
A: Az összes egyéni mező megmarad az exportálás során; az elrendezés módosításai csak a távolságot érintik, az adatot nem.

**Q: Kezeli a könyvtár hatékonyan a nagy projekteket?**  
A: Az Aspose.Tasks adatfolyamot használ, és képes több száz oldalas MPP fájlokat feldolgozni a teljes fájl memóriába betöltése nélkül; azonban elegendő heap memóriát kell biztosítani a nagy felbontású képek exportálásakor.

**Legutóbb frissítve:** 2026-05-20  
**Tesztelve a következővel:** Aspose.Tasks 24.11 for Java  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Projekt mentése képként – 24bppRgb formátum az Aspose.Tasks segítségével](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Projekt mentése sablonként, CSV‑ként és szövegként az Aspose.Tasks for Java segítségével](/tasks/java/project-file-operations/save-csv-text-template/)
- [Hogyan hozzunk létre MPP fájlt – Üres projekt létrehozása és mentése MPP formátumban az Aspose.Tasks segítségével](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
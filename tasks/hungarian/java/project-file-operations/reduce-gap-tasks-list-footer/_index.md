---
title: Az Aspose.Tasks feladatlista és lábléc közötti különbség csökkentése
linktitle: Az Aspose.Tasks feladatlista és lábléc közötti különbség csökkentése
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan csökkentheti az MS Project feladatlisták és láblécek közötti különbséget az Aspose.Tasks for Java segítségével. Könnyedén optimalizálhatja a projektdokumentum elrendezését.
weight: 10
url: /hu/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az Aspose.Tasks feladatlista és lábléc közötti különbség csökkentése

## Bevezetés
Ebben az oktatóanyagban a feladatlista és a lábléc közötti különbség csökkentésével foglalkozunk a Microsoft Project-fájlokban az Aspose.Tasks for Java használatával. Ezen lépések követésével könnyedén optimalizálhatja projektdokumentumai elrendezését.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java Library: Töltse le és foglalja bele a projektébe az Aspose.Tasks for Java könyvtárat. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Mielőtt belemerülnénk a kódolási részbe, importáljuk a szükséges csomagokat:
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
## 1. lépés: Adja meg az elérési utat az adattárhoz
```java
String dataDir = "Your Data Directory";
```
 Mindenképpen cserélje ki`"Your Data Directory"` a tényleges adatkönyvtár elérési útjával, ahol a Microsoft Project fájl (`HomeMovePlan.mpp` ebben a példában) található.
## 2. lépés: Olvassa el az MPP fájlt
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Ez a kódsor a Microsoft Project nevű fájlt olvassa`HomeMovePlan.mpp`.
## 3. lépés: Állítsa be az ImageSaveOptions beállításait
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Konfigurálja a képmentési opciókat, beállításokat`ReduceFooterGap` nak nek`true` hogy csökkentse a szakadékot a feladatlista és a lábléc között.
## 4. lépés: Mentés képként
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Mentse a projektet képként a konfigurált opciókkal.
## 5. lépés: Állítsa be a PdfSaveOptions beállításait
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Határozza meg a PDF mentési beállításokat, és gondoskodjon a beállításról`ReduceFooterGap` nak nek`true`.
## 6. lépés: Mentés PDF-ként
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Mentse a projektet PDF-ként a konfigurált beállításokkal.
## 7. lépés: Állítsa be a HtmlSaveOptions beállításait
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // igazra állítva
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Adja meg a HTML mentési opciókat, beállításokat`ReduceFooterGap` nak nek`true`.
## 8. lépés: Mentés HTML-ként
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Mentse a projektet HTML-fájlként a konfigurált opciókkal.

## Következtetés
Összefoglalva, a feladatlista és a lábléc közötti különbség csökkentése a Microsoft Project-fájlokban egy egyszerű folyamat az Aspose.Tasks for Java segítségével. Az oktatóanyagban ismertetett lépések követésével hatékonyan optimalizálhatja projektdokumentumai elrendezését.

## GYIK

### K: Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?

V: Az Aspose.Tasks támogatja a Microsoft Project 2003-2019 formátumokat, biztosítva a kompatibilitást a különböző verziók között.

### K: Testreszabhatom a lábléc megjelenését a projektdokumentumaimban?

V: Igen, az Aspose.Tasks kiterjedt lehetőségeket kínál a láblécek megjelenésének testreszabására, beleértve a hézagok csökkentését és a tartalomelhelyezés módosítását.

### K: Az Aspose.Tasks támogatja a projektek mentését a PNG-től, PDF-től és HTML-től eltérő formátumban?

V: Igen, az Aspose.Tasks a formátumok széles skáláját támogatja, többek között az XLSX-et, az XML-t és az MPP-t.

### K: Elérhető az Aspose.Tasks próbaverziója?

 V: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).

### K: Hol kaphatok támogatást, ha problémákat tapasztalok az Aspose.Tasks használata során?

 V: Segítséget kaphat az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-05-26
description: Ismerje meg, hogyan exportálhatja az MPP-t CSV-be, mentheti a projektet
  sablonként, és konvertálhatja az MPP-t szöveggé az Aspose.Tasks for Java használatával.
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: MPP exportálása CSV-be, szövegbe és sablonba az Aspose.Tasks Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MPP exportálása CSV-be, szövegbe és sablonba az Aspose.Tasks Java segítségével
url: /hu/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP exportálása CSV‑be, szövegbe és sablonba az Aspose.Tasks for Java‑val

## Bevezetés
Ezen az útmutatón keresztül megtudja, **hogyan exportálja az MPP‑t CSV‑be**, hogyan hozhat létre újrahasználható projekt sablonokat, és hogyan generálhat egyszerű szöveges kiextraktumokat az Aspose.Tasks Java könyvtár segítségével. Akár jelentéskészítő csővezeték építésén, projekt létrehozásának automatizálásán, vagy más rendszerekkel való integráción dolgozik, ezek a lépések a nyers MPP‑fájlt a szükséges kimenetre viszik — gyorsan és a Microsoft Project telepítése nélkül.

## Gyors válaszok
- **Exportálhatok MPP‑t CSV‑be?** Igen – hívja a `project.save("output.csv", SaveFileFormat.CSV)`.
- **Hogyan exportálhatok egyszerű szövegbe?** Használja a `SaveFileFormat.TEXT`‑t a `save` metódussal.
- **Mit csinál a „save project as template”?** Létrehoz egy `.mpt` fájlt, amely eltávolítja a dátumokat és az alapvonalakat, csak a vázlatot hagyja meg.
- **Szükségem van licencre?** A próbaverzió értékelésre használható; egy kereskedelmi licenc eltávolítja az értékelési korlátokat.
- **Melyik Java verzió szükséges?** A Java 8 vagy újabb teljes mértékben támogatott.

## Mi az a „save project as template”?
A projekt sablonként (`.mpt`) való mentése rögzíti a struktúrát, a feladat hierarchiát és az erőforrás hozzárendeléseket, miközben eltávolítja a tényleges kezdő‑ és befejezési dátumokat valamint az alapvonal adatokat. Ez a sablont ideálissá teszi egy szabványos projekt elrendezés több új projektben való újrahasználatához. Megőrzi az összes egyéni mezőt, költségárat és hozzárendelési részletet, biztosítva, hogy a sablon bármely új projektre alkalmazható legyen a lényeges konfiguráció elvesztése nélkül.

## Miért használja az Aspose.Tasks for Java‑t?
Exportáljon MPP‑t CSV‑be, szövegbe vagy sablonba közvetlenül Java‑ból a Microsoft Project nélkül. Az Aspose.Tasks **20+ Microsoft Project verziót** (2000‑2024) támogat, és akár **500 MB**‑os fájlokat is képes memóriatakarékos módban feldolgozni, ami ideálissá teszi szerver‑oldali automatizáláshoz, CI csővezetékekhez és kereszt‑platformos segédprogramokhoz.

## Előkövetelmények
- Java Development Kit 8 vagy újabb telepítve.  
- Aspose.Tasks for Java könyvtár hozzáadva a projekthez – töltse le [itt](https://releases.aspose.com/tasks/java/).  
- Más Aspose könyvtárakat is felfedezhet [itt](https://releases.aspose.com/).  
- Alapvető Java és Maven/Gradle projektkonfigurációs ismeretek.

## Csomagok importálása
A `Project` osztály az Aspose.Tasks központi objektuma, amely egy Microsoft Project fájlt reprezentál a memóriában. A könyvtár build fájlba való hozzáadása után importálja a szükséges osztályokat:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Projekt mentése CSV‑ként (Export MPP to CSV)
Az MPP fájl CSV‑be exportálása lehetővé teszi, hogy a feladat adatokat Excel‑be, Power BI‑ba vagy bármely elemző platformra továbbítsa.

### 1. lépés: A projekt betöltése
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 2. lépés: Mentés CSV‑ként
`SaveFileFormat.CSV` azt mondja az Aspose.Tasks‑nek, hogy CSV formátumban adja ki a projektet.  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Projekt mentése szövegként (Hogyan exportáljunk szöveget)
Az egyszerű szövegfájl gyors, ember által olvasható kiírást biztosít a feladatokról, erőforrásokról és hozzárendelésekről.

### 1. lépés: A projekt betöltése
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 2. lépés: Mentés szövegként
`SaveFileFormat.TEXT` utasítja a könyvtárat, hogy generáljon egy egyszerű szöveges ábrázolást a projektről.  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Projekt mentése sablonként (Projekt sablon létrehozása Java‑ban)

### 1. lépés: A projekt betöltése
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 2. lépés: Sablon beállítások megadása
Használja a `Project.save`‑t a `SaveFileFormat.MPT` (vagy `SaveFileFormat.TEMPLATE`) paraméterrel, hogy létrehozzon egy sablonfájlt, amely eltávolítja a dátumokat és az alapvonalakat.  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### 3. lépés: Mentés sablonként
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Gyakori problémák és tippek
- **Fájl nem található:** Ellenőrizze a `YourProject.mpp` elérési útját, vagy használjon abszolút útvonalat.  
- **Licenc kivételek:** Érvényes licenc nélkül a könyvtár értékelési módban fut, és vízjelet adhat hozzá. Alkalmazza a licencet korán (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Nagy projektek:** 200 MB-nál nagyobb fájlok esetén növelje a JVM heap‑et (`-Xmx2g`), hogy elkerülje a `OutOfMemoryError` hibát.  
- **Teljesítmény:** Sok projekt konvertálásakor, ahol lehetséges, használjon egyetlen `Project` példányt újra, hogy csökkentse az objektum‑létrehozási terhelést.

## Összegzés
Bemutattuk, hogyan **exportálhatja az MPP‑t CSV‑be**, **konvertálhatja az MPP‑t szöveggé**, és **mentheti a projektet sablonként** az Aspose.Tasks for Java segítségével. Ezek a lehetőségek lehetővé teszik a jelentéskészítés automatizálását, szabványos projektvázlatok létrehozását, és a projektadatok integrálását bármely downstream rendszerbe — anélkül, hogy a Microsoft Project telepítve lenne.

## Gyakran ismételt kérdések

**K: Kezeli az Aspose.Tasks for Java a komplex, többfázisú projekteket?**  
V: Igen, teljes mértékben támogatja a feladatokat, erőforrásokat, hozzárendeléseket, alapvonalakat és egyéni mezőket minden Project verzióban 2024‑ig.

**K: Elérhető próbaverzió?**  
V: Teljesen – töltsön le egy ingyenes próbaverziót [itt](https://releases.aspose.com/).

**K: Hol kaphatok segítséget, ha problémám van?**  
V: A hivatalos támogatási fórum a [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), ahol a személyzet és a közösség tagjai válaszolnak a kérdésekre.

**K: Szerezhetek ideiglenes licencet rövid távú értékeléshez?**  
V: Igen, vásároljon ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/).

**K: Fut az Aspose.Tasks Linuxon és macOS‑on?**  
V: Teljesen keresztplatformos, és működik Windows, macOS és Linux rendszereken bármely Java 8+ futtatókörnyezettel.

---

**Legutóbb frissítve:** 2026-05-26  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12 (latest)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre MPP fájlt – Üres projekt létrehozása és mentése MPP formátumban az Aspose.Tasks segítségével](/tasks/java/project-configuration/create-save-mpp/)
- [MPP fájl betöltése Java - Projekt tulajdonságok kezelése az Aspose.Tasks segítségével](/tasks/java/project-management/default-properties/)
- [Hogyan exportáljunk MPP-t Excel-be az Aspose.Tasks for Java segítségével](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
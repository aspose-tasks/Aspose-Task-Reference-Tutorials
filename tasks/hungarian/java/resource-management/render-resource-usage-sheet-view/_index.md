---
date: 2026-01-15
description: Tanulja meg, hogyan mentse el a projektet PDF‑ként, és hogyan jelenítse
  meg az MS Project erőforrás‑használat és lap nézeteket az Aspose.Tasks for Java
  segítségével. Kövesse lépésről‑lépésre útmutatónkat a projekt PDF‑be exportálásához
  könnyedén.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt mentése PDF‑ként – Erőforrás‑felhasználás és táblanézet megjelenítése
  az Aspose.Tasks‑ben
url: /hu/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt mentése PDF‑ként – Erőforrás‑használat és Lap nézet renderelése az Aspose.Tasks‑ben

## Bevezetés
Ebben az útmutatóban megtudja, hogyan **mentse a projektet PDF‑ként**, miközben a Microsoft Project fájl Erőforrás‑használat és Lap nézeteit rendereli. Akár nyomtatható jelentést kell készítenie az érintettek számára, akár MPP fájlokat szeretne egy mindenki számára megtekinthető formátumba konvertálni, az Aspose.Tasks for Java egyszerűvé teszi a folyamatot – Microsoft Project telepítése nélkül.

## Gyors válaszok
- **Mit csinál a „save project as pdf”?** Egy Project fájlt (MPP) PDF dokumentummá konvertálja, megőrizve a kiválasztott nézetet.  
- **Mely nézet exportálható?** Erőforrás‑használat, Lap, Gantt, Feladat‑használat és egyéb.  
- **Módosítható a PDF‑ben a időskála?** Igen – a lehetőségek közé tartozik a Days, ThirdsOfMonths és Months.  
- **Szükséges a Microsoft Project telepítve?** Nem, az Aspose.Tasks önállóan működik.  
- **Kell licenc a termeléshez?** Igen, kereskedelmi licenc szükséges a nem‑próba használathoz.

## Mi a „save project as PDF”?
A projekt PDF‑ként való mentése egy statikus, nagy felbontású ábrázolást hoz létre a kiválasztott Project nézetről. Ez ideális ügyfelekkel való megosztásra, archiválásra vagy nyomtatásra anélkül, hogy a háttérben lévő projektfájlt felfedné.

## Miért használja az Aspose.Tasks‑t a projekt PDF‑be exportálásához?
- **Nincs külső függőség** – bármely Java‑t támogató platformon működik.  
- **Finomhangolt vezérlés** – kiválaszthatja a nézetet, az időskálát és az elrendezést.  
- **Magas hűség** – a PDF tükrözi az eredeti Project nézet megjelenését.  
- **Automatizálásra kész** – integrálható CI csővezetékekbe, jelentési szolgáltatásokba vagy kötegelt konvertálókba.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK)** – a legújabb verzió ajánlott.  
2. **Aspose.Tasks for Java** – töltse le a [letöltési oldalról](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először importálja a szükséges osztályokat a Java projektjébe:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Lépésről‑lépésre útmutató

### 1. lépés: A forrásprojekt beolvasása
Töltse be a konvertálni kívánt MPP fájlt.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 2. lépés: SaveOptions definiálása a szükséges időskálával (Projekt exportálása PDF‑be)
Állítsa be a PDF exportálási beállításokat, és adja meg a kívánt időskálát.  
*Ebben a példában a **Days**‑t használjuk.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 3. lépés: A PresentationFormat beállítása ResourceUsage‑ra
Válassza ki a renderelni kívánt nézetet. Ebben az esetben a **Resource Usage** nézet.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 4. lépés: Projekt mentése (MPP konvertálása PDF‑be)
Hajtsa végre a konverziót, és generálja a PDF fájlt.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### 5. lépés: Nézetek renderelése más időskála beállításokhoz (Időskála módosítása PDF‑ben)
Ismételje meg az előző lépéseket, hogy különböző időskálákkal, például **ThirdsOfMonths** és **Months**, PDF‑eket hozzon létre.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Gyakori problémák és megoldások
- **File not found hibák** – Ellenőrizze, hogy a `dataDir` a megfelelő mappára mutat-e, és hogy az MPP fájl neve pontosan egyezik-e.  
- **Üres PDF kimenet** – Győződjön meg arról, hogy a `PresentationFormat` olyan nézethez van beállítva, amely tartalmaz adatot (pl. ResourceUsage).  
- **Helytelen időskála** – Ellenőrizze, hogy a `options.setTimescale()` minden `project.save()` előtt meghívásra került.

## Gyakran feltett kérdések

### Az Aspose.Tasks képes más nézetek renderelésére is az Erőforrás‑használat és Lap mellett?
Az Aspose.Tasks különféle nézetek renderelését támogatja, például Gantt-diagram, Task Usage és Calendar nézetek, többek között.

### Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?
Igen, az Aspose.Tasks széles körű Microsoft Project fájlformátumot támogat, beleértve az MPP, MPT és XML formátumokat.

### Testreszabhatom a renderelt nézetek megjelenését az Aspose.Tasks használatával?
Természetesen! Az Aspose.Tasks kiterjedt lehetőségeket kínál a renderelt nézetek megjelenésének és elrendezésének testreszabására, hogy megfeleljenek az Ön egyedi igényeinek.

### Az Aspose.Tasks megköveteli a Microsoft Project telepítését a rendszeren?
Nem, az Aspose.Tasks egy önálló könyvtár, és nem igényli a Microsoft Project telepítését a működéséhez.

### Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
Igen, az Aspose.Tasks felhasználók technikai támogatást vehetnek igénybe a [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utolsó frissítés:** 2026-01-15  
**Tesztelve a következővel:** Aspose.Tasks for Java 24.12  
**Szerző:** Aspose
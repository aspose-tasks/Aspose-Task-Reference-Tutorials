---
title: Rendererje le az erőforráshasználatot és a lapnézetet az Aspose.Tasks alkalmazásban
linktitle: Rendererje le az erőforráshasználatot és a lapnézetet az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan jeleníthet meg MS Project erőforrás-használati és munkalapnézeteket az Aspose.Tasks for Java alkalmazásban. Kövesse lépésenkénti útmutatónkat, hogy könnyedén készítsen részletes PDF jelentéseket.
weight: 16
url: /hu/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rendererje le az erőforráshasználatot és a lapnézetet az Aspose.Tasks alkalmazásban

## Bevezetés
Ebben az oktatóanyagban megtanuljuk, hogyan használhatja az Aspose.Tasks for Java-t az MS Project Resource Usage és Sheet nézeteinek megjelenítéséhez. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára, hogy a Microsoft Project telepítése nélkül dolgozzanak Microsoft Project fájlokkal.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy telepítette és beállította a következő előfeltételeket:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a Java Development Kit telepítve van a rendszeren. A JDK legújabb verzióját letöltheti és telepítheti az Oracle webhelyéről.
2.  Aspose.Tasks for Java: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat a[letöltési oldal](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először is importálnia kell a szükséges csomagokat a Java projektbe:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 1. lépés: Olvassa el a Forrásprojektet
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
// Olvassa el a projekt forrását
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
Ebben a lépésben megadjuk a forrás Project fájl elérési útját (`ResourceUsageView.mpp` ), és használja a`Project` osztályt elolvasni.
## 2. lépés: Adja meg a mentési beállításokat a szükséges időskála-beállításokkal
```java
// Határozza meg a mentési beállításokat a szükséges időskála-beállításokkal Napokként
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Itt definiáljuk a`SaveOptions` a szükségesvel`TimeScale` beállítások. Ebben a példában beállítjuk a`TimeScale` a mai.
## 3. lépés: Állítsa a Prezentációs formátumot ResourceUsage értékre
```java
// Állítsa a Prezentáció formátumát ResourceUsage értékre
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Beállítottuk a prezentáció formátumát`ResourceUsage`, jelezve, hogy az Erőforráshasználat nézetet szeretnénk megjeleníteni.
## 4. lépés: Mentse el a projektet
```java
// Mentse el a projektet
project.save(dataDir + days, options);
```
Végül elmentjük a Projektet a megadott opciókkal. Ebben a példában a kimeneti fájl a következő néven lesz elmentve`result_days.pdf`.
## 5. lépés: Rendereljen nézeteket az egyéb időskála-beállításokhoz
Ismételje meg a 2–4. lépéseket a nézetek megjelenítéséhez különböző időskála-beállításokkal (Hónapok harmada és hónap).
```java
// Állítsa az Időskála beállításait ThirdsOfMonths értékre
options.setTimescale(Timescale.ThirdsOfMonths);
// Mentse el a projektet
project.save(thirds, options);
// Állítsa az Időskála beállításait Hónapokra
options.setTimescale(Timescale.Months);
// Mentse el a projektet
project.save(dataDir + months, options);
```
 Győződjön meg arról, hogy megváltoztatja a`Timescale` minden nézethez megfelelő beállításokat.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan használhatjuk az Aspose.Tasks for Java-t az MS Project Resource Usage és Sheet nézeteinek megjelenítésére. A fent vázolt lépések követésével hatékonyan hozhatja létre ezeket a nézeteket PDF formátumban, megkönnyítve a projektadatok jobb megjelenítését és elemzését.
## GYIK
### Az Aspose.Tasks megjeleníthet más nézeteket az Erőforrás-használaton és a Munkalapon kívül?
Az Aspose.Tasks támogatja a különféle nézetek, például Gantt-diagram, Feladathasználat és Naptár nézetek megjelenítését.
### Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?
Igen, az Aspose.Tasks a Microsoft Project fájlformátumok széles skáláját támogatja, beleértve az MPP, MPT és XML formátumokat.
### Testreszabhatom a megjelenített nézetek megjelenését az Aspose.Tasks segítségével?
Teljesen! Az Aspose.Tasks kiterjedt lehetőségeket kínál a renderelt nézetek megjelenésének és elrendezésének testreszabására az Ön egyedi igényei szerint.
### Az Aspose.Tasks használatához telepíteni kell a Microsoft Projectet a rendszeren?
Nem, az Aspose.Tasks egy önálló könyvtár, és működéséhez nem szükséges a Microsoft Project telepítése.
### Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
 Igen, az Aspose.Tasks felhasználók technikai támogatást vehetnek igénybe a következőn keresztül[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

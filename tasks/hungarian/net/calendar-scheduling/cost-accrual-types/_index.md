---
date: 2026-07-05
description: Ismerje meg, hogyan követheti nyomon a projekt költségvetését és kezelheti
  a projekt költségeit az Aspose.Tasks for .NET használatával. Határozza meg a költségfelhalmozási
  típusokat a pontos költségkövetéshez.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Költségfelhalmozási típusok az Aspose.Tasks-ben
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Kövesse a projekt költségvetését a költségfelhalmozási típusokkal az Aspose.Tasks-ben
url: /hu/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt költségvetés nyomon követése költség felhalmozási típusokkal az Aspose.Tasks-ben

## Bevezetés

Pontos **követni a projekt költségvetését** a sikeres projektmegvalósítás gerince. Ha a költséginformációkat a megfelelő pillanatokban rögzítik, előre jelezhetők a túllépések, módosíthatók az erőforrások, és a résztvevők tájékoztathatók. Az Aspose.Tasks for .NET finomhangolt vezérlést biztosít a költség felhalmozás felett, lehetővé téve, hogy eldöntse *mikor* kerül a költség rögzítésre – legyen az a munka kezdete, folyamatosan, vagy csak a munka befejezésekor. Ez az útmutató végigvezet a koncepciókon, bemutatja, hogyan állítsa be a felhalmozási típust, és demonstrálja a megbízható költségvetés‑követés legjobb gyakorlatait.

## Gyors válaszok
- **Mi a költség felhalmozási típusok elsődleges célja?** Meghatározzák a feladat életciklusának azt a pontot, amikor a költség elismerésre kerül, lehetővé téve a pontos költségvetés‑követést.  
- **Melyik enum érték késlelteti a költséget, amíg a munka be nem fejeződik?** `CostAccrualType.End`.  
- **Szükségem van licencre a kód futtatásához?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termelési használathoz.  
- **Módosíthatom egyszerre több erőforrás felhalmozási típusát?** Igen—iteráljon a `Resources` gyűjteményen, és rendelje hozzá a kívánt típust.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a költség felhalmozási típus?
A **cost accrual type** megmondja az Aspose.Tasks-nek, mikor alkalmazza egy erőforrás költségét a projekt költségvetésére. Ezt a `CostAccrualType` felsorolás képviseli, és beállítható erőforrásonként vagy feladatonként. A megfelelő típus kiválasztása biztosítja, hogy a költségadatok összhangban legyenek a szervezet számlázási szabályaival, legyen szó a költségek munka kezdetén történő rögzítéséről, időarányos elosztásról a teljes időtartam alatt, vagy csak a befejezés után.

## Miért érdemes a projekt költségvetését költség felhalmozási típusokkal nyomon követni?
Az Aspose.Tasks **négy** felhalmozási lehetőséget támogat—`Start`, `Prorated`, `Duration` és `End`—amelyek lefedik a tipikus projektkönyvelési forgatókönyvek teljes skáláját. A megfelelő opció kiválasztása lehetővé teszi, hogy a költségfelismerést a szerződéses számlázási ciklusokhoz igazítsa, csökkentse a pénzügyi jelentések eltéréseit, és költségkimutatásokat generáljon, amelyek zökkenőmentesen integrálódnak az ERP rendszerekkel, miközben nagy projektek esetén alacsony memóriahasználatot tart fenn.

## Előkövetelmények

Mielőtt elkezdenénk, győződjön meg arról, hogy rendelkezik a következő előkövetelményekkel:

### 1. Telepítse az Aspose.Tasks for .NET-et
A kezdéshez telepítve kell legyen az Aspose.Tasks for .NET a fejlesztői környezetben. A könyvtárat letöltheti a [download page](https://releases.aspose.com/tasks/net/) oldalról, és kövesse a mellékelt telepítési útmutatót.

### 2. Ismerje a .NET keretrendszert
Alapvető ismeretek a .NET keretrendszerről és a C# programozási nyelvről szükségesek ahhoz, hogy követhesse a példákat ebben az útmutatóban.

## Hogyan állítsuk be a költség felhalmozási típust egy erőforrásra?

A projekt betöltése, a cél erőforrás megtalálása, és a kívánt `CostAccrualType` hozzárendelése. Az alábbi két soros minta a szabványos megközelítés: hozzon létre egy `Project` példányt, szerezze be az erőforrást az azonosítója alapján, majd állítsa be a `CostAccrualType`-ot. Ez a tömör sorozat biztosítja, hogy **követni a projekt költségvetését** pontosan már az erőforrás hozzáadása pillanatától.

### 1. lépés: Névterek importálása
Kezdjük a szükséges névterek importálásával, hogy hozzáférjünk az Aspose.Tasks funkcionalitáshoz a .NET projektünkben:

```csharp

```

### 2. lépés: Projektfájl betöltése
`Project` osztály egy Microsoft Project fájlt képvisel, és hozzáférést biztosít a feladatokhoz, erőforrásokhoz és egyéb adatokhoz.

```csharp
var project = new Project("Project2.mpp");
```

### 3. lépés: Erőforrás elérése
A `Resources` gyűjtemény tartalmazza a projektben definiált összes erőforrást. A `GetById` metódus egy erőforrást kér le az egyedi azonosítója alapján.

```csharp
var resource = project.Resources.GetById(1);
```

### 4. lépés: Költség felhalmozási típus beállítása
A `Set` metódus értéket ad egy erőforrás mezőnek.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Itt állítjuk be a költség felhalmozási típust az erőforrásra. Ebben a példában `CostAccrualType.End`-re állítjuk, ami azt jelenti, hogy a költségek csak akkor halmozódnak fel, amikor a hátralévő munka nulla. Az `End` választása ideális, ha csak a feladat teljes befejezése után szeretné **követni a projekt költségvetését**.

### 5. lépés: Folytassa a munkát a projekttel
A költség felhalmozási típus beállítása után folytathatja a munkát a projekttel a szükség szerint, további műveleteket vagy számításokat végezve, például költségjelentések generálása, hozzárendelések frissítése vagy a fájl exportálása.

## Általános buktatók és profi tippek
- **Pro tip:** Mindig hívja meg a `project.Save`-t a felhalmozási típusok módosítása után a változások mentéséhez.  
- **Pitfall:** A `CostAccrualType.Start` beállítása egy olyan erőforrásra, amely soha nem kezdi meg a munkát, felpúposíthatja a költségvetési jelentéseket – először ellenőrizze a feladat ütemezéseket.  
- **Pro tip:** Használja a `project.Resources.ToList()`-et, amikor sok erőforrást kell egyszerre frissíteni; ez elkerüli a többszöri gyűjteménykeresést és javítja a teljesítményt nagy projektek esetén.

## Gyakran feltett kérdések

**Q:** Módosíthatom egyszerre több erőforrás felhalmozási típusát?  
A: Igen, iteráljon a `project.Resources`-en, és rendelje hozzá a kívánt `CostAccrualType`-ot minden erőforráshoz egy `foreach` ciklusban.

**Q:** Melyek a `End`-en kívül elérhető költség felhalmozási típusok?  
A: Az Aspose.Tasks a `Start`, `Prorated` és `Duration` típusokat biztosít – mindegyik egy külön számlázási stratégiához illeszkedik.

**Q:** Hogyan határozhatom meg egy adott erőforrás aktuális költség felhalmozási típusát?  
A: A `resource.Get(TskResource.CostAccrualType)` segítségével kérheti le az értéket; ez visszaadja az aktuális beállítást reprezentáló enumot.

**Q:** Lehet különböző költség felhalmozási típusokat alkalmazni különböző feladatokra ugyanabban a projektben?  
A: Természetesen. Mind a feladatok, mind az erőforrások rendelkeznek `CostAccrualType` tulajdonsággal, amely lehetővé teszi az egyes entitások független beállítását.

**Q:** Támogatja az Aspose.Tasks egyedi költség felhalmozási típusokat?  
A: Nem, a könyvtár jelenleg csak a négy beépített típust támogatja; egyedi logikát külsőleg kell megvalósítani, ha szükséges.

---

**Utoljára frissítve:** 2026-07-05  
**Tesztelve a következővel:** Aspose.Tasks 24.8 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Aspose.Tasks naptár és ütemezés](/tasks/net/calendar-scheduling/)
- [MS Project díjak kezelése az Aspose.Tasks for .NET segítségével](/tasks/net/rate-recurring-tasks/handling-rates/)
- [MS Project erőforrások könnyed kezelése az Aspose.Tasks segítségével](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}